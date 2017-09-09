##<center>JavaScript_11
####this的使用
	1.给一组元素绑定事件
		for(var i = 0;i<list.length;i++){
		lis[i].onclick=function(){
		console.log(i);
		this.style.backgroundColor=”red”;
		}
		}
	2. 在元素内部通过事件属性使用
		<button onclick='change(this)'></button>
		function change(ob){ob.style.color='red'}
####事件列表
######1.鼠标事件
> 1.onclick    		单击<br>
> 2.ondblclick 		双击<br>
> 3.oncontextmenu	右击     --return false 阻止系统菜单弹出<br>

	自定义右键菜单
	1.event对象
	2.client.X   client.Y
	3.window.innerWidth   window.innerHeight
	4.document.documentElement.clientWidth;
	5.document.documentElement.clientHeiht;
> 4.onmouseover		鼠标滑上元素   --导航条<br>
> 5.onmouseout		鼠标移出元素	<br>
> 6.onmousedown		鼠标按下<br>
	
	box.onmousedown=function(en){
	var env = en || window.event;
	switch (env.button){
	console.log(env.button);    } }
> 7.onmouseup 		鼠标抬起	<br>
> 8.onmousemove		鼠标移动
	
	box.onmousemove=function(en){
		var env = en || window.event;
	//获取鼠标的坐标
		var X = env.clientX;
		var Y = env.clientY;
	//获取box的位置  --offsetLeft相对于定位的父级
		var left  = this.offsetLeft;
		var top  = this.offsetTop;
	//得到鼠标在box上的位置
		var x = X-left;  var y = Y-top;
		}
######2. 键盘事件
>onkeydown		键盘按下 <br>
>onkeyup		键盘抬起<br>
>onkeypress		键盘按下---可打印的(可见的)
	
	document.onkeydown=function(en){
	var e = en || window.event;
	var char = String.fromCharCode(e.keyCode);
	返回ASCII表的字母(大写)
	}


######3. 文档事件
>onload			文档中的一切加载完成（可以使代码放在元素前面）	<br>
>onunload		文档关闭的时候(w3c里有标准但是浏览器不支持)	<br>
>onbeforeunload 	文档关闭之前  

	body window的兼容和冲突  
	window.onload=function(){
	alert(1);
	};
	
	浏览器支持较差
	window.onbeforeunload = function(){
		return "别走";   //页面刷新的时候提醒
	}
######4. 表单事件
>1.  onsubmit --- 提交

	document.myForm.onsubmit=function(){
	return false;   不提交
	//return true;  提交
	}
>1. onreset --- 重置
	
	doucment.myform.onreset=function(){
		return false ;     不重置
		return true;		重置
	}
>1. onfocus -- 获取焦点
	
	inp.onfocus=function(){
	this.style.backgroundColor='blue';
	}
>1. onblur ---失去焦点

	使用onblur验证表单（提高用户体验）
	
>1. onchange ---内容发生改变(失去焦点)
	
	input.onchange = function(){
		document.getElementById('box').innerHTML = this.value;
	}
	实例：地址联动   
>1. onselect  ---当内容被选择(表单)
	
	textarea.onselect = function(){
			alert('选中了');
		}
######5. 图片事件
>1. onload   ---加载完成
	
	<img src=”1.jpg” onload=”alert()”>
>2. onerror  ---加载失败	
	
	img.onerror = function(){this.src = "error.jpg";}
>3. onabort  ---加载中断

---
####作业：
>1. 完成图层的拖拽
>1. 使用css和js两种方法写出横向导航(二级菜单)
>1. 轮播图
>1. 打灰机实例
>1. 银行卡补全实例
