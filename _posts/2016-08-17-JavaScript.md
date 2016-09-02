---
layout: post
title:  "前端开发利器——JavaScript"
date:   2016-08-17
---

>JavaScript是前端开发的基础，也可以说是前端开发的灵魂，其基础知识是每一个前端开发者应该熟练掌握的。

#### 一、JavaScript的基本内容

一个完整的JavaScript实现包括三个不同的部分：核心ECMAScript、文档对象模型DOM和浏览器对象模型BOM。

1、ECMAScript主要规定了这门语言的语法、类型、语句、关键字、保留字、操作符和对象等组成部分。  
2、DOM是针对XML但经过扩展用于HTML的应用程序接口，它把整个页面映射为一个多层节点结构。  
（1）DOM1级的目标主要是映射文档的结构，包括DOM核心和DOM HTML；  
（2）DOM2级在原来的基础上扩充了鼠标和用户界面时间、范围、遍历等模块，主要包括DOM视图、DOM事件、DOM样式和DOM遍历及范围；  
（3）DOM3级进一步扩充了DOM，新增了验证模块方法，开始支持XML1.0规范。  
3、BOM用于控制浏览器显示的页面以外的部分，主要包括弹出窗口、改变浏览器窗口、navigator对象、location对象、screen对象和支持cookies等。

#### 二、JavaScript语法

##### 一、数据类型

ECMAScript中包括5种基本数据类型：Undefined、Null、Boolean、Number和String。还有一种复杂数据类型：Object。使用typeof可以检测变量的数据类型。  
Undefined：只有一个值，即undefined，是变量未定义或未初始化时的值。  
Null：只有一个值，即null，是一个空指针对象。undefined值派生自null值，即null==undefined为真。  
Boolean：有两个值，即true和false。所有类型都有与这两个值等价的值，可以调用Boolean()将其转换为对应的Boolean值。  
Number:包括整数和浮点数值，可以使用Number()进行数值转换。NaN表示非数值，它与任何值都不相等（包括NaN本身），可以使用isNaN()判断。  
String:表示零或多个16位Unicode字符组成的字符序列，可以使用String()方法进行类型转换。  
Object:一组数据和功能的集合，即对象。

##### 二、变量和作用域问题

访问变量有按值和按引用两种方式，而函数的参数只能按值传递。

作用域包括全局作用域和函数的局部作用域，其中的变量分别对应全局环境的变量和局部函数的变量。

##### 三、引用类型

对象是引用类型的实例，新对象是使用new操作符后跟一个构造函数来创建的，使用instanceof可以检测引用的类型。

1、Object类型

创建Object实例的方式：  
（1）使用new操作符后跟Object构造函数：  
var person=new Object();person.name="tian";person.age=25;  
（2）使用对象字面量表示法：  
var person={name:"tian",age:25}

访问对象属性的方式：  
（1）点表示法：  
alert(person.name);  
（2）方括号语法：  
alert(person["name"]);

2、Array类型

创建数组：  
（1）使用Array构造函数：  
var colors=new Array(3);  
var colors=new Array("red","blue","green");  
（2）使用数组字面量表示法：  
var colors=["red","blue","green"];   

数组方法：  
（1）转换方法：  
toLocaleString()：创建一个数组值的以逗号分隔的字符串，和机器的本地环境相关，  
toString()：返回由数组中每个值的字符串形式拼接而成的一个以逗号分隔的字符串  。
valueOf()：返回原来的数组。  
join("分隔符"):使用给定的分隔符构建字符串。  
（2）栈方法：  
push():可以接收任意数量的参数，把它们逐个添加到数组末尾，并返回修改后数组的长度。  
var colors=["red"]; &nbsp; var count=colors.push("green","blue"); &nbsp; alert(count);//2  
pop():从数组末尾移除最后一项，数组的长度减少1，然后返回移除的项。  
var colors=["red","blue"]; &nbsp; var item=colors.pop(); &nbsp; alert(item);//"blue"  
（3）队列方法：  
shift():移除数组中的第一项并返回该值，数组的长度减少1。  
push():和栈方法中相同。  
unshift():在数组前端添加任意个项并返回新数组的长度。  
（4）重排序方法：  
reverse():反转数组项的顺序。  
sort()：按照升序排列数组项。  
（5）操作方法：  
concat():返回一个新数组，将参数拼接到原有数组的后面。  
slice():返回一个新数组，其中的值是原数组对应的参数起始和结束之间的部分。  
splice():若是指定2个参数，则参数时要删除的第一项的位置和要删除的项数，返回一个新数组；若指定3个参数，且第2个是0，则第一个参数为起始位置，从该位置插入第三个参数；若指定3个参数，且第2个不是0，则参数分别对应起始位置，要删除的项数，要插入的任意数量的项。  
（6）位置方法：  
indexOf():从数组的开头向后查找，可以指定开始位置，返回要查找参数的位置。  
lastIndexOf():从数组的末尾开始向前查找，可以指定开始位置，返回要查找参数的位置。  
（7）迭代方法：  
every():对数组中的每一项运行给定的函数，若该函数对每一项都返回true，则返回true。  
filter():对数组中的每一项运行给定的函数，返回该函数true的项组成新的数组。  
foreach():对数组中的每一项运行给定的函数，没有返回值。  
map():对数组中的每一项运行给定的函数,返回每次调用的结果组成的数组。  
some():对数组中的每一项运行给定的函数,如果该函数对任一项返回true，则返回true。  
foreach():与使用for循环迭代数组相同，没有返回值。  
（8）归并方法：  
reduce():从数组的第一项开始，逐个遍历到最后，构建一个返回值。  
reduceRight():从数组的最后一项开始，向前遍历到第一项，构建一个返回值。  

3、Date类型  

和日期时间相关的类型，包含若干组件方法。  
