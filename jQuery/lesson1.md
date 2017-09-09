# jQuery第一天

##类库的认识
	1. 类库(class library)  --程序员用来实现各种功能的类的集合
	2. 类库就是一些函数的集合，把特定效果的代码写好，你只需要在用的时候要用很少的代码去调用。   
	起主导作用的是你的代码，由你来决定何时使用类库。
##常见JS类库  (框架)	
* jQuery
* ExtJS
* AngularJs     
* prototype.js   
* React.js
* Vue.js

---
##什么是jQuery	
* jQuery是一个高效、精简并且功能丰富的 JavaScript 工具库
* jQuery极大的简化了JavaScript 编程 "write less do more"
* jQuery很容易学习
* jQuery链式调用
###jQuery的优势	
* 开源 免费
* 便捷的选择器
* 方便的DOM操作
* 方便的动画特效
* 易用的ajax操作  
* 丰富的插件扩展
* 解决浏览器兼容性效果
####jQuery的版本	 --www.api.jquery.com
* 1.**   
* 2.**   IE9+
* 3.**   正式版发布于2016/6/9  不支持IE6-8  精简版不提供ajax模块支持
###关于版本的介绍
		jQuery 1.12.4
		jQuery 1.7.2
		jQuery 1.8.3
		jQuery 1.11.3
		火狐    51.0.1
* 大版本   会有兼容性问题
* 副版本   向下兼容 （升级 内容增加）
* bug版本
##jQuery基础	
* 安装导入jQuery		
* 第一个jQuery脚本	
* jQuery的$函数		
>1. 使用jQuery代替$ 
>1. 让jQuery放弃$   jQuery.noConflict()  --保证不和其他类库冲突
>1. var jj = jQuery.noConflict();   给jQuery重新命名
####等待DOM就绪		
* ready  	$(document).ready(function(){ code..});<br>
简写  $(function(){ code..});
* 与onload的区别
>1. ready 	--页面的dom加载完毕   --可多次绑定
>1. onload 	--页面的所有内容加载完毕
##jQueryDOM 和DOM    --不能混用
* var box = $(‘#div’);   --由dom组成的类数组对象
* var big = document.getElementById(‘div’);  
####相互转换
* 将jquery dom转为dom：   box[0]   
* 将dom转为jquery dom:    $(box)
##jQuery选择器 
###基本选择器
>1.  #id
>2.  element
>3.  .class
>4.  *
>5.  selector1 ,selector2 , selectorN 
###层级选择器
>1. E F
>2. E > F
>3. E + F
>4. E ~ F
####jQuery 导入模块sizzle  选择器功能

	http://sizzlejs.com/ 下载sizzle.js   --得到Jquery对象
	Sizzle(".box")[0].onclick = function(){}
###jQuery筛选器
####基本筛选器	
>1.  :first
>2.  :not(selctor)
>3.  :even
>4.  :odd
>5.  :eq(index)
>6.  :gt(index)
>7.  :last
>8.  :lt(index)
>9.  :header   --选择标题标签
>10. :animated  --正在执行动画的元素
>11. :focus     --使用autofocus显示无效 (可用dom.focus())
>12. :root         
>13. :target       
>14. :lang()     $(“:lang(en)”)     
####内容选择器
>1.  :contains(text)  过滤出包含某个文本的元素
>2.  :empty			过滤出文本为空并且没有子元素的元素
>3.  :has(selector)	包含指定子元素
>4.  :parent			过滤出包含子元素或文本的元素
####可见性选择器
>1. :hidden	过滤出不可见元素（display:'none' type="hidden"）
>2. :visible	过滤出可见元素
####属性选择器
>1. [attribute]	  			包含某个属性的元素
>2. [attribute=value]			包含某个属性且值等于value的元素
>3. [attribute!=value]		匹配包含attribute且值不等于value的元素
>4. [attribute^=value]		包含某个属性且值以value开头的元素
>5. [attribute$=value]		包含某个属性且值以value结束的元素
>6. [attribute*=value]		包含某个属性且值包含value的元素
>7. [attr1][attr2][attrN] 		多个属性选择器
####子元素选择器
>1. :first-child			
>2. :first-of-type  	1.9+	
>3. :last-child
>4. :last-of-type   	1.9+
>5. :nth-child
>6. :nth-last-child()  	 1.9+
>7. :nth-last-of-type()    1.9+
>8. :nth-of-type()         1.9+
>9. :only-child
>10. :only-of-type         1.9+
####表单选择器
>1. :input	所有的表单控件
2. :text	type=text的控件
3. :password	type=password的控件
4. :radio		type=radio的控件
5. :checkbox    type=checkbox 的控件
6. :submit		可提交的按钮
7. :image		type=image的按钮
8. :reset		type=reset的按钮
9. :button		button和type=button
10. :file		type=file
####表单对象属性
>1. :enabled		可用的控件
2. :disabled		禁用的控件
3. :checked			选中的控件
4. :selected			选择的控件
####过滤  --破坏性操作
>1. eq(index|-index)  指定集合中的第几个元素
>2. first()			 集合中的第1个元素
>3. last()			 集合中的最后1个元素
>4. hasClass(class)   返回true | false  (作为判断)
>5. filter(expr|obj|ele|fn)   过滤满足条件的(参数--选择器 可以使用逗号分隔)
>6. is(expr|obj|ele|fn)		返回true| false
>7. map(callback)			遍历所有元素
>8. has(expr|ele)			包含指定子元素
>9. not(expr|ele|fn)			排除满足条件的元素(跟子元素没关系)
>10. slice(start,[end])		截取集合的一部分
