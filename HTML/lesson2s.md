##<center>HTML第二天
####超链接   a标签
	超级链接在本质上属于一个网页的一部分，它是一种允许我们同其他网页或站点之间进行连接的元素。
	各个网页链接在一起后，才能真正构成一个网站。
	所谓的超链接是指从一个网页指向一个目标的连接关系，这个目标可以是另一个网页，
	也可以是相同网页上的不同位置，还可以是一个图片，一个电子邮件地址，一个文件，甚至是一个应用程序。
	而在一个网页中用来超链接的对象，可以是一段文本或者是一个图片。
	当浏览者单击已经链接的文字或图片后，链接目标将显示在浏览器上，并且根据目标的类型来打开或运行。

> 一网络中的个文件： http://cdn.bootcss.com/html5shiv/3.7.2/html5shiv.min.js
#####路径信息
	相对路径  
			./   
			../   
			../../
	绝对路径  	
			http://  开头
	根路径 
			/  网站根目录
####URL详细地址
	http://www.w3school.com.cn/info/conf/index.php?p=1
	或者
	http://www.w3school.com.cn/info/conf/index.php#page

>1. http://  					协议
>1. www.w3school.com.cn 	 域名 (通过DNS解析 对应ip地址)
>1. /info/conf/	    path 路径
>2. index.php  		文件名
>3. p=1 			查询
>4. #page 			锚点
####a标签属性 
>1. title  	&nbsp;	&nbsp;提示信息
>1. target 	&nbsp;	&nbsp; _blank	&nbsp;   _self 		&nbsp;<font color="red"> -parent   	&nbsp;-top </font>	
>1. href    &nbsp; 	&nbsp;url地址信息
>1. download  	&nbsp;下载
>1. alt   		&nbsp;	&nbsp;	&nbsp;描述信息。给搜索引擎看的
####其他功能

	---需要操作系统有outlook
	email： <a href=”mailto:mayun@lampbrother.net”>发邮件</a>
	电话：  <a href=”tel:110”></a>
	信息...  <a href=”sms:100”></a>（需要window系统装有outlook）

####锚点
>1. &lt;a name='test'&gt;&lt;/a&gt;  		锚点声明  <br>
>1. &lt;a href='#test'&gt;  &lt;/a&gt;    	锚点调用

---
####图像  
	格式  jpg  png  gif .....   （新的图片格式webp）

>1. jpg 适用于摄影图片，以及色彩丰富的图片。它采用压缩算法，通过强制渐变的方法来减小文件尺寸，因此无论选择的储存质量多高，还是会多多少少失真一些，但对于摄影之类的图片来说，jpg格式就会比png小很多了
>1. png 完爆gif的地方在于失真小，没锯齿；劣势是不支持动画；
采用无损压缩，在多数情况下都可以保留图片里所有像素。PNG无损压缩算法，简单地说，就是把图片里出现的每一个颜色都记录下来。通过记录这些颜色相对应的值记录一张图片
>1. gif 色彩效果最低，用gif保存鲜艳的图片的话会让你的网站看上去非常可怕。但是gif有着不可忽视的特点：体积小，有着极好的压缩效果，支持动画，
####属性
>1. src 		图片地址
>1. alt 		描述信息/加载失败的提醒
>1. height   高度
>1. width    宽度
>1. border   边框
>1. ismap	点击图片，会将坐标信息发送到服务器端
>1. usemap  配合map标签进行图像的映射
####图像的映射
>1. ismap
	
>1. usemap  (为了良好的兼容请使用#)
	<pre>
	   img src = ''   usemap='#myimg'
		map  
            id='myimg' name='myimg'
			area shape='rect | circle | poly' 
            coords='0,0,23' 
            href='www.baidu.com' target=''  
            alt=''
	   /map
    </pre>
####实例：
>使用图像映射，锚点完成商城活动。


