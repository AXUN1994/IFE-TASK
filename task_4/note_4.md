> ###  `* {margin:0;padding:0;}`
> *是通配符，表示所有标签元素。此句表示给所有标签设置margin和padding为0。简单粗暴。

### 可以用border-radius画圆

### 水平垂直居中可以用position:absoult;并结合相应代码实现。body的宽和高没有给定，但是定位的是给定具体数值px的区域，实现居中的时候可以用 
>  `top：50%; margin-top:100px; left:50%; margin-left:-200px;`

> 这是根据task_4来讲的。主要在margin-top和margin-left的数值上。

## 以下为源代码

### task_4.html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    	<meta charset="UTF-8">
    	<title>task_4</title>
    	<link rel="stylesheet" href="task_4.css">
    </head>
    <body>
    <div class="graybg">
    <div class="toparea"></div>
    <div class="bottomarea"></div>
    </div>
    </body>
    </html>

### task_4.css

	    body{
    	margin: 0;
    	padding: 0;
    }
    .graybg {
    	width: 400px;
    	height: 200px;
    	background: #ccc;
    	position: absolute;
    	top: 50%;
    	margin-top: -100px;
    	left: 50%;
    	margin-left: -200px;
    }
    
    .toparea {
    	width: 50px;
    	height: 50px;
    	border-radius: 0 0 50px 0;
    	position: absolute;
    	background-color: #fc0;
    }
    .bottomarea {
    	width: 50px;
    	height: 50px;
    	border-radius: 50px 0 0 0;
    	position: absolute;
    	background-color: #fc0;
    	right: 0;
    	bottom: 0;
    }

## 参考别人的代码

1. 在固定元素的宽高下如何居中

        .backg {
  		 width: 400px;
  		 height: 200px;
   		 background: #ccc;
   		 position:fixed;
   		 margin:auto;
   		 left:0;
   		 right:0;
   		 top:0;
   		 bottom:0;
   		 overflow:hidden;
   		 } 

2. 在元素不定宽高的情况下，随着浏览器窗口的变化，宽高也随之改变。

    	<!DOCTYPE html>
    	<html>
    	<head>
    	<meta charset="utf-8" />
    	<title>任务4</title>
    	<style type="text/css">
    	*{margin:0; padding:0;}
		 .box{background: #ccc; position: absolute; top: 25%;left: 25%;bottom:25%;right: 25%;}
    	.round1{width: 50px; height: 50px; background: #fc0;border-radius: 0 0 100% 0; position: absolute; left: 0; top: 0;}
    	.round2{width: 50px; height: 50px; background: #fc0;border-radius: 100% 0 0 0; position: absolute;bottom:0;right:0;}
    	</style>
  	  	</head>
   		 <body>
    		<div class="box">
    			<div class="round1"></div>
    			<div class="round2"></div>
    		</div>
   		 </body>
    	</html>
	备注：定位position:absoult;通过top:25%;left:25%;bottom:25%;right:25%;加上背景颜色来实现灰色区域的宽高和居中位置。

3.  flex居中

	flex布局介绍参考:

	[flexbox 弹性盒布局和布局原理 - 言川的博客](http://blog.csdn.net/lihongxun945/article/details/45458717)

	[Flex 布局教程:语法篇 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

	[Flex 布局教程:实例篇 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html?bsh_bid=683103006)

		<!DOCTYPE html>
		<html lang="en">
		<head>
		<meta charset="UTF-8">
		<title>flex</title>
		<style type="text/css">
		*{
			padding:0;
			margin:0;
		}
		body{
		width: 100%;
		height: 100%;
		}
		.wrap{
			width:100%;
			height:100%;		
			display: -webkit-flex;
			display: flex;
			justify-content:center;
			align-items:center;
		}
		.inner{
			width: 400px;
			height: 200px;
			background: #ccc;
			position: relative;
			overflow: hidden;
		}
		.corner{
			position: absolute;
			width:100px;
			height: 100px;
			border-radius: 50%;
			background: #fc0;
		}
		.top-corner{
			left:-50px;
			top:-50px;

		}
		.bottom-corner{
			right:-50px;
			bottom:-50px;
		}
		</style>
		</head>
		<body>
		<div class="wrap">
		<div class="inner">
			<div class="corner top-corner"></div>
			<div class="corner bottom-corner"></div>
		</div>
		</div>
		</body>
		</html>

4. table居中

	##### 关于display:table-cell;的应用：

	参考链接： [display:table-cell;的应用](http://www.zhangxinxu.com/wordpress/2010/10/%E6%88%91%E6%89%80%E7%9F%A5%E9%81%93%E7%9A%84%E5%87%A0%E7%A7%8Ddisplaytable-cell%E7%9A%84%E5%BA%94%E7%94%A8/)

	 - display:table-cell属性指让标签元素以表格单元格的形式呈现，类似于td标签。单元格有一些比较特别的属性，例如元素的垂直居中对齐，关联伸缩等。

		与其他一些display属性类似，table-cell同样会被其他一些CSS属性破坏，例如float, position:absolute；所以，在使用display:table-cell与float:left或是position:absolute属性尽量不同用。设置了display:table-cell的元素对宽度高度敏感，对margin值无反应，响应padding属性，基本上就是活脱脱的一个td标签元素了。

	* display:table-cell实现两栏自适应布局

		左侧为头像，右侧内容自适应。其中头像部分使用了float属性，左浮动，IE8+以及Firefox、Chrome、Opera等现代浏览器右侧使用了display:table-cell属性，结果就自适应了。

		对于不认识display:table-cell属性的IE6/7呢？很简单，使用display:inline-block属性代替display:table-cell就完全ok的啦！

		如果内容有限，则宽度就是内容的宽度，此时想要让某个元素（例如关闭按钮）右侧定位就会有问题，解决方法就是定义一个非常宽的宽度，就像上面facebook截图中的CSS属性一样，所以，考虑到各种情况，更健壮耐用的CSS代码应如下：

			display:table-cell; *display:inline-block; width:2000px; *width:auto;

		或者使用：

			display:table-cell;  width:2000px; *width:auto; *zoom:1;

	* display:table-cell下的等高布局

		table表格中的单元格最大的特点之一就是同一行列表元素都等高。

	##### 关于vertical-align的应用：
	参考链接： [理解vertical-align或“如何竖向居中”](http://www.webhek.com/vertical-align/)

	##### table居中的源代码

		    <!DOCTYPE html>
    		<html lang="en">
    		<head>
    		<meta charset="UTF-8">
    		<title>flex</title>
    		<style type="text/css">
    		*{
    			padding:0;
    			margin:0;
    		}
    		 body{
    		width: 100%;
   			height: 100%;
   			}
    		.wrap{
    			width: 100%;
    			height:100%;
    			display: table;
    		}
    		.content{
    			display: table-cell;
    			vertical-align: middle;
    		}
    		.inner{
    			width: 400px;
    			height: 200px;
    			background: #ccc;
    			position: relative;
    			margin:0 auto;
    			overflow: hidden;
    		}
    		.corner{
    			position: absolute;
    			width:100px;
    			height: 100px;
    			border-radius: 50%;
    			background: #fc0;
    		}
    		.top-corner{
    				left:-50px;
    				top:-50px;
    
    		}
    		.bottom-corner{
    				right:-50px;
    				bottom:-50px;
    		}
    		</style>
    		</head>
    		<body>
    		<div class="wrap">
    		<div class="content">
    			<div class="inner">
    				<div class="corner top-corner"></div>
    				<div class="corner bottom-corner"></div>
    			</div>
    		</div>
    		</div>
    		</body>
    		</html>