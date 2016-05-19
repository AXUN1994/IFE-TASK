## 日报  5.19 星期四
### 做了什么
* 完成任务五
 
> demo地址:[https://axun1994.github.io/IFE_TASK/task_5/index.html](https://axun1994.github.io/IFE_TASK/task_5/index.html)

> code:[https://github.com/AXUN1994/IFE_TASK/blob/master/task_5/index.html](https://github.com/AXUN1994/IFE_TASK/blob/master/task_5/index.html)

### 遇到什么问题
* Q1:要使左侧区域随着页面大小的调整而调整，不知道如何设置article和section区域的大小

### 解决情况 
* S1：给定属性margin和line-height,设置为line-height:1.5;，其中margin-left和margin-right给定了区域的宽度，line-height给定了区域的高度
 

### NOTE
* 要使多个图片随着浏览器大小自动调节排列，则可把包含这多个图片的外部容器设置display:inline-block;task_5中section部分是文字和图片包含在同一个容器figure中，**应设置figure的宽度为具体px数值，而不是百分比**（*因为若设置为百分比，随着浏览器大小的调整，里面的文字会变成多行，容器会相应变小，图形会变得特别小*），高度可以不设置；容器中的图片宽度设置百分比或具体px值（原图片的百分之xx），高度可以不设置。
* 单行文字居中，只需设置其line-height与父容器的height等值即可。
* 给body设置一个min-width，可以使左侧的内容在页面不断缩小时保持有宽度。
* task_5整个任务没有用position定位。
	- position:absoulte;是基于屏幕页面的绝对定位，其他元素不会对其产生影响
	- position:relative;是基于上一行没有用position的文字的相对定位
	- 右侧区域aside用position:absolute;定位时，若body不设置min-width，当浏览器的宽度缩小至其宽度时，article变得只有一个文字的宽度，aside会覆盖在article上面，且导航栏处会乱掉；当body设置min-width属性时，aside右侧会有大片空白。所以在此不采用position,采用浮动float:right;
* 实现导航栏处链接在当前页面内的跳转，设置为href="#article_1",然后在相应的位置给合适的标签添加id="article_1"
