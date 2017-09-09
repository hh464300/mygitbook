##<center>第十二天
####css背景属性
>1. background-origin: 起始位置   padding-box（默认） | border-box(边框) | content-box(内容) 
>1. background-clip: 结束位置  padding-box(padding结束) | border-box(默认) | content-box(内容) 
>1. background-size:背景大小
	Background-size:auto;			使用原图的大小尺寸
	Background-size:px | %;			使用固定值指定背景图大小	
	Background-size:cover;			自动缩放铺满盒子模型
	Background-size:contain;		等比例缩小原图，盒子包含原图，但是会有空白
######多背景属性
	url('../../images/bg-tl.png') no-repeat, 
	url('../../images/bg-tr.png') no-repeat right top, 
	url('../../images/bg-bl.png') no-repeat left bottom, 		
	url('../../images/bg-br.png') no-repeat right bottom,
####文本属性 
>1. word-spacing  
>1. letter-spacing 
>1. text-indent   
>1. vertical-align  
>1. text-decoration
>1. text-transform 字体转换 none(不转) capitalize(首字母大写) uppercase(大写) lowercase(小写)
>1. text-transform:full-width	全宽属性(兼容较差) firefox支持 排版拉丁字符等。
>1. tab-size  int | px        tab键缩进的尺寸。   -- 配合pre
>1. text-align   left | center | right | justify | start | end | match-parent | justify-all (不兼容) 
>1. text-align-last left | right | center  (最后一行的偏移方向) 
>1. <font color="red">text-justify :  文本对齐方式                               所有都不支持
>1. text-size-adjust :auto | none | %  文本大小根据设备尺寸调整 所有都不支持  </font> 
>1. text-shadow :3px 3px 4px #ccc  字体阴影
>1. text-overflow:  clip（剪切）  | ellipsis   	文字溢出   配合overflow:hidden
>1. word-wrap 单词超出换行机制  normal(正常不换行) | break-word 	强制换行
>1. word-break 换行机制  normal(正常)  keep-all(统一英文机制换行)  break-all强制换行
>1. text-stroke  设置文字描边 IE不支持   p{-webkit-text-stroke:2px green;color:transparent}
>1. white-space 空白处理 --参考w3c

	white-space :normal   正常显示 正常换行
	white-space : pre  类似<pre>/</pre>
	white-space : nowrap 文字在一行显示 可配合text-overflow:ellipsis 
	white-space:  pre-wrap   比pre多了一个换行
	white-space:  pre-line	pre换行并取消每行前面空白


---

####转换  变形  
######位移
>1. -webkit-transform:translate(50%，50%)。  设置元素位移
>1. -webkit-transform:translatex().设置x轴的位移
>1. -webkit-transform:translatey().设置y轴的位移
	
	如何让一个盒子在大盒子的正中间	
	position:absolute;left:50%;top:50%;transform:translate(-50%, -50%);
######缩放
>1. -webkit-transform:scale(0.5);        设置元素缩放
>1. -webkit-transform:scale(0.5,0.2);    设置元素缩放
>1. -webkit-transform:scalex(0.2);	 设置x轴的缩放
>1. -webkit-transform:scaley(0.4);	 设置y轴的缩放	

######旋转
>1. -webkit-transform:rotate(20deg);	 设置旋转角度
	
	配合transform-origin:0 0;
######扭曲
>1. -webkit-transform:skew(0deg,0deg);	 设置扭曲
>1. -webkit-transform:skewx(50deg);	 设置x轴扭曲
>1. -webkit-transform:skewy(50deg);	 设置y轴扭曲


----

####3D中的过渡变形旋转
######位移
	transform:translatex(10px),
	transform:translatey(20px),
	transform:translatez(20px),
	transform：translate3d(10px,20px,30px) 分别对应x,y,z轴位移
######旋转
	transform:rotatex(),
	transform:rotatey(),
	transform:rotatez(),
	transform:rotatex(20deg)  rotatey(20deg)  rotatez(20deg);
	-webkit-transform:rotate3d(1,1,1,60deg); 三个方向一个角度
	0或1的数值 主要用来描述元素是否围绕x,y,z轴旋转的矢量值

######缩放
	transform:scale3d(1,2,3);  3d缩放。参数分别对应xyz轴
	transform:scalez();			z 轴的缩放值  -- 没效果
######变形的组合写法	
     transform:translate(50px,0px) rotate(20deg) scalex(1.5);


####3D相关属性
>1. transform-origin: left top;			指定圆点(使用旋转)
>1. perspective 			指定观察者与z=0的平面距离。 舞台元素

>1. transform-style:      flat(子元素不保留3d位置 不常用)  preserve-3d	(子元素保留3d位置)  
>1. perspective-origin:center center;指定3d透视圆点
>1. backface-visibility:visible(默认)显示hidden；  指定3d背面元素不显示<br>
<img src="./images/12.png" width="400px">
####过渡
	transition属性	
	过渡的触发  1.伪元素触发  2.媒体查询 3.JavaScript触发
>1. transition-property: none | all | css属性  （指定要过渡的css属性） 颜色，长度，属性值是数值的如z-index opacity  阴影 渐变，变形
>1. transition-duration:1s;	指定过渡需要的时间
>1. transition-delay:2s;  延迟时间
>1. transition-timing-function:
	ease 
	linear 
	ease-in 
	ease-out 
	ease-in-out
	cubic-bezier 自定义贝塞尔曲线http://cubic-bezier.com/	
	Steps(7)以7步变化
######组合属性
	将所有属性写在一起；transition:all 5s 1s cubic-bezier(0,1.15,.28,.83);
<img src="./images/11.png">


