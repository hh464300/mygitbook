##<center>HTML第四天
####表格table
	概念  行 单元格
####标签table  
>1. border 		边框 
>1. width 		宽度
>1. height 		高度
>1. cellspacing 	边框间距
>1. cellpadding 	字体距离边框间距
>1. bgcolor   	背景颜色
>1. align 		表格位置
>1. background 背景图片
####tr    行
>1. height  		高度  
>1. bgcolor 		背景颜色
>1. align=“left|center|right” 		水平位置
>1. valign=“top|center|bottom” 		垂直位置
>1. background 背景图片
####td单元格 
>1. width  	宽
>1. height  高   
>1. align 	
>1. valign 
>1. bgcolor 
>1. rowspan   	合并行
>1. colspan		合并列
>1. background 背景图片
###caption 表格标题
####th   表头tablehead 单元格
####表格语义性质的三个标签
	thead 
	tbody
	tfoot
	修改指定的列(宽度 背景颜色)
	colgroup span=''
	col span=''  

####表单
	表单在网页中主要负责数据采集功能。
	label的使用
####form属性  
>1 action 
>1. method
>1. enctype="multipart/form-data"  当有文件传输的时候
####表单控件
	input  type='' 
>1. text 
>1. password 
>1. radio 
>1. checkbox 
>1. file 
####按钮 
	submit
	reset  
	button  
	image
####select  下拉菜单
	<option value></option>	
	<optgroup label=''></optgroup> 将option 分组

####textarea 文本域  
	name="" name值
	rows    行数
	cols    列数
####表单控件常用属性
>1. name=""   
>1. value="" 
>1. size='23' 	尺寸（23个字符宽度）通常不用 而是使用css控制input长度
>1. maxlength  最大输出长度
>1. readonly 只读
>1. checked  默认选中  常针对单选和多选
>1. selected  默认选中  针对下拉菜单
>1. disabled  不可用
######readonly 可以将数据提交  disabled数据不能提交
####表单分组
	fieldset 将表单分组 
	legend 为组定义标题

	form
		fieldset
			legend>个人信息</legend>
			input
			select  ..
		/fieldset
	/form
####分帧 -- html框架
>在网页中使用框架结构最大的弊病是搜索引擎的“蜘蛛”(spider)程序无法解读这种页面。
但是有些地方不需要搜索引擎收录如添加微博直播信息，这些微博信息我们并不需要提供给搜索引擎，而我们需要提供的 是与访客的一个互动的体验
######优点：	
	1.重载页面时不需要重载整个页面，只需要重载页面中的一个框架页			
	2.方便制作导航栏
######缺点：	
	产生很多页面，不容易管理。
	不容易打印
	移动端适应性较差
	增加http请求·
####iframe
	iframe  src="menu.html" 
			width="800" 
			height="500" 
			frameborder="1" 
			style="border:10px solid #999" 
			scrolling="yes">
	/iframe
	div style="position:absolute;top:0px;right:20px;"
		iframe src="http://www.baidu.com" style="width:300px;height:250px;" name="main" 
		/iframe
	/div  
	使用div指定布局位置  
######iframe 属性
>1. src=''   url
>2. frameborder='0 | 1'  是否显示边框
>3. height
>4. width
>5. name
>6. scrolling   yes  | no | auto

---
####实例练习：
>在表格中创建一个表单