##<center>JavaScript_01
####什么是JavaScript
>1. JavaScript是一种计算机编程语言 <br>
	通过给计算机处理问题的逻辑指令从而得到相应结果的一种人机交互语言
	HTML是标记语言,CSS是层叠样式表, 都不能算作编程语言, 因为不具备图灵完备性(一切可计算的问题都能计算，--图灵机)  
>1. JavaScript 是 性价比最高的语言
>1. JavaScript 是 世界上最被误解的语言<br>
     与java的关系  雷锋 | 雷峰塔
>1. JavaScript 是 世界上最好的语言
>1. JavaScript 是 世界上最流行的语言
>1. JavaScript 必 将统治全宇宙 <br>

<img src="./img/1.png"/>

---

####JavaScript能做什么？
>1. Web前端     html  css   JavaScript
>1. node.js 后端  
>1. Hybrid App（混合app） 淘宝 微信 京东.. <br>
Native App是一种基于智能手机本地操作系统如iOS、Android、WP并使用原生编写运行的第三方应用程序,也叫本地app <br> 
Hybrid App（混合模式移动应用）是指介于web-app、native-app这两者之间的app，兼具“Native App良好用户交互体验的优势”和“Web App跨平台开发的优势”。
比如街旁网最开始的应用就是包了个客户端的壳，其实里面是HTML5的网页，后来才推出真正的原生应用 <br>
Hybrid总体特性更接近Native App但是和Web App区别较大。只是因为同时使用了网页语言编码，所以开发成本和难度比Native App要小很多
>1. 桌面应用
>1. 游戏 cocos2d-js  unity3D  白鹭
>1. 阿特伍德定律 <br>
    any application that can be written in JavaScript, will eventually be written in JavaScript.
                                                         ---Jeff Atwood

####计算机编程语言的分类   
>1. 机器语言 00101010101011011   
>1. 汇编语言 计算机只能读懂机器指令，程序员用汇编语言写出的源程序，再用汇编编译器将其编译为机器码，再由计算机执行。--符号语言,不同的计算机有不同的汇编语言。
>1. 高级语言 -- 编译语言（c++等） -- 解释性语言(JavaScript,Python,php,Perl等)
 <br>
 1. 编译语言  - > 编译 ->执行 （项目完成以后不需要再进行翻译）开发慢，执行效率快
 2. 解释语言  由编译语言开发,不需要编译,执行的时候翻译。开发快，执行效率慢
####JavaScript的由来
>1. 1992年底，美国国家超级电脑应用中心（NCSA）开始开发一个独立的浏览器，叫做Mosaic。
>1. 1994年10月，NCSA的一个主要程序员Marc Andreessen联合风险投资家Jim Clark，成立了Mosaic通信公司，不久后改名为Netscape(网景)。
>1. 1994年12月，Netscape发布浏览器Navigator1.0，市场份额一举超过90%。
>1. 1995年 Netscape 程序员 Brendan Eich 设计出了LiveScript1.0  后来 改名 JavaScript
>1. 1996年3月，Navigator 2.0浏览器正式内置了JavaScript脚本语言。
>1. 1996年8月，微软模仿JavaScript开发了一种相近的语言，取名为JScript, 内置于IE3.0
>1. 1996年11月，网景公司决定将JavaScript提交给欧洲计算机制造联合会ECMA，希望JavaScript能够成为国际标准，以此抵抗微软。
>1. 1997年7月，ECMA组织发布262号标准文件（ECMA-262）的第一版，规定了浏览器脚本语言的标准，并将这种语言称为ECMAScript。这个版本就是ECMAScript 1.0版。
>1. 2009年12月，ECMAScript 5.0版正式发布。
>1. 2011年6月，ECMAscript 5.1版发布，并且成为ISO国际标准
>1. 2015年6月17日，ECMAScript 6发布正式版本，即ECMAScript 2015
####JavaScript 的语言特点
>1. JavaScript是弱类型语言
>1. JavaScript是事件驱动的语言
>1. JavaScript是一种基于对象的语言   (面向对象的三个基本特性：继承 封装  多态)
>1. JavaScript具有跨平台性。
>1. JavaScript具有安全性与简单性  -操作系统的安全
####JavaScript 的局限性   
>1. 浏览器的兼容。 
>1. 执行效率的问题。
####JavaScript 的运行和开发环境
	1. 浏览器上运行：chrome firefox opera safari IE 360
	2. 编译器：     sublime notepad++  webstrom 记事本
	3. JavaScript程序是用Unicode字符集编写的 
	4. utf = Unicode transformation formats
	5. 严格区分大小写 （html不区分大小写）
####布兰登·艾克   
	十天发明JavaScript
	新官上任的布兰登·艾克到底做错了什么，为何如此让人憎恨？ 因为他反对同性恋。
	2014年3月24日，艾克晋升为Mozilla公司首席执行官引发同性恋族群反弹，
	4月3日，艾克宣布从Mozilla离职。
##JavaScript的基本语法
####JavaScript 在html中的使用
>1. 在script标签中写js代码
>1. 导入外部的JavaScript脚本文件
>1. 通过事件属性定义在元素的内部
####JavaScript 的注释
>1. 单行注释：  //
>1. 多行注释：  /* */ 
####指令(语句)结束符
>1.    ;       -英文的分号
>1.    换行
####在页面中输出内容  
>1. document.write(); 输出到文档流
>1. console.log();	 输出到控制台
####三个基本的弹框
 >1. alert();  提示框  警告框
 >1. confirm(); 确认框   
 >1. prompt(); 输入框 --可以有两个参数<br>
	1. 提示信息
	2. 输入框默认内容
####第一个JavaScript的应用
>1. 获取html中的dom元素  : document.getElementById();
>1. 元素的应用：             得到元素的属性
>1. 事件的应用：				触发了事件再执行某段代码
>1. 函数的简单调用：			把好多代码作为一个整体，调用的时候执行
>1. 简单运算符的应用：       +   -  *   /   %  =

####变量和直接量
>1. 直接量     程序中直接使用的数据值   -- 关键字(保留字)不能直接使用
>1. 变量		数据临时存储的容器  <br>
   	1. 长久存储使用数据库，临时存储使用变量
  	2. 变量使用前必须先声明
####变量声明  
>1.  声明一个变量    var 变量名=值；
>1.  声明多个变量    var 变量1=值，var 变量2 = 值，var 变量3 = 值

####JavaScript变量特性
>1. 没有赋值的变量初始值为undefined
>1. 动态类(弱类型)语言：在运行期间才去做数据类型检查的语言，编程时不用给任何变量指定数据类型。如： Python  PHP  Ruby JavaScript
>1. 静态类(强类型)语言：数据类型是在编译期间检查，在写程序时，要先声明所有变量的数据类型。如：c  c++  c#  java
>1. 给没有声明的变量赋值，严格模式下会报错。（‘use strict’）
####命名规则    
>1. 数字  字母   _  $ 组成 但是不能以数字开头
>1. 不能与系统保留字冲突  

<img src="./img/1s.png">      
       
  
---
       
####数据类型  
######原始类型  
>1. 数字 	Number
>1. 字符串 	String
>1. 布尔值 	Boolean
>1. 空	  	null
>1. 未定义 	undefind 
######对象类型   
>1. 数组    Array
>1. 函数	Function
>1. 日期	Date
>1. 正则	RegExp
>1. 错误	Error  .......
####数据类型的检测
>1. 检测数据类型的方法  typeof()


