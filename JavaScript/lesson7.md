##<center>JavaScript_07
####创建相同属性和方法的对象
>1. 原始方法创建对象
	
	-- 代码重复 
	var obj1 = {}
	obj1.name = "小红";
	obj1.age = 12;
	var obj2 = {}
	obj1.name = "小黑";
	obj1.age = 13;
>2. 工厂模式
	
	function createUser(name,age){
	var obj = new Object();//创建对象      			--获取原料
	obj.name=name;         //给对象添加属性和方法  	--加工
	obj.age=age;
	obj.say = function(){console.log("能吃能睡")}
	return obj;			  //返回对象 				--出厂
	}
	var obj1 = createUser('小红',12);
	var obj2 = createUser('小黑',13); 
>3. 构造函数 <font  color="green">this --实例化本构造函数的对象   (本对象)</font>
	
	function Createuser(name,age){
	this.name=name;
	this.age=age;
	this.say = function(){console.log("能吃能睡")}
	//隐式返回 this
	}
	var obj1 = new Createuser('小红',12);
	var obj2 = new Createuser('小黑',13); 
####构造函数  
	1.别的语言中(class)
	2.ECMA定义：
		Constructor is a function that creates and initializes the newly created object.
		构造函数是用来新建同时初始化一个新对象的函数
####构造函数特点
>1.每个对象都有与之相对应的构造函数   
	
	var arr = new Array();
>2.一个构造函数可以有多个对象 
	
	var arr1 = new Array();
	var arr2 = new Array()		 
####构造函数判断 
	var o = {};var a = [];
	document.write(o instanceof Object);
<font color="color">注意：不能用来判断数字和字符串</font>
####构造函数的获取
	constructor 属性 -- 所有的对象都具有constructor  获取对象的构造函数
	function demo(){}; demo的构造函数：demo.constructor;
	var num = 10;     num 的构造函数   num.constructor
######数字调用constructor 错误 
	使用10..constructor 
	使用(10).constructor  
####JavaScript中的特殊情况  
	Number数值 在new的时候是一个Object对象但是正常使用是number。
####构造函数与普通函数
#####普通函数
>不需要用new关键字调用<br>
可以用return语句返回值<br>
函数内部不建议使用this关键字<br>  
函数命名以驼峰方式，首字母小写<br>
#####构造函数----涉及更加的底层
>用new关键字调用<br>
函数内部可以使用this关键字<br>
默认不用return返回值(隐式返回this)<br>
函数命名建议首字母大写，与普通函数区分开<br>
普通函数可以是构造函数的一个方法<br>
####对象的引用比较
	var bool1 = new Boolean(1);
	var bool2 = new Boolean(1);
	console.log(bool1 == bool2);  //返回false

	var arr1 = [1,2,3];
	var arr2 = [1,2,3];
	console.log(arr1 == arr2);   //返回false  
>原始类型的数据比较  只是值的比较<br>
对象类型的数据比较  需要值和引用地址都相同
####原型
	使用构造函数每创建一次对象就产生一份方法(属性)
	资源的占用较大
>1. 对象的原型prototype让公用的方法或者属性在内存中只存在一份
>2. 每个函数在创建的时候都自动添加了prototype属性，这就是函数的原型
>3. prototype是函数的内置属性
>4. 原型也是对象
>5. 原型是添加在构造函数下面的
####
	通过new Array() 创建的对象的原型是Array.prototype 
	通过new Date()  创建的对象的原型是Date.prototype
	...
	通过直接量设置的对象  var a = true;
	原型是a.constructor.prototype 
####原型中的属性(方法)  与 对象中的属性(方法)区别
	类似于：class(原型属性)  style(普通属性)
	对象属性的优先级 >  原型的属性优先级
	[1,2,3].index = "index";
	Array.prototype.index = "myindex";
	console.log([1,2,3].index);
####将构造函数中的方法写在原型中
	function Createuser(name,age){
	this.name=name;
	this.age=age;
	}
	Createuser.prototype.say = function(){console.log("能吃能睡")}
	var obj1 = new Createuser('小红',12);	
	var obj2 = new Createuser('小黑',13); 
	console.log(obj1.say == obj2.say);//返回true

####使用 Object.create()创建对象 传入对象原型
	function Demo(){this.name="小毛"}  
	Demo.prototype.add=function(){}
	var index = Object.create(Demo.prototype);
	传入null,创建一个没有原型链的对象
	
	参数二：传入对象描述
	var obj = Object.create(null,{
			size:{
				value:10
			}
		})
####获取对象的原型   
	ECMA5新方法:   Object.getPrototypeOf({});
####原型中的this
	(本对象)   调用此方法的对象
####原型链
	1.JavaScritp引擎在访问对象的属性时，如果在对象本身中没有找到，则会去原型链中查找，如果找到，直接返回值，如果整个链都遍历且没有找到属性，则返回undefined.
####自定义原型继承
	Weapon->(sword gun knife)->(武器的展示 描述)
####关于对象的 __proto__
	对象的内置属性，不是标准的属性。IE不支持。
####判断自有属性  --hasOwnProperty  返回true | false	
	构造函数内存在的属性或者方法属性自有属性
	在原型上添加的不属于自有属性		
	if (list.hasOwnProperty(i)) {   //获取一组li  遍历
			document.write(list[i]);
		}