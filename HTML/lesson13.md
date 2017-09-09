##<center>第十三天
####css3动画
	关键帧：通过控制关键帧来控制动画；帧——最小单位的单幅影像画面，（电影胶片上的每一格镜头）
	设置对象所应用动画的名称：通过@keyframes 定义一个动画的名称
	 @keyframes an{0%{} 25%{} 100%{}}
>1. animation-name:an;      .box{animation-name:an;} 
>1. animation-duration：1s 设置动画的持续时间
>1. animation-timing-function:ease; 设置动画的过渡类型
>1. animation-delay:1s     设置动画的延迟时间
>1. animation-iteration-count: 循环次数  2 | infinite无限循环
>1. animation-direction: <br>
		normal(正常运行)<br>
		reverse（反向运行）<br>
        alternate(先正后反运行 持续) <br>
		alternate-reverse(先反再正 持续)<br>
>1. animation-play-state:<br>
		running(运行) <br>
		paused(暂停) <br>
>1. animation-fill-mode:设置动画结束时的状态<br>
		none(无)<br>
		forwards 结束时的状态 <br>
		backwards 开始时状态<br>
	
	实例：小球下落的简单动画     
####多列  -- 前缀
>1. columns   复合属性（后面可跟列宽300px，列数4,）<br>
               columns:3; 或者columns:300px;
>1. column-width:300px  | 12em;  	指定列宽
>1. column-count:3			   	指定列数
>1. column-gap:20px;     			   设置列与列的间隙距离
>1. column-rule:1px solid #ccc   	设置列与列之间的边框<br>
           column-rule-width: 2px | medium（中）|thin（瘦）|thick(粗)
>1. column-span:none (不跨列)<br>
                 all (横跨所有列) 
>1. column-fill （所有列高度是否统一，但是所有浏览器都不支持）<br>
     column-break-before 		-- firefox IE 不支持<br>
		auto  (默认)
>1. always 总是在元素之前断行并产生新列<br>
	avoid	避免在元素之前断行并产生新列<br>
    column-break-after:	auto 默认<br>
	always 总是在元素之后断行并产生新列<br>
	avoid  避免在元素之后断行并产生新列<br>
>1. column-break-inside:   auto 默认  内容被截断<br>
	avoid  段落内容不被截断	<br>
    
	参考：花瓣网 ..<br>

####布局方式
>1. 流式布局
>1. 伸缩布局
>1. 响应式布局
####伸缩盒
      特点 1.屏幕和浏览器窗口大小改变时可灵活调整布局
           2.可以指定伸缩项目沿着主轴或侧轴按比列分配额外空间
           3.可以指定伸缩项目沿着主轴或侧轴按比列分担缩小的空间
    	 伸缩盒由伸缩容器和伸缩项目构成
>1. display:flex(块级容器)|inline-flex(行块级容器）<br>
		  老版本使用display:box;  <br>
          定义容器：.container{display:flex;}<br>
      	  伸缩容器中的每一个子元素都是一个伸缩项目。伸缩项目可以是任意数量的<br>
>1. flex-direction: -- 设置主轴<br>
				  row (横向主轴)      横向从左到右排列（左对齐）。 <br>
                  column（竖向主轴）  纵向从上往下排列（顶对齐）。 <br>
                  row-reverse			  (对齐方式与row相反)<br>
                  column-reverse	 （对齐方式与column相反）<br>
>1. flex-wrap:      ---项目超出处理<br>
                 nowrap（超出容器不换行) 默认<br>
                 wrap   (超出容器换行) <br>
                 wrap-reverse (反转wrap值的排列)<br>
>1. flex-flow:  组合属性  <br>
                 由flex-direction和flex-wrap值
>1. justify-content:  ---主轴对齐<br>
                flex-start（默认）<br>
                flex-end（结束）<br>
                center(居中)<br>
                space-between(两边对齐，中间正态分布)<br>
                space-around(全部正态分布)注：沿主轴方向<br>
>1. align-items:侧轴对齐方式(在侧轴上的对齐方式)	<br>
               flex-start : 起始位置 <br>
               flex-end:结束边界  <br>
               center :居中            <br>
               baseline:如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐。<br>
              stretch:如果子项目高度为'auto'，则其值会使项目的边距盒的尺寸尽可能接近所在行的尺寸，但同时会遵照'min/max-width/ height'属性的限	
>1. align-self: 单独定义一个子项在侧轴方向的对齐方式<br>
           auto<br>
           flex-start<br>
           flex-end<br>
           center<br>
           baseline<br>
           stretch<br>
           
>1. align-content:当使用flex-wrap为wrap，并且为多行的时候。在侧轴的对齐方式	<br>
           flex-start 		起始位置堆叠, 每一行都紧靠住前面一行<br>
           flex-end   		结束位置堆叠 每一行都紧靠住前面一行<br>
           center     		中间位置堆叠 每一行都紧靠住前面一行<br>
           space-between 	两端对齐其余在弹性盒容器中平均分布<br>
           space-around  	各行在弹性盒容器中平均分布<br>
           strecth 			默认 各行将会伸展以占用剩余的空间
>1. flex-grow:2;   设置子项目的扩展比例。(应用于子元素没用达到父元素的宽度的时候)
>1. flex-shrink:2; 设置子项目的收缩比例。(应用于子元素超过父元素宽度的时候)
>1. flex-basis:200px | 100%;伸缩项目的基准值。(和重新设置宽一样，计算时配合flex)
>1. flex   复合设置  <br>
         flex:1 2 300px;扩展比例1，收缩比例2，基准值300px;
>1. order  设置盒子排序的顺序。数值小的排在前面。可以为负值。<br>
         order:1; <br>
         order:2;   
####实例如下
<img src="./images/1.png">
####作业如下
<img src="./images/11.png">

