##<center>JavaScript_18
###表单form   （项目经理讲解）
######获取方法
	1.通过id
	2.通过name
	3.document.forms;
######属性
	1.elements   --所有的表单元素
	document.myform.elements[0]  获取form第一个表单元素
######方法
>1. submit()  document.myform.submit(); --可将按钮放在form外面提交
>1. reset()   document.myform.reset():  --可将按钮放在form外面重置
####按钮button
######方法：
>1. focus()
>1. blur()
>1. click()  --设置按钮被点击
####单选框复选框
######方法：
>1. focus()
>1. blur()
>1. click()  --全选全不选
####文本域textarea 
######方法：
>1. focus()
>1. blur()   
>1. select() 
######补充知识点：window.clipboardData 剪切板操作  --仅IE支持
	方法：
	1.clearData(format);   	--删除剪切板指定格式的内容
	2.getData(format);     	--获取剪切板指定格式的内容
	3.setData(format,content); --设置剪切板内容及格式
####下拉菜单select
	下拉菜单的muliple属性（多选）
	双select的应用
######属性
	options 	菜单的集合
	length 		下拉菜单的长度
	index 菜单的索引
	方法
	add()    --添加
	remove() --移除 sel.remove(sel.index)
	focus()  --获取焦点
	blur()   --失去焦点
### call()  和 apply()的应用
####1. call() 的用法
>1. 改变this的指向(上下文的环境)  ------函数的方法
	
	实例一：
	function User(){
				this.name='大毛';
				this.showname = function(){
					console.log(this.name);
				}
			}
			function Show(){
				this.name='二毛';
			}
			var user = new User();
			var show = new Show();
			user.showname();     /// -----返回大毛
	user.showname.call(show);////---返回二毛  this的指向发生改变
	
	实例二：
	var index = '农妇三拳';
		function Getname(){
			this.index = '农夫果园';
		}
		function Demo(){
			this.index='嘀嘀打人';
			this.toshow = function(){
				console.log(this.index);
			}
		}
		var d = new Demo();
		d.toshow();				 //this 是d对象
		d.toshow.call();			//this 是window对象 
		d.toshow.call(new Getname); 	//this 是实例化得到的Getname对象
> 2.call的继承性
	
	function DD(){
			this.username = '小明',
			this.age = 12,
			this.say = function(){
				console.log(this.username+','+this.age);
			}
		}
		function FF(){
			DD.call(this);
		}
		var f = new FF();
		f.say();
###2. apply()的用法
>1. 与call类似。参数形式不同
>2. 调用一个对象的一个方法，以另一个对象替换当前对象。<br>
	
	即：改变this的指向    继承性
	1.call(obj,param1,param2,param3.....);
	2.apply(obj,[paran1,param2,param3...]);
	没有参数的情况下
		----与call一样
	有参数的情况下
	function Getname(name,age){
			this.name= name;
			this.age= age;
			this.toshow = function(){
				console.log(this.name+'今年'+this.age);
			}
		}
	function Toshow(name,age){
	//Getname.apply(this,arguments); //apply的方法继承
	//Getname.call(this,name,age); //call的方法继承
	//Getname.apply(this,name,age); //错误的参数形式
	}
	var show = new Toshow('大毛',21);
	show.toshow();


####函数声明的提前与程序的预执行
	(function(){
				function fn1(){ return 100}
				console.log(fn1());
				function fn1(){ return 200}
	})()
######试题： 
	demo();    
	demo = function(){alert(1)}
	demo();
	function demo(){alert(2)};
####对象传参的引用关系
	function demo(arr){
	//arr.push(4);
	arr = [1,2,3,4];
	}
	demo([1,2,3]);
####闭包
>1. 函数的自调用
>1. 循环中找到对应元素的索引  --一组控制另外一组
>1. 模块化开发 (面向对象封装)

###AJAX
	async Javascript and xml    异步的ajax和xml
####什么是异步
>1. 定时器的异步

####异步的作用：
>1. 传统的网页（不使用 AJAX）如果需要更新内容，必须重载整个网页页面。		
>2. 通过在后台与服务器进行少量数据交换，AJAX 可以使网页实现异步更新。	
>3. WebApp的开发: 后端程序只提供数据接口, 所有的数据需要ajax请求返回, JS动态生成
	
####概述：
>1. XMLHttpRequest 对象提供了对 HTTP 协议的完全的访问。
>2. XMLHttpRequest 可以同步或异步地返回 Web 服务器的响应，并且能够以文本或者一个 DOM 文档的形式返回内容。
	尽管名为 XMLHttpRequest，它并不限于和 XML 文档一起使用：它可以接收任何形式的文本文档。			

####第一步：获取XML对象
	new XMLHttpRequest()						在所有现代浏览器中（包括 IE 7）	
	new ActiveXObject("Microsoft.XMLHTTP")	在 Internet Explorer 5 和 6 中		

####XML对象的常用属性
>1. readyState		http请求状态
	
	0	Uninitialized	初始化状态。XMLHttpRequest 对象已创建或已被 abort() 方法重置。
	1	Open		open() 方法已调用，但是 send() 方法未调用。请求还没有被发送。
	2	Send		Send() 方法已调用，HTTP 请求已发送到 Web 服务器。未接收到响应。
	3	Receiving	所有响应头部都已经接收到。响应体开始接收但未完成。
	4	Loaded		HTTP 响应已经完全接收。
> 2.status	  由服务器发过来的响应状态码

	200 响应成功
	304 重定向 缓存
	403 没有权限
	404 请求的文件没有找到
	503 服务器宕机
	504 网关超时
> 3.statusText	由服务器发过来的响应状态语句

> 4.responseText	获取 服务端的响应文本


####XML对象的常用方法
######第二步：初始化请求
1.open()		初始化 HTTP 请求参数，例如 URL 和 HTTP 方法，但是并不发送请求。<br>
	open(method, url, async, username, password)
######第三步： 发送请求
>1. send()		发送 HTTP 请求，使用传递给 open() 方法的参数，以及传递给该方法的可选请求体。		
>3. setRequestHeader()   向一个打开但未发送的请求设置或添加一个 HTTP 请求。POST
>4. getAllResponseHeaders()	把 HTTP 响应头部作为未解析的字符串返回。
>5. getResponseHeader()		返回指定的 HTTP 响应头部的值。其参数是要返回的 HTTP 响应头部的名称

####XML对象的常用事件
######第四步：事件判断   接收请求内容
onreadystatechange  每次 readyState 属性改变的时候调用的事件句柄函数

####GET请求和POST请求
>1. get:   将参数拼接到url上
>2. post:  将参数拼接到send()中		<br>	
--xhr.setRequestHeader("content-type","application/x-www-form-urlencoded");

	区别： 
		get从服务器获取数据，post向数据库提交数据。
		get传输的数据较小，一般不大于2kb，post传输的数据量较大。
		get安全性较低，post安全性较高，但是get执行效率高。
		get请求时，服务器使用Request.QueryString获取信息，post请求服务器使用Request.Form
		操作数据的增删改查时，get用于查询，post用于修改删除添加。

####练习：
>请求远程API 数据完成1.png  的效果 <br>
huangsir.top/index1.php
huangsir.top/index1.php?content=v2/movie/coming_soon

http://api.douban.com/v2/movie/coming_soon 跨域无法获取
