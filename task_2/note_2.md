###遇到的问题
* Q1:导航栏中百度logo的白色不能被背景色覆盖，导航栏中的无序列表前面的实心圆点消失，并且li {list-style-type:disc;}不起作用
* Q2：不知道如何实现截图中的对齐效果，以及单选框和下拉框的样式效果
* Q3：不知道如何实现垂直居中对齐，自己一直用text-align:center;和padding解决相应问题，不知道这种写法是否正确
* Q4：导航栏中对超链接进行了li a:link,a:visited{······}的定义，不知道为什么在下面的表格中的超链接也沿用了上面的定义
### 解决情况 
* S1：
 + 从任务图上截取logo图片进行替换（背景色不能覆盖背景图片）
 + 不使用`li{display:inline;}`，使用`li{float:left;}`
* S2:
 + 实现对齐效果：给文字部分加上div,class为`.class {width:50%; text-align:right; display:inner-block;vertical-align:top;}`;提示部分加上div，class为`.tip{ margin-left:50%;}`
 + 单选框下拉框的样式仅靠css不能很好的更改，需要借助加上
* S3:暂且如此
* S4:将`li a:link,a:visited`修改为`li a:link,li a:visited`