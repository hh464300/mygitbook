##<center>JavaScript_08
####JavaScript 定时器
>1. 单次定时  setTimeout(fn,2000);
>2. 多次定时  setInterval(fn,2000);
>3. 停止多次定时  clearInterval(timer);   
>4. 停止单次定时  clearTimeout(timer);
######实例：
	使用单次和多次定时写倒计时。
####通过js获取或者修改元素的css样式
	在w3c中找到JavaScript的语法
>1. 获取  dom.style.attribute  
>1. 设置  dom.style.attribute = '';  dom.style.cssText='';
>1. 实例： <font color="red">使用按钮设置隐藏与显示</font>

####命名介绍
	backgroundColor小驼峰命名法 
	BackgroundColor 大驼峰 
	background-color匈牙利命名法
####数学运算  
>1. document.write(Math);   //数学运算对象
>1. document.write(Math.PI);//PI是数学对象的一个属性
>1. document.write(Math.abs(100.21));//绝对值
>1. document.write(Math.pow(2,4));//求次方2的4次方
>1. document.write(Math.sqrt(100));//开平方
>1. document.write(Math.round(100.21));//四舍五入
>1. document.write(Math.floor(100.21));//舍一取整
>1. document.write(Math.ceil(100.21));//进一取整
>1. document.write(Math.max(100.21,334,344,34));//求最大值
>1. document.write(Math.min(100.21,343,543));//求最小值
>1. document.write(Math.random());			//取随机数  0--1

######取随机数   
	1.取0-9随机数： Math.floor(Math.random()*10); 
	2.取0-17随机数：Math.floor(Math.random()*18);
 	3.取0-10随机数：Math.round(Math.random()*11);
######取优质随机数
    4.0-9优质随机数   Math.floor((Math.random()*1000000)%10);
 	5.0-17优质随机数  Math.floor((Math.random()*1000000)%18);
 	6.9-17优质随机数  Math.floor((Math.random()*1000000)%9+9);
>实例：<font color='red'>点名器</font>

####Boolean对象
	var a  = true; 
	var b = new Boolean(1);
	var c =  Boolean('abcd');
	typeof a
	typeof b
	typeof c
	b.valueOf()     //返回boolean对象的原始值  --typeof
	b.toString()   //转为字符串 
####Number对象
######属性
	MAX_VALUE		可表示的最大的数
	Number.MAX_VALUE
	MIN_VALUE 		可表示的最小的数
	Number.MIN_VALUE
	NaN				非数字值
######方法
	toString()			转换为指定的进制数
	50.toString(2)
	toFixed()			转换为指定小数点位数的数值
	12.2343.toFixed(1)  //参数0-20
	toExponential()		转换为科学计数法
	12.434343.toExponential()
	toPrecision()		转换为指定长度的数值
	1000.121323123.toPrecision()    //参数1-21
####String对象
	字符串比较
	(ASCII码表)  Unicode进制
######属性
>string.length;  字符串长度(空格算一个字符)
######String方法
	var str = 'what are you nong sha lie,you are so beautiful';
>1. charAt()			//返回指定位置的字符
>2. concat()			//连接字符串
>3. charCodeAt()      //返回指定字符的unicode编码
>4. fromCharCode()	//将unicode编码转为字符
>5. indexOf()			//搜索指定字符(首次出现)  没有返回-1
>6. lastIndexOf()     //从后往前搜索字符串
>7. slice()			//字符串截取 start,end
>8. match()   		//正则
>9. search()
>10. str.replace
>11. substr()			//截取字符串 start,length
>12. substring()  	//和slice用法相同
>13. toLowerCase()	//转换为小写
>14. toUpperCase()		//转换为大写
>15. split()  		    //分割字符串

实例：<font color="red">尝试将匈牙利命名法 改成 小驼峰命名法</font>

====================================
######以下内容自己下去看
>15. anchor()     //给字符串添加一个锚点
>15. big()  		// 用大号字体显示字符串
>15. blink()       //添加一个blink标签
>15. fixed()		//以打字机文本显示字符串
>15. fontcolor()	//以指定颜色显示字符串
>15. fontsize()  	//以指定大小显示字符串
>15. small()      //小型字体
>15. italics()   	//斜体 
>15. sub()    	//下标	  
>15. sup()        //上标
>15. toLocaleLowerCase()	
>15. toLocaleUpperCase()	

---
####作业
>实例一：进度条<br>
实例二: 点名器1   点名器2<br>
实例三: 距离世界末日还有 10:10:10<br>
实例四：1.jpg中的js效果<br>
实例五：不重复的点名器<br>
实例六：小球的下落(开始暂停)<br>
实例七：来回滚动的小球<br>

