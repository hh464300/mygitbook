##<center>第十一天
####Css3颜色的渐变
######线性渐变   
	background-image:linear-gradient（to bottom,#fff,#333）;
	background-image:linear-gradient（60deg,#fff,#333）;
	background-image:linear-gradient（to bottom,#fff 10%,#333 100%）;
####径向渐变 
	background-image:radial-gradient(#fff,#333);
	background-image:radial-gradient(at left,#fff,#333);
	background-image:radial-gradient(at 100px 100px,#fff,#333);
	background-image:radial-gradient(200px 100px at 50% 60%,#fff,#333);	
		200px 100px 代表水平和垂直的半径
		50% 60%     代表圆点的位置  -webkit-方法不支持
	background-image:radial-gradient(100px circle at 30% 40%,#fff, #333);
		100px 代表圆的半径(渐变完成的半径)
	background-image:radial-gradient(100px 120px ellipse at 50% 60%,#fff,#333);
		100px 120px 水平和垂直所占的距离
		50% 60%     代表圆点的位置  -webkit-方法不支持
####重复渐变：

	线性：background-image:repeating-linear-gradient(to right,orange 100px, green 200px);100px 200
		px 颜色的区域。注意不要相同
	径向：background-image:repeating-radial-gradient(orange 100px, green 200px);
<font color="red">低版本IE渐变的兼容
filter:progid:DXImageTransform.Microsoft.Gradient(GradientType=0,startColorStr=orange,endColorStr=green)  0代表横向，1代表纵向</font>

---

####Css3边框属性
>1. border:
>1. border-width:
>1. border-color:
>1. border-style:    <以上四种又分别有border-left-,border-right-.......>
>1. border-radius:  盒子圆角
>1. border-top-left-radius:  左上角
>1. border-top-right-radius: 右上角
>1. border-bottom-left-radius: 左下角
>1. border-bottom-right-radius:右下角
>1. 同时设置多个角度
		<div style="border-radius:20px 30px 40px 100px/10px 15px 20px 50px"></div>
####盒子阴影 border-shadow
	border-shadow:3px 3px #ccc;  参数分别是水平平移，垂直平移，颜色
	使用负值改变影响所在边
	border-shadow:-3px -3px 3px  #ccc;
	border-shadow:3px 3px 3px #ccc   左 下  模糊度  颜色
	border-shadow:3px 3px 3px 10px  #ccc 左 下 模糊度 向外偏移量 颜色
	内阴影
	border-shadow:3px 3px 3px #ccc inset; 内阴影。如果不加则为外阴影(默认)
	使用逗号分隔可以设置多层阴影
####基础选择器
>1. 元素选择器  
>1. class  
>1. id  
>1. *  
>1. 关联选择器（selecter selecter）
####层次选择器
>1. E F         E下面所有的子元素F(包括后代元素)
>1. E > F       E 下面所有的子元素F(不包括后代元素)
>1. E + F		E后面的第一个兄弟元素F(不包括后代元素) 
>1. E ~ F		E后面的所有兄弟元素F(不包括后代元素)
####属性选择器
>1. E[attr]				选择具有attr属性的E元素
>1. E[attr=‘val’]		选择具有attr属性且值等于val的E元素
>1. E[attr~=’val’]	选择具有attr属性且(值等val或者多个值其中一个为val)的元素E.
>1. E[attr^=’val’]	选择具有attr属性且属性值以val开头的E元素
>1. E[attr$=’val’]	选择具有attr属性且属性值以val结尾的E元素
>1. E[attr*=’val’]	选择具有attr属性且属性值包含val的E元素
>1. E[attr|=’val’]	选择具有attr属性且属性值（等于val或者以val-连接）的E元素    多个属性值需要符合条件的在最前面

####伪类选择器
######动态伪类选择器
<font color="orange">
>1. E:link  设置超链接a在未被访问前的样式(a)
>1. E:hover 设置元素在其鼠标悬停时的样式。 
>1. E:active 鼠标点击时的样式
>1. E:visited设置超链接a在其链接地址已被访问过时的样式。(a)  </font>
>1. E:focus  获取焦点时的样式(input)
######目标伪类选择器
>1. E:target 当url指向具有某个锚点的E元素时的样式。
	
	#demo:target{color:red;}
	<div id="demo">Lorem </div>   <a href="#demo">变红</a>
######语言伪类选择器	
>1. E:lang(en); 通用属性lang（）语言为en的E元素的样式
>1. lang 属性在以下标签中无效：base, br, frame, frameset, hr, iframe, param 以及 script

######UI元素伪类选择器（form内元素）
>1. E:checked  元素E选中时的样式(input type为radio或checkbox)
>1. E:enabled  匹配可用状态的表单元素E
>1. E:disabled 匹配禁用状态的表单元素E
####结构伪类选择器
>1. E:root  	 匹配根元素E。在html中根元素只有一个html
>1. E:first-child 匹配父元素第一个元素E（E必须是第一个）
>1. E:last-child  匹配父元素最后一个元素E（E必须是最后一个）
>1. E:nth-child(n)匹配父元素第n个元素E（E必须是第n个）
>1. E:nth-last-child(n) 倒着数第n个元素E（倒着的第n个元素必须是E）
>1. E:first-of-type  匹配父元素第一个元素E（E不一定是第一个）
>1. E:last-of-type   匹配父元素最后一个元素E（E不一定是最后一个）
>1. E:nth-of-type(n) 匹配父元素第n个元素E（E不一定是第n个子元素） 2n  2n+1  odd  even
>1. E:nth-last-of-type(n) 倒着匹配父元素第n个元素E（E不一定是第n个子元素）2n 2n+1  odd  even
>1. E:only-child 匹配父元素仅有的一个子元素E（只有这一个E，别的元素没有）
>1. E:only-of-type 匹配父元素一个子元素E（父元素只有一个E,可以有别的元素）
>1. E:empty 匹配没有任何子元素(包括text节点)的元素E
######否定伪类选择器
>1. E:not(s) 匹配不含有s选择符的元素E
	 ul li:not(.item)
	 ul li:not(:first-child)
######伪元素选择器
>1. E:first-letter/E::first-letter  元素E的第一个字符的样式
>1. E:first-line/E::first-line 		元素E的第一行字符的样式
>1. E:before/E::before				E元素的前面。(配合content属性)
>1. E:after/E::after				E元素的后面。(配合content属性)

		三角箭头 清除浮动
######E::placeholder			
	选择input中的placeholder  兼容较差不常用
	<input type=”text” placeholder=”占位符”>
	Input::-webkit-input-placeholder{color:red;}
	Input:-ms-input-placeholder{color:red}
	Input::-moz-placeholder{color:red}
######E::selection			
	设置对象被选择时的样式（文字）
	只能定义被选择内容的background，color属性值
	p::selection{
		background:red;
		color:#ccc;
	}
	p::-moz-selection{
			background:yellow;
		}
######特殊属性  文本选中
>1. userselect 	    -webkit-user-select:none | all | text

---
####边框图片
<font color="red">
>1. border-image:			边框图片(组合属性）
>1. border-image-source:	url(...);图片url地址
>1. border-image-slice:		20或者20%..设置背景图的剪切分割宽度（九宫格切割）拉伸   没有单位
>1. border-image-width:		50px 设置背景图片的宽度(如果不设置会铺满border)
>1. border-image-repeat:  	stretch 拉伸铺满 | repeat重复图片铺满 | round 缩放以后重复铺满
</font>