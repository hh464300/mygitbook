##<center>第八天
####实例   
	二级导航栏
	oppo.png
####定位position(不能滥用)
>1. position:static: 静态的。默认。没有特殊样式。
>1. position:relative;相对定位。   相对于自己原来的位置。
		
	Left | right | top | bottom  注意：left 和right 设置一个。Top和buttom 设置一个。
	对别的元素位置没有影响，会覆盖文字和图片
> 3.position:absolute;绝对定位。
		
	1.left | right | top | bottom 
	2.脱离文档流，覆盖文字，覆盖图片
	3.以它"最近"的一个"已经定位"的"祖先元素"为基准进行偏移.如果没有已经定位的"祖先元素", 那么会以<html>为基准进行定位
	4.通常将父元素设置一个定位。relative 和absolute都可以。
> 4.position:fixed;固定定位 。Left | right | top | bottom  
	
	1.脱离文档流
	2.直接根据屏幕定位  跟父级定位没有关系
	3.不随内容滚动
####层级关系 z-index 
>1. 没有单位。   
>1. 该属性用于定位的元素。
>1. 可以为负值
####css的特殊属性  
>1. display  显示

	inline  将块级转化为行级  
	block 	1，显示   2,转化为块级  
	none 隐藏 
	inline-block  行块级，可以设置宽高，但是又不换行。在某些情况下可以取代float。但是换行引起空格     
		已有的行块级元素 input  img
> 2.overflow   
	
	auto 不超出没有滚动条，超出出现滚动条 	
	scroll 不管有没有超出都有滚动条 
	visible 默认超出，对后面没影响 
	hidden  隐藏 | 再次声明我是一个盒子，清除浮动。
	overflow-x  overflow-y 控制x y 轴。
> 3.visibility : hidden; 隐藏   visible 显示 <br>
> 4.display 与 visibility的区别
####通配符  *
####图片的3像素bug
####通用属性
-	标签中都具有的属性  class  id  style  name  title


####页面：猿代码->首页。
######页面准备
>1. ps  cc    markman
>1. 基础base.css样式表 
>1. 创建index.html文件和css  js   images 文件夹
>1. 切图工具  PS   fireworks  fsc
####命名规范：	
#######1. class命名  
	头header 内容 content 尾 footer 导航 nav 侧边栏 sidebar
	栏目  column  左右中 left right center 登陆login  标志 logo 广告 banner 
	页面主体 main 热点 hot 新闻news 子菜单submenu 搜索 search 版权 copyright 		注册 regsiter 服务 service 指南 guide
######2. id命名：   唯一性。简洁  例如按钮 id=”btn” id=”tab” id=”logo”    
######3. 文件的命名规范： 不使用汉字。不使用大写。有意义。
######注意事项： 一律使用小写   使用英文 
####常见问题： 
>1. 该有的a标签没有添加
>1. 代码的缩进
>1. 元素嵌套错误
>1. 使用像素px 单位。不要滥用%。
####审查标准
######1.页面效果完成度(整体感觉)				
######2.页面兼容性 							
>1. IE7 IE8与正常浏览器 
>1. IE7给input设置高度不对齐，（使用：vertical-align:middle;解决）
>1. IE8以下专属属性  *width   *background-color（IE7hack  不做兼容）
>1. IE9以下td高度为设置的高度+边框，IE9及其他td高度为正常的高度  （暂无解决办法）
>1. IE8以下li设置高度  排版错误  设置行高
>1. 使用ul  li ，必要时需要给ul高度
######3.代码规范(缩进, 命名规范,样式与内容分离)		 
######4.标签使用合理程度				 



