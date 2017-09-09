##<center>JavaScript_17

####元素的内容
>1. innerHTML
>1. outerHTML
####作为纯文本的元素内容
>1. textContent   IE9+
>2. innerText  --忽略多余的空白
####文本节点的方法
>1. appendData()  向文本节点追加内容
>2. deleteData(start,length)   删除文本部分内容
>3. insertData(start,string)    向文本中插入部分内容
>4. replaceData()      替换文本内容
>5. substringData()   截取文本内容

####元素节点操作
>1. 节点的创建	
	######document.createElement();
>2. 节点的添加<br>
	appendChild()  --在元素后面添加<br>
	insertBefore(new,old) --在元素指定的位置添加<br>
>3. 删除节点<br>
	removeChild()   --使用父级删除子级<br>
>4. 替换节点<br>
	replaceChild(new_node,old_node)  <br>
>5. 克隆节点<br>
	cloneNode()<br>
	true  --克隆当前节点以及其所有的后代节点<br>
	false --只克隆当前节点<br>
#####DocumentFragment节点<br>
    文档碎片(临时容器)  文档片段
	document.createDocumentFragment();
	documentFragment节点不属于文档树
######应用实例： 元素反转
	var frag = document.createDocumentFragment();
	while(container.lastChild){
	frag.appendChild(container.lastChild);
	}
	container.appendChild(frag);
	----完成反转后frag将不存在文档中
####元素宽高 位置 滚动等尺寸	
######1. 元素坐标
>1. offsetLeft   距离已定位的父级left值
>1. offsetTop     距离已定位的父级top值
>1. offsetParent  得到最近定位的父级元素
>1. clientLeft    得到边框的尺寸
>1. clientTop     得到边框的尺寸
######2. 元素尺寸
>1. getBoundingClientRect()  尺寸对象
>1. offsetWith       盒子模型的宽（包含边框）
>1. offsetHeight     盒子模型的高(包含边框)
>1. clientWidth      盒子模型的内容宽(不包含边框)
>1. clientHeight     盒子模型的内容高(不包含边框)
>1. scrollWidth      盒子模型的宽(计算超出内容)
>1. scrollHeight     盒子模型的高(计算超出内容)
######3.滚动
>1. scrollLeft
>1. scrollTop
######4. 通过坐标点获取元素
>1. document.elementFromPoint(100,100); 
######5. 获取html文档的宽高
>1. document.documentELement.offsetWidth;  --视口宽度
>1. document.documentElement.clientHeight; --视口高度
>1. document.documentElement.scrollHeight; --内容高
######DOCUMENT对象
	每个载入浏览器的 HTML 文档都会成为 Document 对象。
	Document 对象使我们可以从脚本中对 HTML 页面中的所有元素进行访问。   
>1. URL     获取当前页面的URL  --只读
>2. domain  获取域名            --只读
>3. referrer 获取上一个页面的地址 --只读
>4. title   页面title
>5. location      主机			--只读
>6. lastModified  最后一次修改时间  
>7. cookie   获取或设置cookie
######方法：
>1. document.write();
>2. document.getElementById();
>3. .......

<hr>

####Table表格
######table属性
>1. cells 返回包含所有单元格的数组
>2. rows  返回包含所有行的数组<br>
	-tab.rows[0].cells[1] 
>3. border 	返回或设置table边框
>4. caption 	对表头的引用
>5. cellPadding 设置或返回内容与单元格边框间距
>6. cellSpacing 设置或返回单元格间距
>7. id 		 设置或返回表格的id
>8. width 		 设置或返回表格的width
######table 方法
>1. createCaption   创建一个表头<br>
    --var s =  tab.createCaption();s.innerHTML=‘’;
>2. deleteCaption   删除表头<br>
	--tab.deleteCaption();
>3. createTHead()	在表格中创建一个空的 tHead 元素。
>4. deleteTHead()	从表格删除 tHead 元素及其内容。
>5. createTFoot()	在表格中创建一个空的 tFoot 元素。
>6. deleteTFoot()	从表格删除 tFoot 元素及其内容。
>7. insertRow()	在表格中插入一个新行。
>8. deleteRow()	从表格删除一行。--传入行的索引
####tr 的属性
>1. cells	返回包含行中所有单元格的一个数组。
>2. rowIndex	返回该行在表中的位置。
####tr 的方法
>1. deleteCell()	删除行中的指定的单元格。
>2. insertCell()	在一行中的指定位置插入一个空的 <td> 元素。
####td、th的属性
>1. cellIndex	返回单元格在某行的单元格集合中的位置。

######实例：
	将文件(data.html)中模拟的两条数据遍历到表格中

######css样式的查询
>1. element.style.attrname   --需要将样式写在标签的style中
>2. window.getComputedStyle(element)  --低版本IE不支持
>3. element.currentStyle[attrname]     --仅IE