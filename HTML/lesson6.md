##<center>第六天
####背景属性
>1. Background-color:  red   #333  transparent（继承父级）....
>1. Background-image:url()  背景图
>1. Background-repeat：是否重复 repeat | no-repeat | repeat-x | repeat-y 
>1. Background-attachment:scroll（随着内容滚动） fixed（固定在页面）
	
	1.在body中使用 	
	2.在元素中使用 需配合overflow:scroll;
	scroll 相对于元素定位,不随内容滚动
	fixed 相对于视口定位,不随内容滚动
	local 相对于所有内容(元素自身)定位，随内容滚动
> 4.Background-position:背景位置 center top | center center 100px 200px ... <br>
> 5.backgorund: color  url('')  repeate  attachment  position <br>
>精灵图 
  

####颜色属性   
>color:   -- 规定文本属性  继承性

####字体属性
>1. Font-family:(字体族)"Arial","Helvetica",sans-serif,’宋体’,’微软雅黑’;  需要系统字体支持
>1. Font-size:(字体大小)
>1. Font-style:（风格）normal | italic | oblique
>1. Font-weight:（加粗） normal | bold | lighter   400正常  700=bold
>1. Font-variant:(变形) normal | small-caps 小型大写字母
>1. font:bold small-caps 30px Arial,"Microsoft YaHei",sans-serif;

####文本属性
>1. Letter-spacing  字间距
>1. Word-spacing  词间距
>1. Text-decoration   none | underline | overline | line-through
>1. Text-align    left | center | right   左右对齐方式
>1. Vertical-align  top | middle | bottom | baseline....		上下对齐方式
>1. Text-indent  50px  文本缩进
>1. Line-height 设置行高  行高与高度一致，可以垂直居中 
 		
		使用px  
       	%(文字尺寸倍数)  
		number  其中number*font-size等于px的行高
####使用字体行高
	font：15px/3 ‘微软雅黑’;


####边框属性
>1. border-width:边框宽度  (double线 需要大于3)
>1. border-style：边框样式  (dotted 点线   solid  实线 dashed 虚线...)
>1. border-color:边框颜色
     
	1.可单独设置各个边框border-left | border-top | border-right | border-bottom
	2.元素的宽高=设置的宽高+边框宽度
>1. 实例：使用边框属性写一个三角形
####鼠标光标属性
>1. cursor: text | wait | help | pointer | help......






