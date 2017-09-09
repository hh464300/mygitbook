#<center>JavaScript_04
##函数
>####函数是一段在一起，可以做某件事的程序。
###优点：控制程序设计的复杂性 
>1. 提高软件的开发可靠性
>1. 提高软件的开发效率
>1. 提高软件的可维护性
>1. 提高程序的重用性
###JavaScript定义函数的方式 
>1. function 关键字  function demo(){ code..}
>1. 匿名函数  var demo = function(){}
>1. Function 构造函数   （不推荐使用）
	var demo = new Function(‘a’,’b’,”console.log(a+b)”);
###调用方式区别
>1. 函数声明的提前
>1. 匿名函数无法提前使用
###函数名
	函数名可由开发者自行定义
	与变量命名规则相同(描述性强，简洁)。
###函数参数
>1. 多个参数使用,分割
>1. 形参
>1. 实参
####参数特点 
>1. 当实参数量>形参数量(省略)  
>2. 当实参数量<形参数量(undefined)
>3. 通过if(n1 === undefined){}设置参数的默认值
>4. 通过实参对象arguments将获取的参数组成一个数组（arguments在严格模式下是一个关键字）
>
>小实例： <font color="red">配合循环计算所有参数的和。</font>
####函数的返回值
使用关键字return <br> 
>1. 结束函数 
>2. 可以返回值 也可以没有返回值
####函数的引用和调用
>1. 调用：在函数名后面加上();
>2. 引用：使用函数名；
##函数小实例：
>1. 实例1：<font color="red">使用函数求绝对值，求平方。</font>
>1. 实例2：<font color="red">计算两点之间的距离</font>
>1. 实例3：<font color="red">将出生日期判断生肖改成函数</font>

##JavaScript变量的作用域  
>1. 全局变量--定义在函数的外部。
>1. 局部变量--定义在函数内部 
>1. 不使用var时变成全局变量，但是需要执行函数才能使用内部定义的变量
>1. 严格模式下，不支持。不推荐使用。（避免全局变量污染）
####注意：函数外for循环等定义的变量也是全局变量。

###函数的调用
>1.  函数内调用别的函数 
>1. 使用参数调用 --回调函数
>1. 函数内调用自己  --递归函数

	function demo(n){
		if(n<0){
			return;
		}else{
			document.write(n+"<br>");
			demo(n-1);
		}
	}   
	function demo(n){
       if(n<0){
		return;
		}else{
		document.write(n+"<br>");
		demo(n-1);
		document.write(n+"<br>");
		}
	}
<font color="red">使用debugger调试 打开F12</font>

####求阶乘  
1. function demo(n){if(n<=1){return n;} return n*demo(n-1);}
2. for();


---
> 练习： 简易计算器
