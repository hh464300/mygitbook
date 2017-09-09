# jQuery第五天

####BootStrap的使用
>1. 字体图标的使用
2. 导航条
2. 路径
2. 分页
2. 巨幕
2. 缩略图
2. 模态框
2. 轮播图
##jQuery中的ajax
####get   
>1. 参数一：url
2. 参数二：data
2. 参数三：callback
2. 参数四：type(返回数据的类型： json html xml...)
####post
>2. 参数一：url
2. 参数二：data
2. 参数三：callback
2. 参数四：type(返回数据的类型： json html xml)
####ajax
	常用参数
>1. url:'2.txt',
>1. type:'get',
>1. data:'name=sanmao&age=12',
>1. dataType:'json',
>1. async:true,
>1. success:function(data){
		console.log(data);
	},
>1. error:function(){
console.log(‘请求发生错误’);
}
####getJSON
	获取json数据
####getScript
	加载并执行一个js文件
####serialize()
	序列化表单提交内容
####load()
	加载dom元素

---

## sass   less
####css预处理器
	CSS不是一种编程语言。
	你可以用它开发网页样式，但是没法用它编程。
	也就是说，CSS基本上是设计师的工具，不是程序员的工具。
	在程序员眼里，CSS是一件很麻烦的东西。它没有变量，也没有条件语句.
	只是一行行单纯的描述，写起来相当费事。
	很自然地，有人就开始为CSS加入编程元素，这被叫做"CSS预处理器"（css preprocessor）。
	它的基本思想是，用一种专门的编程语言，进行网页样式设计，然后再编译成正常的CSS文件。
####常用的css预处理器
* sass(scss)
* less
* stylus
* Turbine
* DTcss
*  .....
####sass优点：
* 功能强大
* 简单易学
* 学习教程较多
* 新版本功能更加优秀 --(新版bootstrap4.0使用sass开发)
####缺点:sass编译依赖ruby,  ruby官网及服务在国内访问不了。

##安装使用
>1. 使用ruby
2. 使用第三方软件  <br>

	koala和codekit功能类似，支持多平台，免费，开源。可编译less sass coffeeScript等。
####Koala的特性及功能
>1. 多语言支持
2. 实时监听，当文件改变时自动执行编译，一切在后台运行，无需人工操作编译。
3. 编译选项，可以设置各语言的编译选项。
4. 支持代码压缩，less和sass支持编译后自动压缩。
5. 错误提示。
6. 跨平台运行，可以在Window  Linux  Mac   OS等平台运行
####使用方法
>1. 导入目录 目录中存在.scss文件	
2. 右键删除目录
3. 编写.scss代码，当编写完成保存，自动生成.css文件保存在配置目录中。
4. 给submit安装scss/less插件 打开sublime安装目录下的Data → Packages目录 重启submit
####语法
1. 后缀名：  .sass  或者  .scss


	.sass  语法要求严格  不使用大括号和分号。
	.scss  语法类似css。
	
####变量	
* 1.作用于属性值
$color:red;
.box a{
color:$color;
}
* 2.作用于属性名
$side:left;
.box{
		border-#{$left}-radius:
}
####计算  （运算符两端使用空格 防止错误）
	$width:200px;
	$mar:10px;
	.box{
	width:$width/2;
	height:$width*2;
	margin-left:($mar/2);
	}
####嵌套
	div h1{
	font-size:15px;
	}
	可写成
	div{
	h1{
	font-size:15px;
	}
	}
####属性的嵌套
	div{
	border:{color:red}; 注意冒号
	}
####嵌套（引用父元素）
	li a{ &:hover{color:#fff;} }

####继承
	.container{
	font-size:200px;
	}
	.box{
	@extend .container;
	color:white;
	}
####@mixin (重用的代码段 --函数)
	@mixin header{
	color:pink;
	font-size:15px;
	line-height:30px;
	}
	.nav{
	@include header;    //使用@include 调用
	& ul li{float:left;display:block;}
	}
####@mixin (传参)
	@mixin mainer($value:15px){
	color:pink;
	font-size:$value;
	line-height:30px;
	}
	.aside{
	@include mainer(20px);  //传入参数
	border-radius:10px;
	}
	@mixin show($a,$b,$color1:red,$color2:green){
	border-#{$a}:1px solid $color1;
	border-#{$b}:2px solid $color2;
	}
	.main{@include:show(left,right,#333,#ccc)}
####引入外部文件 @import
	@import '2.scss';
	@import '2.css';
	@mixin中的 @content   --使用scss做一响应式的布局(改变断点尺寸)
	@mixin max-screen($maxwidth){
	@media screen and (max-width:$maxwidth){
	@content;
	}
	} 
	@include max-screen(768px){
	.box{background:red};
	}
####占位选择符 %   --定义代码段
	如果不调用，不会有任何css
	%base{
		margin:0;padding:0;
		border:1px solid #ccc;
		box-sizing:border-box;
	}
	.base{
	@extend %base;
	}
####sass函数  @function getSize(){}
	--条件语句 @if  @else  @return
	@function getSize($s){
		@if($s < 100px){
			@return $s;
		}@else{
			@return 200px;
		}
	}
	.box{
		width:getSize(110px);
	}
####三元运算符
	.a{
		width:if($v > 100px,300px,100px);  --if后面没有空格
		}
####循环语句
	1. @for $i from 1 through 10{}   --包含10
	2. @for $i from 1 to 10{}		--不包含10
	@for $i from 1 through 10{
	.box#{$i}{
	color:red;height:200px + $i;
	}
	}
	3. @while{}
	$b : 20;
	@while($b>=1){
		.nn#{$b}{
			width:400px - $b;
		}
		$b:$b - 1;     //运算符尽量留空格，防止报错
	} 
####遍历 @each
	语法
	@each $value in $list;
	$list :damao ermao sanmao simao wumao liumao;
	@each $value in $list{
	.img_#{$value}{
	background:url('../images/#{$value}.jpg');
	}
	}
####字符串函数
	1.unquote(string)  --删除字符串的引号
	2.quote(string)	--给字符串添加双引号
	3.to-upper-case(string)   --大写
	4.to-lower-case(string)	   --小写	
####数字函数
	1.percentage($value)  将一个不带单位的值，转换为百分比(1==100%)
	2.round($value)		四舍五入
	3.ceil($value)		进一取整
	4.floor($value)		舍一取整
	5.abs($value)
	6.min(numbers..)
	7,max(numbers...)
	8.random()			获取0-1的随机数
	--注意：将数值和px等单位拼接
####列表函数
	1. length($list)		列表长度
	2. nth($list,$n)		列表中的制订元素  nth($list,2);
	3. join($list1,$list2) 合并两个集合
	3. append($list,$value)将$value添加进$list集合
	...
####颜色函数
	1. lighten(#000,0%);  给一个颜色增加亮度 形成一个新的颜色
	2. darken(#fff,0%);   给一个颜色降低亮度，形成一个新的颜色
	3. grayscale(red);    将颜色变灰
	.....
####@at_root 跳出嵌套


