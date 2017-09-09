##<center>第十天
####新增的button 属性
>1. Form    指定要提交的form表单id    IE不支持     button form="myform"提 交/button
>1. Formnovalidate  表单不验证  buttom formnovalidate提交/buttom
>1. Formtarget       提交转到页面打开位置   _blank  |  _self（原窗口打开默认）
>1. Fromaction		指定提交的位置button formaction="2.php"提交/button
>1. Formmethod	    指定提交的方法   get  |  post
>1. Formenctype     有文件上传时使用 multipart|form-data   
####新增的form标签
>1. Output 定义不同类型的输出

	属性： for 值： 输出与相关的元素 Form  字段所属的表单 Name  通用属性
	<form action=””  oninput=”res.value=n1.value+n2.value”>  -- 了解即可
		<input type=”number” name=”” id=”n1”> + <input type=”number” id=”n1”> = 
	<output id=”res” for=”n1 n2”></output>
	</form>
####Datalist   input配合datalist属性定义input可能的值用法如下
	<input type="text" name="" style="width:400px;height:40px" list="mylist" autocomplete="on">
	<datalist id="mylist">
		<option >aaaaa</option>
		<option >abadsdfa</option>
	</datalist>
 
<font color="red">Keygen  验证用户	单标签  当提交表单时，会生成两个键，一个是私钥，一个公钥。
私钥（private key）存储于客户端，公钥（public key）则被发送到服务器。公钥可用于之后验证用户的客户端证书（client certificate）  keygen name=”keys”
IE 不支持
</font>
####新增的全局属性
>1. contenteditable	规定元素内容是否可编辑。  p contenteditable="true|false"
>1. <font color="red">contextmenu	规定元素的上下文菜单。上下文菜单在用户点击元素时显示。 只有Firefox可用</font>
>1. data-*	用于存储页面或应用程序的私有定制数据。(自定义数据  暂时用不到)dataset
>1. draggable	规定元素是否可拖动。 p draggable="true|false|auto"
>1. hidden	规定元素隐藏(不占位)
>1. spellcheck	拼写和语法检查。<element spellcheck="true|false">配合contenteditable
>1. <font>translate	是否翻译 <element translate="yes|no">  所有主流浏览器都不支持该功能</font>
####Html5 的兼容解决方式
>1. IE使用最新版解析
	<meta http-equiv="X-UA-Compatible" content="IE=Edge">     (content=”ie = 8”)
>1. 多核浏览器 指定使用webkit
双核：搜狗浏览器、傲游3、猎豹浏览器、QQ浏览器等。
meta name="renderer" content="webkit"
>1. 使用ckplayer插件解决视频兼容
>1. 让IE9以下的IE浏览器支持html5标签
	
	<!--[if lt IE9]>		
		   <script src="/html5shiv/dist/html5shiv.js"></script>
	<![endif]-->
	
	找到ckplayer官网。找到在线配置功能。复制代码   [必须在服务器下打开]

---

####Css3 介绍
	CSS3是CSS2的升级版本，3只是版本号，它在CSS2.1的基础上增加了很多强大的功能
	--不兼容IE8
####优点
>1. 强大的CSS3选择器 
>1. 新增的背景功能  
>1. 盒子模型的变化  
>1. 阴影效果 
>1. 多列布局与弹性盒模型布局 
>1. Web字体与WebFont图标  
>1. 颜色与透明度  
>1. 圆角与边框 
>1. CSS变形  
>1. CSS过渡与动画交互  
>1. 媒体特性与Response布局
####兼容性解决思想
	渐进增强    优雅降级
>1. 针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。
>1. 一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。
####浏览器和它的内核
>1. IE	 		Trident   
>1. chrome		webkit  
>1. safari 		webkit  
>1. friefox 	Gecko 
>1. opera 以前presto  现在webkit 
>1. 国产浏览器   Trident 和 webkit 
>1. 手机浏览器   webkit 

####Css3属性的私有前缀
>1. IE     -ms-
>1. Chrome -webkit-
>1. Opera  -o-
>1. Firefox -moz-

####Css3 的盒子模型
>1. box-sizing:  盒子的解析方式

	content-box   （默认） 
	border-box    按照设置的宽高解析，压缩内容
>1. resize:  是否允许缩放   配合overflow：hidden;

	none(默认)
	both 
	horizontal(水平)
	vertical（垂直） 
>1. outline : 轮廓线 
	
	1px solid red     不占空间 
	outline-offset:5px;向外延伸
>1. display:   规定元素应该生成的框的类型

	none
	inline
	block
	list-item
	inline-block
	table
	inline-table
	table-caption
	table-cell
	table-row
	table-row-group
	table-clumn|....
####Css3 的颜色
######透明度 opacity
	IE的兼容透明度   filter:alpha(opacity=透明值)0-100
	
####滤镜filter 操作
	--需要使用浏览器的私有前缀
 >1. contrast(%)对比度     
  >1. blur (px) 模糊度
 >1.  brightness(%) 亮度
 >1. invert(%) 反色 >1. ...
 >1. grayscale灰度  Filter:grayscale(100%)
 	
	兼容IE的灰度 
 	filter:progid:DXImageTransform.Microsoft.BasicImage(grayscale=1);
####颜色表示方法：
 >1. rgb(211,122,122) 
 >1. #3dd322  
 >1. red  
 >1. rgba(211,211,211,0.5)
 >1. HSL(360,50%,76%)  色调，饱和度0%-100%，亮度0%-100%
 >1. HSLA(120,50%,60%,0.5) 。。。。。+透明度	<br>
<img src="./img/11.png" width="300px">

	background-color:red; opcity=”0.5” 
	background-color:rgba(255,0,0,0.5);  区别  

