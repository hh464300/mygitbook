# jQuery第二天

###查找
>1. parent()		父元素
2. parents()		祖先元素 找指定的元素(div,li,p) 不指定查找所有的祖先元素
3. offsetParent()	第一个定位的祖先元素
4. parentsUntil()	部分祖先元素(截止到..)
5. children()		子元素(可传值) 不包括后代
6. find()			后代元素
7. next()			下一个兄弟元素
8. nextAll()		后面的所有兄弟元素
9. nextUntil()	后面兄弟元素的一部分(截止到).nextUntil('p:last-of-type')
10. prev()		上一个兄弟元素
11. prevAll()     上面的所有兄弟元素
12. prevUntil()	上面兄弟元素的一部分(截止到)
13. siblings()	所有的兄弟元素
14. closest()	祖先元素中满足条件的(从自己开始) 1.7开始不建议使用
###筛选串联
>1. add()  	把匹配的元素加入前面的集合
2. addBack() 	把前面的元素加入当前集合
3. contents() 获取子节点
4. end()     	返回最后一次破坏性操作之前
###DOM操作
######创建节点
	var myimg = $("&lt;img src='../imgs/4.jpg'&gt;");
####内部插入
>1. append()   向每个匹配的元素内部追加内容(后面) 
2. appendTo() 将指定的内容追加到另一个指定的元素中(后面)
3. prepend()  ..(前面)
4. prependTo()..(前面) 
####外部插入
>1. after()	在匹配的元素后面插入内容
2. before()   在匹配的元素前面插入内容
3. insertBefore() 把匹配的内容插入指定的元素的集合前面
4. insertAfter()  把匹配的内容插入指定的元素的集合后面
####包裹
>1. wrap()  	 把所有匹配的元素用其他元素的结构化标记包裹起来
2. unwrap()    移出元素的父元素
3. wrapAll()  将所有匹配的元素用单个元素包裹起来
4. wrapInner() 将每一个匹配的元素的子内容(包括文本节点)用一个HTML结构包裹起来
####替换
>1. replaceWith()  将所有匹配的元素替换成指定的HTML或DOM元素
2. replaceAll(selector)    用匹配的元素替换成所有 selector匹配到的元素
####删除
>1. empty()  清空
2. remove() 从DOM中删除所有匹配的元素
3. detach() 从DOM中删除所有匹配的元素,与remove()不同的是，所有绑定的事件、附加的数据等都会保留下来
####复制
>1. clone()  克隆匹配的DOM元素并且选中被克隆的dom （true|false）
##属性操作
####属性
>1. attr()  		设置或返回被选元素的内置属性和自定义属性值(标签内)
2. removeAttr()   从每一个匹配的元素中删除一个属性
3. prop()			设置或获取内置的属性
4. removeProp()   删除内置属性
####类
>1. addClass()		添加类
2. removeClass()  删除类
3. toggleClass()  存在则删除，不存在则添加
####文本/值
>1. html()			innerHTML属性的值
2. text()			innerText属性的值
3. val()			value属性的值
####尺寸相关
>1. css() 			设置或获取css数值的值
####位置
>1. offset()		获取元素距离 html 的坐标<br>
	box.offset().top;<br>
	box.offset().left;
>2. position()		获取匹配元素相对定位父元素的偏移<br>
	box.position().top;<br>
	box.position().left;<br>
	只能获取不能设置
>3. scrollTop()	获取匹配元素相对滚动条顶部的偏移(document) 
>4. scrollLeft()   获取匹配元素相对滚动条左侧的偏移 
####尺寸
>1. width()		内容高
2. height()		内容宽
3. innerWidth()	内容宽度+左右padding
4. innerHeight()  内容高度+上下padding
5. outerWidth()	内容宽度+左右padding+左右border
6. outerHeight()  内容高度+上下padding+上下border
####使用已学知识制作一个手风琴效果
	2.png 小米作业
	3.京东楼层特效