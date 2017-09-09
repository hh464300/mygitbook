##<center>第七天
####列表属性
>1. list-style-type:   disc（实心点） |  circle（圆圈） | square(小方框) | decimal（数字）...
>1. list-style-position: inside 标示在li里面 | outside 标示在li 外面
>1. list-style-image:  url()   标示的图片展示
>1. list-style: circle inside  url();
####表格属性
>1. table-layout:   auto(自动布局) | fixed(固定布局)
	
	1. fixed固定表格布局与自动表格布局相比，允许浏览器更快地对表格进行布局
	在固定表格布局中，水平布局仅取决于表格宽度、列宽度、表格边框宽度、单元格间距，而与单元格的内容无关。  
	2. auto自动布局，列的宽度由内容决定，算法较慢，这是由于它需要在确定最终的布局之前访问表格中所有的内容
>1. border-collapse:   边框是否被合并为一个单一的边框  
	
	separate默认分开 
	collapse 合并
>1. border-spacing: 10px | 10px 20px（当border-collapse：separate时单元格和行上下左右的距离）
>1. caption-side:  top | bottom  (caption 在上面还是下面)
>1. empty-cells:   show | hide   (空白单元格是否显示,需要border-collapse:separate)

####盒子模型
######Div+css布局介绍(流式布局)
	表现和内容分离 
	代码简洁  
	提高编码速度  
	易于维护和改版  
	提高搜索引擎对网页的搜索效率
######无意义的标签 
 	<div>    块级标签  自动换行(独占一行)
 	<span>  行内标签  内容显示在一行内
######盒子模型
>1. content  	内容
>1. padding  	内边距
>1. border  		边框
>1. margin 		外边距 可设负值 
######块级元素的特点  
>1. 总是开始新的一行。占据整行
>1. 高度，行高以及外边距和内边距都可控制
>1. 没有宽度时，宽度是容器的100%，除非设定一个宽度
>1. 可以容纳行级元素和其他块级元素  

####行内元素特点
>1. 和其他元素在一行
>1. 宽 高，行高，外边距和内边距只有部分可以改变
>1. 宽度和内容有关
>1. 行内元素只能容纳文本或者其他行内元素
######嵌套规则
>1. 块级元素可以包含行级元素或某些块级元素，行级元素不能包含块级元素
	
	<a href=""><a href="">百度</a></a>    错误 
	<a href=""><span>百度</span></a> 	  	正确
	<div><a href="">百度一下</a></div>	  正确
	<div><p>p元素</p></div>			   正确
>2.块级元素不能放在p里
 			 	
	<p><ul><li></li></ul></p>				错误
	<p><div></div></p>						错误
>3.特殊块级元素，只能包含行级元素，不能包含块级元素
	
	h1 h2 --h6  p   dt
>4.li是装载内容的容器。与div类似。

####盒子之间的关系
Document树  	->父元素->子元素->后代元素
####标准文档流
 	
	1.行内元素不占据单独的空间，依附于块级元素，行内元素没有自己的区域。
		它同样是DOM树中的一个节点，在这一点上行内元素和块级元素是没有区别的。
 	2.块级元素总是以块的形式表现出来，并且跟同级的兄弟块依次竖直排列，
	左右自动伸展，直到包含它的元素的边界，在水平方向不能并排。
####盒子在文档流中的特点
>1. 块级元素之间的垂直margin（margin的塌陷）
>1. 嵌套盒子之间的margin,(margin合并)  子元素的magin开始以父元素的内容开始
>1. 可以将margin设置为负值

	特殊情况 ： 父级元素没有设置边框的时候。子元素margin-top出现整体向下的问题。
####margin的参数
	Margin 一个参数 二个参数  三个参数 四个参数    
	margin-left:auto 
	margin-right:auto;
	居中margin:0 auto;
####浮动
	Float:left | right | none
>1. 设置了浮动会脱离文档流  浮动的元素会变为块级元素  
>1. 父级元素不会被撑开  
>1. 下面的元素会挤上来   
>1. 浮动不挡文字 不挡图片
>1. 浮动的元素没有塌陷
####清除浮动 --消除浮动产生的影响
	Clear: left | right | both   
	尝试使用所学内容完成mi.png的布局
  
####实例：	
	1.使用div浮动做个导航条    
   	2.完成div+css布局 
	3.oppo.png