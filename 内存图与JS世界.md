# 内存图与JS世界

|       英语       |         翻译         |  英语   |    翻译    |
| :--------------: | :------------------: | :-----: | :--------: |
| Operating System |       操作系统       | kernel  |    内核    |
|     runtime      | 运行时（需要的东西） | compile |    编译    |
|   environment    |      环境，env       | memory  | 记忆、存储 |
|      person      |        一个人        | people  |   一群人   |

### 浏览器的运行

![](.\pictrure1\1.png)

---

### JS引擎

**JS引擎距离**

- chrome用的是v8引擎，C++编写
- 网景用的是spidermonkey，后被firefox使用，c++
- Safari用是JavaScriptCore
- IE用的是Chakra（JavaScript9）
- edge用的是Chakra（JS）
- node.js用的是V8引擎

**主要功能**

- 编译： 把JS代码翻译为机器能执行的字节码或机器码

- 优化： 改写代码，使其更高效

- 执行：执行上面的字节码或机器码

- 垃圾回收：把JS用完的内存回收，方便之后再次使用

---

### 执行JS代码

**准备工作**

- 提供API：window / document / setTimeout（浏览器提供）
- 上面这些东西都不是JS自身具备的功能
- 我们将这些功能成为运行环境runtime env
- 一旦把JS放进页面，就开始执行JS 

**等一下**

 JS代码在哪里运行？

答案：内存

哪里的内存？

答案：看下一节

---

### 内存

![](.\pictrure1\2.png)

##### 红色区域

- 红色区域专门用来存放数据（重点研究）
- 红色区域不存在变量名，变量名在[不知什么区]
- 每种浏览器的分配规则是不一样的
- 上图的区域并不完整，调用栈、任务队列还没有画

##### Stack和Heap

- 红色区分为Stack栈和Heap堆

- Stack区特点：每个数据顺序存放

- Heap区热点：每个数据随机存放

- 规律：

  ​           数据分两种：非对象（数字、字符串、布尔值）和对象

  ​           非对象存于stack，对象存于heap

  ​            =号总是将右边的东西复制到左边（并不存在什么传值和传址）

---
### JS运行需要的东西                    

###### window 

window由浏览器提供，以下都挂到了window上：

- console

- document

- 对象(Object，**函数实现**)

  var person={}等价于var person = new Object()

  **注意**：Object  是一个全局函数，可以生成对象，var obj=new Object()可以简写成 var obj{};

  ​            object什么也不是，除非我生成一个object；       

- 数组(Array，一种特殊的对象，**函数实现**)

  var a=[1,2,3]等价于 var a=new Array(1,2,3)

- 函数(Function,一种特殊的对象)

​       function f(){} 等价于 var f=new Function()

###### window内存图

![](.\pictrure1\3.png)

![](.\pictrure1\4.png)

###### window的一些细节

window变量和 window对象是两个东西。变量是一个容器，即存放对象的地址，而对象就是一坨坨的数据。同理，console、object也一样。

---

### prototype（原型链）

XXX.prototype 储存了 XXX 对象的共同属性

尝试理解下面的图：

![](.\pictrure1\5.png)

**如果没有原型会怎么样？**

![](.\pictrure1\6.png)

object与array本质是一种含有多种属性的对象，想调用这些属性，直接利用原型链这个原理即可。没有原型链，就要自己一行行的把属性敲出来了。

**隐藏属性**

每个对象都有一个隐藏属性，![](.\pictrure1\7.png)

与prototype里面的内容相同。每个新对象都会被挂上这个隐藏原型。

实验：

​          打开开发者工具的console

​          var obj ={}

​          obj

​           即可查看

​                                                                        **prototype**

​                                                                        挂在函数上

![](.\pictrure1\7.png)

​                                    挂在每个新成的对象（理解图中#9011中的fuck就是它）上                       

---

