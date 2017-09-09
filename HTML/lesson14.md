##<center>第十四天
####web字体
>1. 使用字体库 -- 有字库 http://www.youziku.com/ 
>1. 使用本地的字体<br> 
		@font-face { font-family: myFont;src: url();} p{font-family:myFont;}
####字体图标
>1. 阿里图标。
	
	资源丰富，文件较小。需要提前准备好所有的图标。
	在demo.html文件中查看使用方法
>1. 使用fa图标  运用简单，可远程。
	
	<link href="http://netdna.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css">
	<span class=”fa fa-battery-04”></span>


####响应式设计
<img src="./images/11.png">	  <br>	
	伊桑·马科特（Ethan Marcotte）在2010年首先提出了响应式网页设计（RWD,Responsive Web Design）这个术语。
	在他的一篇文章《Responsive Web Design · An A List Apart Article》中他将已有的三种发开技巧
	（弹性图片，弹性网格布局，媒体与媒体查询） 进行了整合，命名为响应式网页设计。
	那什么才是真正的响应式设计？马科特说，真正的响应式设计方法不仅仅是根据可视区域大小而改变网页布局，
	而是要从整体上颠覆当前网页的设计方法，是针对任意设备的网页内容进行完美布局的一种显示机制。
######优点：1.开发维护运营成本低。针对不同设备不同分辨率的网页只有一个。
     2.兼容优势。
     3.操作灵活。
     4.面对不同分辨率设备灵活性强	
     5.能够快捷解决多设备显示适应问题
     	---（微软  苹果   oppo  vivo ...）
######缺点：
	1.兼容各种设备工作量大，效率低下
	2.代码累赘，会出现隐藏无用的元素，加载时间加长	
	3.其实这是一种折中性质的设计解决方案，多方面因素影响而达不到最佳效果
	4.不利于搜索引擎收录
####像素密度：ppi或者dpi.
	1. 即每英寸屏幕所拥有的像素数，像素密度越大，显示画面细节就越丰富。
    2. 像素密度的计算方式：像素密度=√{（长度像素数^2+宽度像素数^2）}/屏幕尺寸(计算器) 
    3. 设备像素比（dpr）：每个像素包含的点数。
	    Ihone6 1920/736=2.6每个像素2.6个点渲染	
     说明：同样的尺寸。像素不同。如果没有像素比，则显示会有影响。
####viewport
>1. 用户网页的可视区域（视口）
>1. meta name=”viewport” content=”width=device-width,initial-scale=1.0”
	
	代码说明：width=device-width :   	宽度等于当前设备宽度
	initial-scale:				    初始缩放比列（默认1.0）
    user-scalable:				    是否允许用户缩放(no|yes)
    minimum-scale                   允许缩放的最小比例
    maximum-scale                   允许缩放的最大比例
	思考：在pc端，1px代表1个像素，移动端1px由多个像素组成。移动端如何让1px使用正常1像素表示？
		 window.devicePixelRatio
	

####Css3媒体查询
      1.通过不同的媒介类型和条件定义样式表规则。媒介查询让CSS可以更精确作用于不同的媒介类型和同一媒介的不同条件。
      2.媒介查询的大部分媒介特性都接受min和max用于表达”大于或等于”和”小于或等于”。
      3.通过这个标签属性，我们可以很方便的在不同的设备下实现丰富的界面，特别是移动设备，将会运用更加的广泛。

####媒体查询  -- @media
######媒体类型：	
>1. all    所有媒体设备 
>1. screen 电脑显示器 
>1. print  打印机 
>1. Aural  语音音频...
>1. tty    电传打字机
>1. tv     电视
>1. ....
####媒体样式的导入
	新建print.css 和 screen.css
>1. link href=”print.css”media=”print”
>1. style中使用@import导入       <br>
        @import url('./screen.css') screen;  <br>
        @import url('./print.css') print;  <br>
>1. @media screen
>1. style   <br>
	style media='print'  <br>
           @import url()   <br>
	/style
####媒体特性介绍
>1. aspect-ratio           可视窗口宽高比 min-aspect-ratio:1/1
>1. device-aspect-ratio    设备的宽高比 min-device-aspect-ratio:1/1
>1. orientation            设备方向(landscape 水平 | portrait 垂直) orientation:portrait
>1. width  | (min,max)     可视窗口的宽度  min-width:578px
>1. device-width           设备的宽度
>1. Height                 可视窗口的高度
>1. device-height          设备的高度  device-width:320px (逻辑像素)
>1. resolution             像素比（dppx）   min-resolution:2dppx
####Media query 方式   <br>
>1. and 并且     <br>
>1. ，  或者      <br>
>1. not 否定--取反   @media not screen and (max-width:500px){}  <br>
>1. only  只能...  <br>
####断点
>1. 手机等超小屏幕      0-768px
>1. 平板  小屏幕    768px - 992px  
>1. 中等屏幕        992px - 1200px 
>1. 大屏幕          1200px - 
####其他断点
>1. 小屏幕      0-640
>1. 中屏        640px-1024px
>1. 大屏       1024-

####重新定义导入方式
	<link media=”screen and (min-width:980px)” href=”mycss.css”>

---
####实例：oppo图片展示  尾部伸缩盒
####作业：vivo导航条  