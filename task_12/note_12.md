1. `:nth-of-type(odd);`：奇数 ；`:nth-of-type(even);`：偶数；
2. `:nth-child(odd);`：奇数； `:nth-child(even);`：偶数；

	`:nth-child(an+b);`：表示周期的长度，n是计数器（从0开始），b是偏移量

	其中，`:nth-child(-n+x);`：表示前x个；`:nth-child(n+y);`：表示前y个之后的所有数;
3. 伪类 `:target`：选择当前活动的元素
4. 实现点击切换：

两个容器section,一个大的，一个放点击控制的块。前一个包含后一个。html代码如下：

	<section class="banner">
    	<ul class="slider">
    		<li id="fir">1</li>
    		<li id="sec">2</li>
    		<li id="thr">3</li>
        </ul>
    	<section class="banner-controll">
    		<a href="#fir">1</a>
    		<a href="#sec">2</a>
    		<a href="#thr">3</a>
    	</section>
    </section>

点击控制的块用绝对定位定位到右下角，最主要的是切换效果

重要的：`id="fir";` `herf="#fir";` `left:-100%;或者left:100%;` `width:300%;` `overflow:hidden;` `li:target;` `:nth-child(){}`

css代码如下：

	/*切换效果*/
	@keyframes scroll {
		0% {left:-100%;}
		100%{left:0;}
	}
	.slider li:target {
		z-index:6;
		animation:scroll 500ms linear;
	}
	/*样式重置*/
	ul,li{margin:0;padding:0;list-style-type:none;}
	a {text-decoration:none;}
	/*主要的类*/
	.banner {
		position:relative;
		overflow:hidden;
		width: 300px;
		height: 200px;
		border:1px solid #9cc5ef;
	}
	.slider {
		width:300%;
		overflow:hidden;
	}
	.banner-controll{
		position:absolute;
		right:0;
		bottom: 0;
		overflow:hidden;
		z-index:10;
	}
	/*不同背景色的切换区域--方法一*/
	.slider li:nth-child(1){z-index:3;background-color:#01254a;}
	.slider li:nth-child(2){z-index:2;background-color:#C4D213;}
	.slider li:nth-child(3){z-index:1;background-color:#6bacef;}
	/*不同背景色的切换区域--方法二*/
	#fir{z-index:3;background-color:#01254a;}
	#sec{z-index:2;background-color:#C4D213;}
	#thr{z-index:1;background-color:#6bacef;}
	/*其他类和元素效果设置省略*/
				


