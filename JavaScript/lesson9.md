##<center>JavaScript_10
####正则表达式 （规则表达式）
	定义：使用单个字符串来描述、匹配一系列符合某个语法规则的字符串搜索模式。
	^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$
####和正则相似的事物  
>女人的心   
道士的符   
医生的字  
正则表达式

####正则表达式的作用：
	操作字符串是正则唯一的作用
  	验证用户名  
    验证电话号码  
   	验证密码等表单元素
    聊天软件的表情
  	新闻采集  --小偷程序
    ....
####正则表达式的定义		
>1. var res = /html5/
>2. var res = new RegExp(/html5/); 参数二：正则修饰
>3. var res = RegExp(“html5”);  
######ECMA5规定正则对象为独立的实例
    var a = /a/;
	var b = /a/;
	console.log(a==b); 
	return false;
####表单的简单验证
 	html中直接验证： <input type="text" pattern="\w{2}">
使用js进行正则验证
>1. 定义字符串           var email = "abc"; 
2. 定义正则语句         var reg = /b/;
3. 返回匹配结果(数组)	console.log(email.match(res));
    --input:  对字符串对象的引用
####定义正则语句
>正常的字母数字都是原子

		var str = "abcebd123";
		var reg = /b/;
		console.log(str.match(reg));
######特殊字符
>2.\n查找换行符<br>
>3.\f查找换页符  --打印机  或 操作系统等终端<br>
>4.\r查找回车符<br>
>5.\t查找制表符  (tab键)<br>
>6.\v垂直制表符  --打印机  或 操作系统等终端<br>
>7.匹配unicode字符	console.log(text.match(/\u50bb\u903c/));

注意：<font color="red">特殊字符串的匹配：var s = 'abcabcaff';匹配abca</font>

####字符类
>1. [abcdef]   可选列表，只能是原子列表中的一个字符
>2. [7-9]		 多选列表（连字符），7-9之间的数字 
>2. \u2E80--\u9fff  所有的文字包括日语韩语等
>2. [^7-9]  	 取反，不是7-9之间的数字 （[a-zA-Z0-9_]）
>2. \d		  匹配所有数字
>2. \D		  匹配所有非数字
>2. \w		  匹配数字字母下划线
>2. \W		  除了数字字母下划线
>2. \s		  表示所有空白字符   包括 \r  \n \t
>2. \S		  表示所有可见字符
>2. **.**		  匹配所有除了\n \r
####正则重复      {原子数量修饰符}  
	注：修饰紧挨着的一个原子
>1. +       表示一个或者多个(连续的)    /a+/
>1. ？      表示0或者一个			     /a?/	
>1. *       表示任意个				 /a*/
>1. {}      {m,n}   表示m到n个		 /a{3,5}/	
>1. {m,}	表示大于m			   /a{3,}/
>1. {m}	表示m个		 	           /a{m}/
>1. {0,m}	表示0-m个 			   /a{0,5}/    --{,m}  X

####非贪婪模式 ?
	console.log("aaaaaaaaaaaaaaaaaa".match(/\w{2,10}/)); 贪婪
	console.log("abcdefhigklmnopqr".match(/\w{2,6}?/));  非贪婪

####特殊原子的匹配  --在正则中具有特殊意义的符号需要转义
>1. ？  
>1. \                     
>1. //
>1.  .
>1. *  
>1. 等等.......     
####选择修饰符    |
	/a|b/   		匹配a或者b   
	/abc|def/  		匹配abc或者def    字符串结合优先级大于选择符
	/ab(c|d)ef/		改变优先级  匹配abcef   abdef
####模式单元修饰符   （）
1. 将多个原子视为一个原子
	str.match(/(abc){1,3}/);
>1. 将匹配的内容暂存在内存
	'abc'.match(/(a)(b)(c)/);
>1. 提高优先级
  	'abcdef'.match(/ab(c|d)ef/);
>1. 将括号的内容反向引用
	console.log("abcac".match(/(\w)\w(\w)\1\2/));
>1. 使用(?:)取消暂存内存的特性，没有暂存在内存不能进行引用
	console.log("abc".match(/(?:ab)(c)/));<br>
	console.log("abcc".match(/(?:\w)\w(\w)\1/));

####词边界---只对英文有效
	\b   词边界（单词的边界）  
	console.log("hello helloworld".match(/\bhello/g));
	console.log("hello helloworld".match(/hello\b/g));
	\B   非词边界
	console.log("hello helloworld".match(/hello\B/g));
####正向预查(?=)  	
######----字符串后面的值是？？？
	console.log("hellobaby helloworld".match(/hello(?=world)/g));
	console.log("hellobaby helloworld".search(/hello(?=world)/g));
####反向预查(?!)	
######字符串后面的值不是？？？ 
	console.log("hellobaby helloworld".match(/Java(?!baby)/g));
	console.log("hellobaby helloworld".search(/Java(?!baby)/g));
####字符串边界  用于精确匹配
	^  以指定字符开头
		console.log("abcdef".match(/^a/));
	$  以指定字符结尾
		console.log("abcdef".match(/f$/));
####正则表达式修饰符
>1. g   <font color="green">执行全匹配(查找所有匹配)</font>
>2. i   <font color="green">执行对大小写不敏感</font>
>3. m	<font color="green">执行多行匹配(一般存在^或$时才会起作用)</font>
####用于模式匹配的String方法
>1. search()	检索与正则表达式相匹配的第一个字符索引值
>2. match()		找到一个或多个正则表达式匹配的字符串
>3. replace()	替换与正则匹配的子串
>3. split()		把字符串以正则表达式分割成数组<br>
	参数2;指定数组的长度   --超出范围将不起作用
####正则对象的方法
>1. test();检索字符串中指定的值。返回 true 或 false。  <br>
	console.log(/^\w{5}$/.test("abc"));<br>
	console.log(/^\w{5}$/.test("abc3s")); 
>2. exec();返回匹配的值，并确定其位置。不能使用g进行全局匹配。可以使用i	
	console.log(/\w(\w)/.exec('abced45'));<br>
	console.log(/\w/g.exec('abced45'));<br>
#####实例
>实例1.    --匹配html标签
>实例2.    --匹配URL
	
	var str = 'Lorem ipsum dolor sit amet, consectetur adipisicing elit加入百度，加入网页搜索你可以影响世界,将简历发送至：http://www.baidu.com.cn/admin/info/config/index.php Laboriosam, libero, repellendus iste eum necessitatibus nemo cumque ipsum quos accusamus maiores et voluptas eaque provident excepturi expedita consequuntur';
	
	var res = /(http|https):\/\/([\w\.]+)\/((\w+\/)*)(\w+\.(\w+))/;
	var val = str.match(res);
	var s = "URL : "+val[0]+'<br>';
			s += "协议名 : "+val[1]+"<br>";
			s += "主机名(域名) : "+val[2]+"<br>";
			s += "路径名 : "+val[3]+"<br>";
			s += "文件名 : "+val[5]+"<br>";
			s += "后缀名 : "+val[6]+"<br>";
>实例3： 将文章中中文引号替换成英文引号<br>

	vat text = "小明：“门前有条小河沟很难过”.老师：“小明，出去。”";<br>
	var  res = text.replace(/”|“/g,’"’);<br>
>实例4：  将文章中英文引号替换成中文引号<br>


	var res = text.replace(/"([^"]*)"/g,"“$1”");<br>
	注：$1代表第一个存入内存中的内容

>实例5： 将lady gaga 替换成gaga lady<br>
>实例6： 尝试将数字格式化为千分位数字<br>
>实例7： 将匈牙利命名法 改成驼峰命名法<br>
       
		例如： border-bottom-width ->  borderBottomWidth<br>
		1. 使用字符串处理方法<br>
		2. 使用正则匹配方法<br>
		function show(str){
		var reg = /-([a-z])/;
		str.replace(reg,function($0,$1){
		return $1.toUpperCase();
		});
		}

----
#####作业： 
	使用正则对表单提交的内容进行验证(用户名 密码 重复密码 电话 邮箱  博客地址) 不符合条件不能进行表单的提交
	--onsubmit 事件