##<center>JavaScript_06
####对象
>定义：
>
>1. 世间万物都可以用对象表示
>2. 基于对象的编程语言中，用对象给真实的事物建模

#####组成：属性  方法

---

####Javascript对象介绍：
>1. 对象是javascript的一种数据类型
>2. 对象是一种复合值   它将很多值聚合在一起，可通过名字访问这些值。
>3. 对象也可以看做属性的无序集合。每个属性都是  名：值   对。
>4. 属性名是字符串，我们可以把对象看成是从字符串到值的映射。
>5. 对象的其他叫法：散列(hash)  散列表(hashtable) 字典(direction) 关联数组(associative array)

####JavaScript对象分类
>1. 内置对象   如：  数组   函数  日期  正则  等...
>2. 宿主对象   htmlElement对象是Js的宿主浏览器的对象<br>
	1.浏览器中  window对象  (BOM 和 DOM)<br>
	2.Node中   global 对象
>3. 自定义对象  用户自定义的对象

####对象的创建
>1. 使用对象直接量

	console.log({});
	console.log({list:[10,23,243]});
	var oop = {name:’大毛’,list:[1,2,3],getName:function(){}};
>2. 通过构造函数(new)创建对象  
	
	var oop = new Array(); 
	var oop = new Function();
	var oop = new Object();
	console.log(oop);
>3. 通过Object.create();  --ECMA5定义的方法
 
	--传入原型
	--不继承构造函数和原型中的方法属性
	var o = Object.create();
####对象属性值的获取 设置 修改  
>1.  . 运算符    
	ECMA老版本.for 或者.of 是非法  ECMA5放宽了限制，但是不建议使用
>2.   [ ] 运算符  
	
	var oop={name:’lili’,age:12}
	document.write(oop.name);
	document.write(oop[‘name’]);
####区别
	当属性名为变量时 只能使用[ ]
####属性修改或设置
 		oop.name="abc";
 		oop['name']="abc";
####对象方法的调用
	var oop = {name:'aa',age:12,getInfo:function(a){
		document.write(a);return 100;}
	}
	oop.getInfo();  
	oop.getInfo('aa');
####全局对象window
	预定义的对象 作用域链的顶层
	用户定义的变量是全局对象的属性
	用户定义的函数是全局对象的方法
####对象中的this 
	调用本方法的对象
####删除对象属性或方法   
  	delete oop.age; 
 	delete getInfo;
####对象属性的检测  
> 使用关键字 in 
 	document.write('name' in o);
####对象的直接量书写方式  --json格式
 	var oop = {       
		name:’xx’,
		age:13,
		getInfo:function(){},
		"if":[],    				//关键字使用引号
		"color":'黑色',
		"cpu-i5":1500   			//带-使用引号
		}
####对象的遍历
	var o = {x:1,y:2,z:3}
>1. 使用 for in 遍历出对象的属性名<br> 
	for(var i in o){document.write(i)}
>2. 使用Object.keys(o) 将属性名遍历到数组中
####数据结构的认识
	https://developers.douban.com/    远程数据API
	http://api.douban.com/v2/movie/in_theaters
	http://api.douban.com//v2/movie/coming_soon