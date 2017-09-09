##<center>第五天
####Css 样式表
	Cascading Style Sheets  层叠样式表
####1选择器{属性名：属性值}
####2 css的使用  
	1.在元素中 
	2.在style中  
	3.从外部导入link  
	4.style中引入@import url()   
	5.@import url前面不能有别的样式
	link与@import 的区别
####3注释  
	/*  */
####Css的单位 

######长度单位：  
>1. px   宽高 距离 字体大小等
>1. % 
>1. em     字体本来大小的倍数(作用于字体)
>1. rem		根元素html的font-size
>1. vh   	1vh = 	视口高度/100
>1. vw   	1vw =	视口宽度/100 
>1. vmin    vm和vh中较小的
>1. vmax    vm和vh中较大的
>1. 绝对单位：pt（点）   cm   mm
####颜色单位：
>1. 单词   
>1. rgb(0-255,0-255,0-255)    
>1. rgb(%，%，%)  #000; 

####颜色转换

####选择器  
>1. html元素选择器
>1. id 选择器
>1. class 类选择器
>1. 关联选择器 select select   select > select  select + select     select ~ select
>1. 组合选择器 div p span.item 
####选择器优先级
>1. 就近原则
>1. 优先级的计算
	
	Id:100
	Class:10
	Html：1
	Style:1000
####伪类选择器
>1. :link   链接样式      针对链接
>1. :hover  鼠标滑过的样式  
>1. : active   点击时的样式
>1. :visited   访问过后的样式  针对链接
 	
	顺序不同 执行效果不同
	提示：在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
	提示：在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
	提示：伪类名称对大小写不敏感。
1.   :hover  :visited在不是超链接的元素中使用
2.   使用伪类自定义一个按钮



