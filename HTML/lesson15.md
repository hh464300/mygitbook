##<center>第十五天
####常用宽度设置
>1. 最大高度 max-height
>1. 最小高度 min-height
>1. 最大宽度 max-width
>1. 最小宽度 min-width
####响应式常用单位
>1. vw      100vw = 视口宽度
>1. vh      100vh = 视口高度
>1. vmin    取vm和vh的最小值
>1. vmax    取vm和vh的最大值
######关于base.css（reset.css）  和normalize.css
>1. base.css	<br>
      简单暴力，不管你有没有用，统统重置成一样的效果，且影响的范围很大，讲求跨浏览器的一致性。(革命派)
>1. normalize.css  <br>
       Normalize 相对平和，注重通用的方案，重置掉该重置的样式，保留有用的样式，同时进行一些 bug 的修复，这点是 reset 所缺乏的。(改良派)		
####网格系统（栅格系统）
<img src="./img/1.png">
######配合media媒体查询可以很快的布局。  
######实例：使用网格系统完成微软网页部分

---
####响应式图片
>1. 设置图片的宽度为百分比。<br>
      width:设置宽度%.<br>
      min-width:缩放到最小值时不能继续缩小。<br>
      max-width:图片宽度增大到一定程度不能继续增加。 <br>
>1. 使用背景图片 <br>
      background:url() + background-size:cover + padding,margin
>1. 使用picture   -- 兼容不好 <br>
	
	<picture>
		<source srcset="smaller.jpg" media="(max-width: 768px)">
    	<source srcset="default.jpg">
    	<img srcset="default.jpg" alt="My default image">
	</picture>
> 4.使用picturefill插件 导入picturefill.js文件
    	
		<span data-picture data-alt="img">
			<span data-src="./theme/images/01.jpg"></span>
			<span data-src="./theme/images/01_s_2x.jpg" data-media="(max-width:768px)"></span>
			<span data-src="./theme/images/01_s.jpg" data-media="(max-width:480px)"></span>
		</span>

###PS切图操作
####项目开发人员分配
>1. 项目经理 统筹项目，各方沟通协调
>1. 设计师 (UI)
>1. 程序员(前端，后端，测试，运维等)
####项目开发流程
>1. 了解项目需求  （需求文档） <br>
	a.小型的web项目最好边开发边和用户交流，以尽可能满足用户需求 <br>
	b.大型的web项目最好能将需求让用户确认，便于未来需求修改时评估修改成本或以合适理由拒绝修改
>1. 讨论确定要使用的服务器，数据库，开发语言，框架，跨平台及浏览器支持等。
>1. 前端按照设计完成页面，特效，功能。后端设计数据库及写接口。
>1. 前后端代码优化，数据库优化 组网测试。
>1. 压力测试。
>1. 试运行。试运行也可和前期测试相结合。
>1. 正式上线 （使用文档及培训工作）。
>1. 后期维护 迭代升级。

=====================
