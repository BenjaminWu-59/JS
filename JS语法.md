# JS语法

## 基本认知

#### 表达式与语句

##### 表达式

- 1+2表达式的值为3
- add（1，2）表达式的值为函数的返回值
- console.log表达式的值为函数本身
- console.log（3）表达式的值为多少？ **undifined**

##### 语句

var a=1 是一个语句

##### 二者的区别

- 语句是为了进行某种操作（如修改环境），一般情况下不需要返回值，而表达式都是为了得到返回值，一定会返回一个值（这里的值不包括undefined）
- 上面的话并不绝对

---

#### 关于空格和回车

- 大部分空格没有实际意义：

  ​                     var a= 1 和 var a=1 没有区别

- 加回车大部分时候也不影响，只有一个地方不能加回车，那就是return后面

---

#### 标识符

在JS中所有的可以由我们自主命名的都可以成为标识符，例如：变量名、属性名、函数名都属于标识符

##### 规则

第一个字符，可以使Unicode字母或$或_或中文

后面的字符，除了上面所说，还可以有数字

##### 标识符之变量名

- var _=1
- var $=2
- var______=6
- var 你好==‘hi’

##### 其他

用到再说

---

#### 注释

###### 主要写法

​                   `//  或 /* 注释 */`

###### 不好的注释

- 把代码翻译成中文
- 过时的注释
- 发泄不满的注释

###### 好的注释

- 采坑注解
- 解释复杂代码 或 bug 

---

#### 区块 block

###### 把代码包在一起

`{`

​    `let a = 1`

​    `let b = 2`

`}`

**常常与if/ for/ while 合用**

---

## 条件语句

#### if 语句

###### 语法

`if（表达式）{语句1}else{语句2}`

理解：如果表达式成立，则运行语句1；表达式不成立则运行语句2

记忆记忆！！（if默认选择最近的一个语句，因此只有一行时可以省略大括号，但非常不建议）

###### 比较变态的情况

- 表达式里的变态： 可以是a=1
- 语句1变态：里面再镶嵌 if else
- 语句2变态： 里面同样可以再镶嵌 if else
- return后面不可换行
- 缩进的变态：

​       `a=1`

​      `if（a === 2）`

​      `console.log('a')`

​      `console.log('a等于2')`

以上代码没有｛｝号，仅仅作用于第一句“console.log('a')。

如果是这种形式（加上“，”号）：

  `console.log('a')`，`console.log('a等于2')`

则成立，因为“，”表示语句没有结束。

一定要使用最没有歧义的写法！！

###### if写法推荐

最推荐的：

​      `if（表达式）｛`

​                  `语句`

​          `｝ else if（表达式）｛`

​          `｝else ｛`

​              `语句`

​          `｝`

次推荐：

​            `function fn(){`

​               `if(表达式){`

​                 `return 表达式`

​             `}`

​              `if （表达式）{`

​                 `return 表达式`

​              `}`

​             `return 表达式`

​         `}`

---

#### switch语句

switch 语句用于基于不同条件执行不同动作，是 if...else 的升级版

###### 语法

```javascript
switch(表达式) {
     case a:
        代码块1
        break;
     case b:
        代码块2
        break;
     default:
        默认代码块(兜底)
} 
```

case为：将...放入的意思，以上代码意为：选择a，则执行代码1；选择b，则执行代码2；没有选择或选择其他，则执行默认代码块（default 指当不存在 case可以匹配时，所运行的代码）。

###### break

一定不可省略

---

#### 问号冒号表达式

语法：

表达式1？表达式2：表达式3

镶嵌使用，一般在if和else两个条件后面都只有一句的时候使用

例：

​        `function max（a,b）{`

​             `if(a>b) return a;`

​            `else return b;`

​         `}`

可以改成：

​          `function max（a,b）{`

​              `return a>b ? a : b`

​         `}`

 ？a 表示：如果成立，则输出a；

 ：b 表示：不过不成立，则输出b；

---

#### &&短路逻辑

 A && B 本意指如果A是真的，则运行B；

 如果A是假的，就输出（运行）A；

 如果A是真的：就输出（运行）B；

![](.\pictrure1\8.png)

长话短说，即：A && B && C && D，取ABC中的**第一个假值**或D

---

#### ||短路逻辑

与&&相反，A || B 如果A是假的，则执行B（如果不是A，那就是B）

   A || B || C || D ,取ABC中**第一个真值**或D

---

## 循环语句

#### while循环

###### 语法

```javascript
while (表达式) {
    要执行的语句
}
```

当表达式为真，执行语句，执行完再继续判断表达式真假，一直为真就一直执行；

当表达式为假的时候，停止执行；

```javascript
var i = 0 //初始化

while(i<10){ //判断

    console.log(i）//循环体

    i = i+1 //增长

}
```

###### 其他

do...while 是 while 循环的变体。在检查条件是否为真之前，这种循环会执行一次代码块，然后只要条件为真就会重复循环。

```javascript
do {
    语句
}

while (表达式);
```

---

#### for循环

###### 语法

```javascript
for (语句 1; 表达式 2; 语句 3) {
     循环体
}
```

语句1相当于初始化，表达式2需要被判断，语句3为增长体

-  先执行语句1 =》 判断表达式2 
-  为真，则执行循环体，然后执行语句3，接着继续判断表达式2
-  为假，则直接退出循环

######  例子

              ```javascript
for(var i=0; i<5; i++){
    console.log(i)
}
              ```

​    console显示的有1、2、3、4。当i=5的时候，不符合条件，console不执行，循环执行完毕， i 的最终值是5

---

#### break和continue

退出所有循环 break

continue 退出当前一次循环（可以理解为next）

---

#### label

###### 语法

```javascript
foo:{
    console.log(1);
    break foo;
    console.log('本行不会输出')；
}
console.log(2);
```



###### 小知识

```javascript
{
  foo:1
}
```

这是个啥？

标记语句，内容为1（有个代码块叫foo，里面有个1）

没有什么实际意义



## 书籍推荐

阮一峰教程

[网道入门](https://wangdoc.com/javascript/basic/grammar.html)

《你不知道的JavaScript》（进阶用）

