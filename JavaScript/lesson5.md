##<center>Javascript_05        
###数组
    相关概念：
>1. 数组是值的有序集合。   
>1. 每个值叫做一个元素  
>1. 每个元素在数组中有一个位置，以数字表示。
<font color="red">称为索引(下标)</font>。
####特点 
  	数组的元素可以是任何类型
  	数组索引从0开始，最大为2^32-2  4294967294个元素
####创建数组
>1. 使用数组直接量[]   
	var arr = [1,2,3,];
>1. 使用构造函数       
	var arr = new Array(10);10个元素 <br>
    var arr = new Array('a','b','c'); 
####数组的长度
	arr.length;    
	length属性只计算非负整数的索引
####数组元素的访问和修改：
>1. 使用[]
>
>1. 数字类型的字符串 也可以访问数组元素
>
> 小实例：<font color="red">尝试将数组中的内容放入新的数组中</font>
####稀疏数组
	稀疏数组就是不连续索引的数组
>1. var arr = new Array(3); -- 是稀疏数组
>1. var arr = [,,]; -- 是稀疏数组
>1. var arr = [1,2];arr[10]=100; -- 是稀疏数组	
>1. 使用delete删除一个元素  得到稀疏数组
>
>小实例： <font color="red">尝试将稀疏数组变成不稀疏</font>
####数组元素的添加：  		
>1. 为新索引赋值 arr[4]=2;
>1. 利用数组长度在数组尾部插入新元素 arr[arr.length]=5;
>1. push()  在尾部加入新元素 arr.push(‘abc’);
>1. unshift()在前面加入一个新元素  arr.unshift(‘abc’);
####数组的删除：
>1. 删除数组后面的一个元素 delete()不推荐--产生稀疏数组
>1. pop() 删除数组最后一个元素 arr.pop();
>1. shift() 删除数组第一个元素 arr.shift();
>
>练习题：<font color="red">自定义一个函数验证元素是否在数组中</font>
####判断是否数组  
	typeof []; 无法进行判断
>ESMA5定义新的方法用来判断是否数组：   Array.isArray([]);
####搜索数组是否具有的元素
	arr.indexOf(); 
	 	如果存在返回元素位置      
		如果不存在返回-1
####数组的遍历：
>1. 使用for循环遍历 
	for（var i = 0; i < arr.length;i++）{
		console.log(arr[i]);
	}

>2. 使用for/in循环 
	for(var i in arr){
		console.log(arr[i]);
		}
>3. <font color="red">注意：遍历稀疏数组 和 特殊下标数组时的区别</font>
>4. 使用forEach();  传入匿名函数  
>  <font color="red">低版本IE不支持</font>


---
####数组的方法：
>1. join()把数组的元素拼接成字符串
		var message = arr.join(‘，’);    
>2. concat() 合并多个数组
####
	var message = arr.concat([12,43],[4,35,3]);
	var message = arr.concat(1,2,3);
	var message = arr.concat(1,2,[4,,5,[6,,7]]);
>3. slice()  截取数组中的一部分(不破坏原数组)，返回新的数组
####	
	var arr = list.slice(2);  取出从下标2到后面的所有元素
	var arr = list.slice(2,4); 取出从下标2到下标4(不含4)的元素>
>4. splice() 删除、替换、添加、 破坏原数组 返回删除的内容
####
	var new_arr = list.splice(2);   下标2以后的元素
	var new_arr = list.splice(2,2); 下标2以后的两个元素
	1. 在指定位置添加新的元素
		var arr = [3,454,435,343]; 
		arr.splice(2,0,’abc’);
		在435的位置前添加一个abc
	4. 替换指定位置的元素
		var arr=[1,2,3,4];arr.splice(2,1,’abc’);
		将3替换成abc;
实例：<font color="red">使用 splice()方法处理稀疏数组</font>

>5. reverse()  数组反转  改变原数组

>6. sort();  数组排序，必须使用排序函数 list=[1,334,32,324];
	list.sort(function(a,b){return a-b;});
>7. toString() 把数组转换为字符串
>
>8. toLocaleString()把数组转换为本地字符串(不常用)

---
####ECMA5中数组的新方法
> filter() 创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素
	
	var arr = [2,3,4,5,6];
	var newArr = arr.filter(function(v){return v>3});
> every()方法用于检测数组所有元素是否都符合指定条件 不改变原数组
	
	var arr = [1,2,3];
	var boo = arr.every(function(v){return v>4});
> map()  方法按照原始数组元素顺序依次处理元素
	
	var arr = [1,4,9,16];
	var newArr = arr.map(Math.sqrt);
	var newArr = arr.map(function(v){return v*v});
> some() 方法用于检测数组中的元素是否满足指定条件
	
	var arr = [1,2,3,4];
	var boo = arr.some(function(v){
		return v>3;
	})

---
####多维数组
	
	var arr = [[1,2,3,4,5],[1,2,3,4,5]];
####用[ ][ ]方式访问多维数组内的元素

####类数组对象
>有数组的一些特性。但不是数组.也不具有数组的方法
####
>1.arguments 

	function demo(){
		console.log(arguments);arguments.length;
	}
	demo(1,2,3,4,45,5); 
>2.Elementcollection 元素集合

	var uls = document.getElementById(‘nav’);
	var lis = ul.getElementsByTagName(‘li’); 获取集合
	console.log(lis);console.log(lis.length);
####元素集合的遍历
	1.使用for遍历
	2.使用for in遍历 (会将不需要的内容遍历出来)

####作为数组使用的字符串
	
	var a = "aadfadf";  
	console.log(a[0]);
	a[0]="dd";    只能访问 无法进行修改 
######练习：  
>1. (checkbox)全选 全不选  反选
>2. 使用函数自定义数组的其他方法：
	
	数组去重(删除数组中重复的元素) **重点**
	求数组元素的和
	删除数组中指定的元素


练习：

自定义求数组最大值的函数

自定义求数组最小值的函数

<font color="red">冒泡排序