##<center>JavaScript_13
####3. navigator
该对象描述了浏览器厂商和版本信息  (浏览器相关信息)
>1. Navigator 是为了纪念NetSpace公司的Navigator 浏览器
>1. appName    返回浏览器的名称  --只读
>1. cookieEnabled 返回一个布尔值。true （cookie）可用。false  被禁用。
>1. appVersion 返回浏览器的平台和版本信息
>1. userAgent	  返回由客户机发送服务器user-agent头部的值
>1. platform	  返回运行浏览器的操作系统平台
>1. onLine    是否在线
 

####4. History
>1.  back()   	加载history列表中的前一个URL.
>1. forward() 加载history列表中下一个URL    
>1. go()		加载history列表中的某个具体页面 (有参数)

####5. screen
   概述：提供有关窗口显示大小和可用颜色数量的信息
>1. width   返回显示器屏幕的宽度
>1. height  返回显示器屏幕的高度
>1. availWidth	返回显示屏幕宽度（除windows任务栏之外）
>1. availHeight 返回显示屏幕高度(出windows任务栏之外)
>1. colorDepth  返回目标设备或缓冲器上的调色板的比特深度


####实例
>1. 使用正则匹配出浏览器的浏览器名和版本号navigator.userAgent
>1. 无缝滚动   


---

####DOM    文档对象模型  
	--Document Object Model
	--文档对象模型是w3c组织推荐的处理可扩展标志的标准编程接口
######分类：
######1. HTMLDom 针对HTML文档的标准模型
######2. XMLDOM	  针对XML文档的标准模型 
	--语句要求更加严密   （数据传输 跨平台）  Xhtml->html5
	<?XML version="1.0"encoding='utf-8'?>
	<recipe>
	<!--注释-->
	<da></da>
	<im pic=“”/>
	</recipe>

####节点
文档中的每一部分都是节点包括document元素  属性   文本  注释 等等
######核心Dom  针对任何结构化文档的标准模型
	documentNode   ElementNode,  TextNode  AttributeNode

>1. 元素节点            　　Node.ELEMENT_NODE(1)
>1. 属性节点            　　Node.ATTRIBUTE_NODE(2)
>1. 文本节点            　　Node.TEXT_NODE(3)
>1. CDATA节点              Node.CDATA_SECTION_NODE(4)
>1. 实体引用名称节点    　　Node.ENTRY_REFERENCE_NODE(5)
>1. 实体名称节点        　　Node.ENTITY_NODE(6)
>1. 处理指令节点        　　Node.PROCESSING_INSTRUCTION_NODE(7)
>1. 注释节点            　 Node.COMMENT_NODE(8)
>1. 文档节点            　 Node.DOCUMENT_NODE(9)
>1. 文档类型节点        　　Node.DOCUMENT_TYPE_NODE(10)
>1. 文档片段节点        　　Node.DOCUMENT_FRAGMENT_NODE(11)
>1. DTD声明节点            Node.NOTATION_NODE(12)
######HTMLDOM节点
>1. document   HTMLdocument文档
>1. element 	 	元素
>1. attr 			属性
>1. CharacterData  -- text  文本   
	   -- comment 注释
####节点属性
>1. nodeName   节点名字
>1. nodeValue	节点值  
>1. nodeType	节点类型

####获取文档元素方法：
>1. 通过ID选取元素   document.getElementById();<br>
	id属性可自动生成被脚本访问的全局变量
 	不推荐使用  --可读性 保留字
>2. 通过名字选取元素	document.getElementsByName  <br>
	IE9以上和标准浏览器认为所有元素都有name<br>
	IE9 以下认为只有个别元素有name  表单 img form<br>
	document.elementname -->(form  img iframe);  --兼容
>3. 通过标签名选择器	<br>
	document.getElementsByTagName();<br>
	element.getElementsByTagName();
>4. 通过css类选择器元素<br>
	document.getElementsByClassName()  --IE9以下不兼容
>5. 通过css选择器选择元素<br>
	document.querySelector()     获取元素<br>
	element.querySelector()    <br>
	document.querySelectorAll()  获取集合<br>
	element.querySelectorAll()<br>
>6. document.all		获取所有元素的集合
####文档结构
######节点的关系
		--父节点 
		--子节点  
		--兄弟节点   
		--祖先节点  
		--后代节点
######节点树
		childNodes 所有的子节点   length
		firstChild 第一个子节点
		lastChild  最后一个子节点
		previousSibling  上一个兄弟节点
		nextSibling      下一个兄弟节点
		parentNode 父节点  --只有element可以作为父节点(除了document顶级节点)
		var html = document.documentElement;
######元素树
		children  		所有子元素集合
		firstElementChild	第一个子元素		IE9+
		lastElementChild	最后一个子元素		IE9+
		previousElementSibling  上一个兄弟元素  IE9+
		nextElementSibling  下一个兄弟元素  	IE9+
		parentElement   父元素  --只有element可以作为父元素
		childElementCount  子元素的数量     	IE9+
		ownerDocument      返回元素所属的文档对象
实例： 通过table中最后一td中的按钮获取第一个中的数值

* IE9+ 和非IE childNodes将空白作为文本
* IE9- childNodes忽略空白   建议使用children
* 使用previousSibling比使用父节点列表查找效率高  
####属性
	标准属性
		DOM元素映射HTML的属性(属性伴随元素存在) 
	非标准属性 (自定义属性)
	  getAttribute(attr) --获取自定义或内置属性的值(属性需要存在)
	  setAttribute(attr,value)  --设置自定义或内置属性
	  hasAttribute()		--判断属性是否存在(自定义或内置)
	  removeAttribute()     --删除自定义或内置属性
	属性节点
	 getAttributeNode(attr)  		--获取属性节点
	 setAttributeNode(s)  			--设置属性节点
   	--创建属性  
		var s = document.createAttribute(attrname);
    --设置节点值：s.nodeValue=’attrvalue’;
    --设置属性节点 box.setAttributeNode(s);
实例： 图片的延迟加载
####HMLT5  data-*属性的使用
> 使用 data-* 属性来嵌入自定义数据--IE10以上
> 
 	<div data-id="abc123"></div>
	console.log(this.dataset);