##<center>JavaScript_10
####日期对象
#####获取日期对象 
	var date = new Date();   --没有参数即获取当前的时间对象
####日期对象的方法
>1. 获取当前的年   	date.getYear();
>2. 获取当前的公元年  date.getFullYear();
>3. 获取当前的月   	date.getMonth()+1;
>4. 获取当前的日    	date.getDate();
>5. 获取当前的星期	date.getDay();
>6. 获取当前的时		date.getHours();
>7. 获取当前的分		date.getMinutes();
>8. 获取当前的秒		date.getSeconds();
>9. 获取当前的毫秒	date.getMilliseconds();
>10. 获取当前时间戳	date.getTime();
>11. 获取标准时区的时间年  date.getUTCFullYear();
>12. 获取标准时区的日	     date.getUTCDate();
>13. 获取标准时区的小时 	 date.getUTCHours();
>14. 标准时区的日期时间字符串 date.toUTCString();

####时间戳的认识 
	从Unix元年至今的毫秒数   
	其他语言时间戳(unix元年至今的秒数)
Unix 元年： 1970年一月一日0点0分0秒0毫秒（unix->linux）
>1. 很多编程语言起源于UNIX系统，而UNIX系统认为1970年1月1日0点是时间纪元，所以我们常说的UNIX时间戳是以1970年1月1日0点为计时起点时间的
>2. C语言的产生
>3. 时间戳应用：法律效力 档案管理 数据库存储

####将时间戳转换为标准格式
	var  timer = 24324343;   		//从数据库取出的时间戳
	var time = new Date(timer);
	var year = time.getFullYear(); //通过时间戳获取年
	var day = time.getDay();
####设置时间   
	date.setTime(14480907809);  使用js设置cookie的保质期


####全局对象  
	console.log(this);
######全局对象的常用方法
>1. isNaN();
>2. parseInt();
>3. parseFloat();
>4. Number();
>5. String();  	...等相关强制转换函数
>6. eval();		解析执行字符串
>7. escape()  对字符串进行编码，可以在所有的计算机上读取该字符串
>8. unescape();  字符串解码
>9. encodeURI();  将字符串作为URI进行编码。
        
		--防止特殊字符造成URI的传递错误，一般用于页面跳转
		不编码的字符82个： !#@$~&*_+-,.:;=?()/0-9a-zA-Z
> 10.decodeURI(); 对encodeURI()进行解码 <br>
> 11.encodeURIComponent();将字符串作为URI进行编码
	
	防止URI参数中特殊字符串造成参数读取错误 用来传递参数
	不编码的字符有71个
	!’()*-._~0-9A-Za-z
> 12.decodeURIComponent();解码encodeURIComponent

####错误处理
######常见错误    
>1. 未经定义的变量
>1. 未区分大小写
>1. 不匹配的大括号或者圆括号
>1. 赋值和相等（=    ==）  --逻辑错误
>1. 字符串的拼接+  ....细节
####错误类型  	
	SyntaxError   		语法错误
	ReferenceError   	引用错误(变量未定义)
	RangeError 			超出范围   
		array.length=-1;
		123..toPrecision(22)
	TypeError		类型使用错误  
		null.a();
		o.floor(); --object
	URIError   EvalError  Error  不常见
####处理方法
>1. 避免错误
>2. try..catch语句 （可以相互嵌套）
	
		try {
			throw new Error('错');
			console.log('aaa');
			throw new SyntaxError('错了');	//抛出错误
		} catch (e) {
			console.log(e);
		}
> 3.finally 字句    
	
	try{    }catch{  }finally{  } 
> 4.调试
	
	控制台source找到文件使用debugger调试
	使用console.log（）控制台输出调试
####JavaScript学习内容
    ECMAScript  核心语法
    DOM 		文档对象模型(html5给js更大的权限接口)
	BOM			浏览器对象模型
####JavaScript对象
	1.内置对象
	2.自定义对象(自定义构造函数)
	3.宿主对象
		1. BOM
		2. DOM
####事件
######事件的绑定方法	
>1. 标准方式   
	
	一个dom元素同一个事件可以绑定多个 
			addEventListener(Event,fn)   (非IE)
			attachEvent(Event,fn);		 (IE)
			兼容绑定
			if(btn.addEventListener){
				btn.addEventListener('click',function(){alert(1)});
				btn.addEventListener('click',function(){alert(2)});
			}else{
				btn.attachEvent('onclick',function(){});
			}
> 2.把事件作为元素的方法  

	同一个事件只能绑定一次，后者会覆盖前者
	dom.onclick=fn;
		
> 3.把事件作为标签的内部属性
	
	<button onclick=”code..”></button>
	
####解除事件绑定
	标准方式解除	--需要使用函数名，匿名函数不能解除
	removeEventListener(event,fn);  (非IE)
	detachEvent(Event,fn);  (IE)		

	其他方式解除绑定    重新定义事件
	dom.onclick=function(){}
####自定义绑定事件函数
		function bindEvent(dom, event, fn) {
			if (dom.addEventListener) {
				dom.addEventListener(event, fn);
			} else if (dom.attachEvent) {
				dom.attachEvent("on"+event, fn);
			} else {
				alert("您的设备不支持事件");
			}
		}
####自定义解除事件函数
		function unbindEvent(dom, event, fn) {
			if (dom.removeEventListener) {
				dom.removeEventListener(event, fn);
			} else if (dom.detachEvent) {
				dom.detachEvent("on"+event, fn);
			} else {
				alert("您的设备不支持事件");
			}
		}

----
#####作业

>1. 实例： 时钟效果   .play()  
>1. 实例： (做一个电子表)
>1. 实例：给一个盒子绑定点击事件（要求：背景颜色随机变化，字体随机大小(12-30)）
>1. 实例：尝试给一组li绑定点击事件(要求：使用for循环绑定，背景变红)

