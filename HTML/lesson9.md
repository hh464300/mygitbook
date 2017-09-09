##<center>第九天
####HTML5介绍
	HTML5草案的前身名为 Web Applications 1.0，于2004年被WHATWG提出，
	于2007年被W3C接纳，并成立了新的 HTML 工作团队。
	HTML 5 的第一份正式草案已于2008年1月22日公布。HTML5 仍处于完善之中。
	然而，大部分现代浏览器已经具备了某些 HTML5 支持。
	2012年12月17日，万维网联盟（W3C）正式宣布凝结了大量网络工作者心血的HTML5规范已经正式定稿。
	根据W3C的发言稿称：“HTML5是开放的Web网络平台的奠基石。”
	2014年10月29日，万维网联盟宣布，经过接近8年的艰苦努力，该标准规范终于制定完成。
####Html5 的优点      
>1. 提高可用性，改进用户体验。
>2. 添加新标签，有助于开发人员定义重要的内容。
>3. 更多的多媒体元素（视频影音）。
>4. 很好的替代flash和siverlight
>5. 对搜索引擎更加友好。Seo优化。  
>6. 可移植性比较好，将被大量应用于应用程序和游戏。
####兼容性：
	chrome  safari opera  firefox 以及以webkit为内核的国产浏览器   IE9及以上
####新增的结构标签（块级元素  语义性）
>1. Header 头部 
>1. nav 导航
>1. footer页脚 
>1. main(ie 不支持)主体部分
>1. aside 侧边栏    
>1. section 带标题的段 
>1. article文章 贴子 等  
>1. <font color='red'>details （open 属性 打开）配合 --summary
>1. summary  解释说明。 chrome safari 支持 新版本火狐支持。基本不用。
>1. dialog  (open 属性)定义一个对话框 脱离文档流   只有chrome  safari支持</font>
####新增的文本标签（行级元素  语义性）  在w3c 手册中查看标签的兼容性
>1.  bdi  允许改变文本方向(bdo)    各大浏览器都不支持。
>1.  mark  高亮显示。可以改变背景颜色来改变高亮的颜色
>1.   meter 定义度量  属性： high  low(警戒值) max min (最大最小值) value (当前值) optimum（当值大于high 说明越高越好，小于low，越小越好）
 ie不认识     大小可以,别的样式改不了。
>1. progress  进度   和meter差不多。语义性。一个是固定的度数。一个是进度完成了多少。  IE认识
>1. wbr  截断单词   一行可以显示时不换行. 
>1. ruby  注音 <ruby>犇<rt>ben</rt></ruby>   <ruby>骉<rt>biao</rt></ruby>   <rp></rp>不再支持
>1.  time  定义一个时间   

	<time datetime=”2016-10-1”>国庆节</time>  		
	<article pubdate=”2016-5-3”></article>
####新增的图像标签
>1. figure   定义一段独立的流内容，比如文章的插图。如果删除不影响主体内容。
> figcaption   流内容的主题  
	
>1. canvas  定义图像（使用代码画图)
	
	
####新增列表标签  
	dl         定义对话   解释  类型的列表标签
	 dt
	 dd
	dl 
####menu   只有firfox支持

####HTML5中的音视频
<img src="./images/2.png">
####video 视频
video src=””你的浏览器不支持/video
######属性：
>1. 	src      url路径
>1. autoplay		如果出现该属性，则视频在就绪后马上播放。
>1. controls	如果出现该属性，则向用户显示控件，比如播放按钮。
>1.   loop如果出现该属性，则当媒介文件完成播放后再次开始播放。
>1.   muted	  规定视频的音频输出应该被静音。
>1.  	preload	 如果出现该属性，则视频在页面加载时进行加载，并预备播放。 如果使用 "autoplay"，则忽略该属性。注：支持流媒体
>1. poster	 URL	规定视频下载时显示的图像，或者在用户点击播放按钮前显示的图像。
>1. height	 pixels	设置视频播放器的高度。
>1. width	 pixels	设置视频播放器的宽度。

####source 定义多种媒体资源
	属性 src(url)   type (video/mp4)(video/ogg)
	<video controls>
			<source src="../../source/movie.ogg" type="video/ogg">
			<source src="../../source/movie01.mp4" type="video/mp4">
	</video>
####audio 定义音频
######属性  
>1. src (url) 
>1. autoplay  
>1. controls  
>1. loop  
>1. muted  
>1. preload
  	
	可以配合source标签定义多种资源进行兼容
	strack  进度控制，预览等功能。需要javascript

####Html5新增表单元素
######新增Input type属性
>1. email  匹配邮箱地址
>1. url    必须输入url地址
>1. number 必须是数字  属性： min   max   step  value 
>1. range   取值范围  min  max   step   value
>1. search   效果和text一样。属性 results (-webkit-内核专有)
>1. tel	     用于电话号。在pc上等于text。在移动设备上会调用数字键盘
>1. color	 调出取色板    IE不支持 （IE edge版本支持）
####时间相关（火狐 IE不支持）
>1. date  日 月 年
>1. month	月 年
>1. week	周 年
>1. time	小时 分钟
>1. datetime  utc时间（日 月 年）--暂不支持
>1. datetime-local 本地时间，(日 月 年)
####新增Input 控件
>1. pattern  正则验证 内容为空的时候不验证 和required配合
>1. multiple 可以选择多个文件。type=”file” 时
>1. placeholder  提示文字，和value不同  
>1. autocomplete  自动完成    可以设置值为  on/off
>1. autofocus	   自动获取焦点  只能给一个input获取焦点
>1. required		   不为空
####新增form属性  
>1. autocomplete  自动完成  off/on
>1. novalidate 	   表单不验证  写或者不写。