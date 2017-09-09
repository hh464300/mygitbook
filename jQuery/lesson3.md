# jQuery第三天

##事件绑定/解除
>1. bind()   事件绑定(单事件,多事件,event.data) 1.7以后建议使用on()
2. on()     事件绑定  事件委派   
3. one()    绑定一次
4. jQuerydom.click(function(){})  原始绑定
5. trigger()	自动触发(地址联动的自动触发)
6. triggerHandler()  自动触发，不触发浏览器默认动作
7. unbind()    解除绑定 1.7以后建议使用off()
8. off()		解除绑定
##事件委派
>1. delegate(dom,event,fn)   事件委派(指定被选元素的子元素)  1.7以后建议使用on()
2. undelegate() 			解除委派    				  1.7以后建议使用off()
3. on(event,dom,fn)          事件委派--注意参数顺序
4. off(event)				不传值解除所有事件
##事件切换
>1. hover(fn1,fn2(可选))   (mouseover 和 mouseout)-->(mouseenter 和 mouseleave)
2. toggle(fn1,fn2)  隐藏/显示
##事件
>1. blur()   		--失去焦点
2. change()   		--value改变
3. click()    		--单击
4. dblclick()  	--双击
5. error()  		--错误   1.8以后废弃的事件
6. focus()		 	--获取焦点
7. focusin()		
8. focusout()	
9. keydown()   	--键盘按下	
10. keypress() 	--键盘按下(可见字符)
11. keyup()		--键盘提起
12. mousedown()  	--鼠标按下
13. mouseenter()    --鼠标滑进
14. mouseleave() 	--鼠标离开
15. mousemove()   	--鼠标移动
16. mouseout()
17. mouseover()
18. mouseup()	    	--鼠标抬起
19. resize()       	--窗口尺寸发生变化
20. scroll()	 	--滚动事件
21. select()	   	--选中
22. submit()	   	--表单提交
23. unload()	  	--离开

##效果
####显示/隐藏
>1. show()   显示  ['normal']['fast']['slow'][2000]  参数二：fn
2. hide()   隐藏
3. toggle() 显示/隐藏
####滑动
>1. slideDown()  ['normal']['fast']['slow'][2000]  参数二：fn
2. slideUp()
3. slideToggle()
####淡入淡出
>1. fadeIn()  ['normal']['fast']['slow'][2000]  参数二：fn
2. fadeOut()
3. fadeTo()  ['normal']['fast']['slow'][2000]  参数二：opacity  参数三：fn
4. fadeToggle()
####自定义动画
>1. animate({},2000,fn)  样式，时间,函数
2. stop()			停止动画 $(.box).animate().animate()   

	--stop()只阻止当前
	可选参数一：是否应该清除动画队列。默认是 false
	可选参数二：参数规定是否立即完成当前动画。默认是 false
3. delay()			延迟
4. finish()		结束动画(瞬间)
####设置
>1. jQuery.fx.off   true|false  是否禁用动画
2. jQuery.fx.interval   帧率(13)
####对象的访问
>1. each(callback)
2. size()  方法
3. length  属性
4. selector	 返回原始选择器
5. context     返回传给$的dom节点
6. get(index)	得到匹配集合中的一个元素   不传值为所有  返回原始dom对象
7. index()    返回相应元素的索引   (选项卡)
####event对象
>1. event.which  --针对键盘鼠标（返回的哪个键）
2. event.data   --事件的传参
3. event.type()   --返回事件类型
4. event.preventDefault()  --阻止默认事件
5. event.stopPropagation() --阻止事件冒泡
6. event.target()		    --触发事件的dom
7. event.pageX			--鼠标的x坐标
8. event.pageY			--鼠标的y坐标

---
* 使用jquery完成表单的验证
* 轮播图 
* homework 作业
