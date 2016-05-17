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

- 备注：定位position:absoult;通过top:25%;left:25%;bottom:25%;right:25%;加上背景颜色来实现灰色区域的宽高和居中位置。

3. flex居中

4. table居中
