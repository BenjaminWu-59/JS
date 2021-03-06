# 认识JavaScript

### 定义

JavaScript（通常缩写为JS）是一种高级的、解释型的编程语言。JS是一门基于原型、函数先行的语言，是一门多范式的语言，它支持面向对象程序设计，命令式编程，以及函数式编程。它提供语法来操控文本、数组、日期以及正则表达式等，不支持I/O，比如网络、存储和图形等，但这些都可以由它的宿主环境提供支持。它已经由ECMA（欧洲电脑制造商协会）通过ECMAScript实现语言的标准化。它被世界上的绝大多数网站所使用，也被世界主流浏览器（Chrome、IE、Firefox、Safari、Opera）支持。

---

### 历史

**初创**

1994年，由于网页浏览器的竞争已经开始。浏览器公司“网景”预见到网络需要变得更动态。公司的创始人马克·安德森认为HTML需要一种胶水语言，让网页设计师和兼职程序员可以很容易地使用它来组装图片和插件之类的组件，且代码可以直接编写在网页标记中。

1995年，网景便招募了布兰登·艾克（JS发明者），目标是把Scheme语言嵌入到Netscape Navigator浏览器当中。但更早之前，网景已经跟昇阳合作在Netscape Navigator中支持Java，这时网景内部产生激烈的争论。后来网景决定发明一种与Java搭配使用的辅助脚本语言并且语法上有些类似，这个决策导致排除了采用现有的语言，例如Perl、Python、Tcl或Scheme。为了在其他竞争提案中捍卫JavaScript这个想法，公司需要有一个可以运作的原型。艾克在1995年5月仅花了十天时间就把原型设计出来了。

最初命名为Mocha（摩卡），1995年9月在Netscape Navigator 2.0的Beta版中改名为LiveScript，同年12月，Netscape Navigator 2.0 Beta 3中部署时被重命名为JavaScript[1][16]，当时网景公司与昇阳电脑公司组成的开发联盟为了让这门语言搭上Java这个编程语言“热词”，因此将其临时改名为JavaScript，日后这成为大众对这门语言有诸多误解的原因之一。

**微软的采纳**

微软公司于1995年首次推出Internet Explorer，从而引发了与网景的浏览器大战。IE同样支持JS，但两家公司的脚本有差别。

发展初期，JavaScript的标准并未确定，同期有网景的JavaScript，微软的JScript双峰并峙。除此之外，微软也在网页技术上加入了不少专属对象，使不少网页使用非微软平台及浏览器无法正常显示，导致在浏览器大战期间网页设计者通常会把“用Netscape可达到最佳效果”或“用IE可达到最佳效果”的标志放在主页。

**走向标准化**

1996年11月，网景正式向ECMA（欧洲计算机制造商协会）提交语言标准。1997年6月，ECMA以JavaScript语言为基础制定了ECMAScript标准规范ECMA-262。JavaScript成为了ECMAScript最著名的实现之一

除此之外，ActionScript和JScript也都是ECMAScript规范的实现语言。尽管JavaScript作为给非程序人员的脚本语言，而非作为给程序人员的脚本语言来推广和宣传，但是JavaScript具有非常丰富的特性。

### 版本

| 版本 |       官方名称        |                             描述                             |
| :--: | :-------------------: | :----------------------------------------------------------: |
|  1   |  ECMAScript 1 (1997)  |                           第一版。                           |
|  2   |  ECMAScript 2 (1998)  |                       只改变编辑方式。                       |
|  3   |  ECMAScript 3 (1999)  |             添加了正则表达式。添加了 try/catch。             |
|  4   |     ECMAScript 4      |                         从未发布过。                         |
|  5   |  ECMAScript 5 (2009   | 添加了“严格模式”。添加了 JSON 支持。添加了 String.trim()。添加了 Array.isArray()。添加了数组迭代方法。 |
| 5.1  | ECMAScript 5.1 (2011) |                          编辑改变。                          |
|  6   |    ECMAScript 2015    | 添加了 let 和 const添加了默认参数值添加了 Array.find()添加了 Array.findIndex() |
|  7   |    ECMAScript 2016    |  添加了指数运算符（**）。添加了 Array.prototype.includes。   |
|  8   |    ECMAScript 2017    | 添加了字符串填充。添加了新的 Object 属性。添加了异步功能。添加了共享内存。 |
|  9   |    ECMAScript 2018    | 添加了 rest / spread 属性。添加了异步迭代。添加了 Promise.finally()。增加 RegExp。 |

### 优点

**一种可解释执行的脚本语言**
和其他脚本语言一样，JavaScript也是一种解释性语言，它提供了一个非常方便的开发过程。JavaScript的语言基本结构形式与C、C++、java十分类似。但是在使用前，不需要先编译，而是在执行过程中逐步的解释。JavaScript与HTML标识结合在一起，方便用户的使用。

**一种基于对象的脚本语言**
JavaScript也是一种面向对象的语言，这意味着JavaScript能运用其已经创建好的对象。因此，许多功能可以来自脚本环境中对象的方法与脚本的相互作用。

**一种简单弱类型脚本语言**
简单是JavaScript是一种基于java基本语句和控制流之上的简单而紧凑的设计，从而对于使用者来说学习C或者java语言是一种很好地过渡。JavaScript也非常容易上手，其次变量类型采用的是弱类型，并未使用严格的数据类型。

**一种相对安全脚本语言**
JavaScript语言不允许访问本地的硬盘，且不能将数据存入服务器，不允许对网络文档进行修改和删除。从而有效的防止数据的丢失或对系统非法访问。

**一种事件驱动的脚本语言**
JavaScript对于用户的响应，是以事件驱动的方式进行的。在网页的执行中，用户的操作被称为"事件"。当事件发生后，可能会引起相应的事件响应，执行对应的脚本，这种机制叫"事件驱动"。

**一种跨平台性脚本语言**
JavaScript依赖的是浏览器本身，与其操作环境无关，只要计算机能运行浏览器，并支持JavaScript的浏览器，就可以正确执行。

**JavaScript减少网络传输**
JavaScript可以被嵌入HTML文件中。所以当一位使用者输入一项资料时，此资料不需要传送给服务器，而是直接在客户端的应用程序所处理。

---

### 缺点

**设计阶段过于仓促**

Javascript的设计，其实只用了十天。由于设计时间太短，语言的一些细节考虑得不够严谨，导致后来很长一段时间，Javascript写出来的程序混乱不堪。

另一方面，这种语言的设计初衷，是为了解决一些简单的网页互动（比如，检查"用户名"是否填写），并没有考虑复杂应用的需要。设计者做梦也想不到，Javascript将来可以写出像Gmail这种极其庞大复杂的网页。

**没有先例**

Javascript同时结合了函数式编程和面向对象编程的特点，这很可能是历史上的第一例。而且直到今天为止，Javascript仍然是世界上唯一使用Prototype继承模型的主要语言。这使得它没有设计先例可以参考。

**过早的标准化**

Javascript的发展非常快，根本没有时间调整设计。

1995年5月，设计方案定稿；10月，解释器开发成功；12月，向市场推出，立刻被广泛接受，全世界的用户大量使用。Javascript缺乏一个从小到大、慢慢积累用户的过程，而是连续的爆炸式扩散增长。大量的既成网页和业余网页设计者的参与，使得调整语言规格困难重重。

更糟的是，Javascript的规格还没来及调整，就固化了。

1996年8月，微软公司强势介入，宣布推出自己的脚本语言Jscript；11月，为了压制微软，网景公司决定申请Javascript的国际标准；1997年6月，第一个国际标准ECMA-262正式颁布。

也就是说，Javascript推出一年半之后，国际标准就问世了。设计缺陷还没有充分暴露就成了标准。相比之下，C语言问世将近20年之后，国际标准才颁布。



