##<center>JavaScript_12
######轮播图
######选项卡
####1. Scroll事件  
	元素内部内容的滚动 --内容向左滚动， 滚动条向右
	1.有滚动条的元素
	box.onscroll = function(){
	var left = box.scrollLeft;   
	var top = box.scrollTop;		
	}
	2.给window绑定scroll事件
	var top=document.body.scrollTop  ||  document.documentElement.scrollTop;
####2.Resize事件
	绑定给window  窗口尺寸发生改变
	获取窗口大小 	
	w  = window.innerWidth;
	h = window.innerHeight;
	window.onresize = function(){
		var w = window.innerWidth;
		var h = window.innerHeight;
	}
####3. 新增事件
* oninput 事件在 &lt;input&gt; 或 &lt;textarea&gt; 元素的值发生改变时触发。
	立即触发
	低版本IE不支持
* onsearch  针对type=”search” 回车发送的时候触发  IE火狐不支持
* onfocusin  通过父元素判断子元素是否获取焦点 
	--需要使用addEventListener()
* onfocusout  通过父元素判断子元素是否失去焦点 
--需要使用addEventListener()
####4. 剪切板事件
*  oncopy() 用户拷贝元素内容时触发
* oncut() 用户剪切元素内容时触发
* onpaste() 用户粘贴内容时触发  
####5.过渡/动画事件  (标准绑定)
* animationend  该事件在 CSS 动画结束播放时触发
* animationiteration 事件在重复播放时触发
* animationstart  动画开始时触发
* transitionend 过渡完成以后触发
####6. 其他
* onwheel     鼠标滚动的时候触发 (onmousewheel 已废弃)


###event对象
>1. cancelBubble	--阻止冒泡  值等于true取消默认动作
	<pre>
	var e = en || window.event;
	if(e.stopPropagation){
		e.stopPropagation();
	}else{e.cancelBubble=true}
	</pre>
>2. target  返回触发事件的元素
	Console.log(e.target);
3. stopPropagation()		阻止事件冒泡    IE9 以下不兼容

>4. 阻止js默认事件   (a,contextmenu)
	<pre>
	a.onclick=function(en){
	var e = en || window.event;
		alert('ok');
		e.preventDefault();
		} 
	</pre>  
>5. 返回事件类型
	<pre>
	div.onclick=show;
	function show(en){var e = en || window.event;
	alert(e.type);
	}
	</pre>
>6. 返回触发事件的时间戳
	<pre>
	document.onclick = function(e){ 
	var e = e || window.event;
	Console.log(e.timeStamp);
	}
	</pre>

---
####BOM 浏览器对象模型
	--  Borwser Object Model 
    --  用来描述浏览器相关信息的几个对象
	--  其中代表浏览器窗口的window对象是BOM的顶层对象，其他对象都是该对象的子对象。

####BOM
>1. Window    整个窗口(顶层)
>2. Location  url信息
>3. History   历史记录
>4. Screen    屏幕相关
>5. Navigator 浏览器版本及客户机信息
 

####Window 概述：
>1. window是客户端JavaScript的全局对象 
>1. 它表示web浏览器的一个窗口或窗体，并且用标识符window来引用

	是所有客户端javascript特性和API的主要接入点
	Window包含  location history screen navigator  document
####1. window
*  innerHeight		返回窗口的文档显示区高度   IE9以下不兼容
*  innerWidth		返回窗口的文档显示区宽度  	IE9以下不兼容
	
	解决方法<br>
	<pre>
	document.write('视口的宽 : '+document.documentElement.offsetWidth+"<br>");
	document.write('视口的高 : '+document.documentElement.clientHeight+"<br>");
	</pre>
* outerWidth  返回窗口外部宽度  IE9以下不兼容  
* outerHeigh  返回窗口外部高度  IE9以下不兼容  
	
	解决方法   --暂无
* 弹窗  alert()  无返回值 confirm()  有返回值  prompt()   有返回值  

* setInterval()    clearInterval()

* setTimeout()	clearTimeout()

* print()  		window.print();

* scrollTo(x,y)    将内容滚动到指定坐标

* scrollBy()		按照指定像素滚动   ---回到顶部

 
*  <font color="red"> moveTo(x,y)    window.moveTo()仅IE</font>


* <font color="red"> moveBy()		window.moveBy()仅IE</font>

* <font color="red"> resizeTo()		将窗口大小调整到指定的宽度和高度      仅IE</font>

* <font color="red"> resizeBy()		按照指定像素调整窗口大小              仅IE</font>

####2. location
表示该窗口中当前显示的文档的URL
并定义了方法来使窗口载入新的文档
######属性
* href 		 设置或返回当前的URL协议
* protocol   设置或返回当前URL的协议
* host		 设置或返回主机名和当前URL的端口号
* hostname   设置或返回当前URL的主机名
* port 		 设置或返回当前URL的端口号<br>
	--虚拟端口</br>
	--物理端口
* pathname	 设置或返回当前URL的路径部分
* hash 		 设置或返回从#开始的锚
* search	 设置或返回从？开始的URL查询部分
	
	
			
######方法
* reload();   --重新加载当前文档 location.reload();
* assign();  --加载新的文档      location.assign(“http://www.baidu.com”);
* replace(); --替换当前文档  location.replace(“http://www.baidu.com”);

---
>1. 自定义一个超链接
>1. 定时刷新





####实例：
* 页面滚动100px后，导航条变成固定定位
* 放大镜效果
* Top^回到顶部效果