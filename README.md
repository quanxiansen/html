**布局：假设高度固定，左栏、右栏宽度为300px，中间自适**
**实现方法1：用float**
html结构：
```
<div class='left'></div>
<div class='right'></div>
<div class='center'></div>
```

css代码

```
div{
height:100px;
}
.left{
	float:left;
	width:300px;
}
.right{
float:right;
width:300px;
}
.center{
width:auto;
}
```
float布局好处：兼容性比较好。缺点：需要去除浮动；
**实现方法2：用绝对定位**
html结构：

```
<section>
	<div class='left'></div>
	<div class='center'></div>
	<div class='right'></div>
</section>
```
css代码：

```
div{
position:absolute;
}
.left{
left:0;
width:300px;
}
.center{
left:300px;
right:300px;
width:auto;
}
.right{
right:0;
width:300px;
}
```
好处：浏览器兼容性好，写法简单；缺点：脱离文档流；
**实现方法3：flex布局**
html布局结构同上
css样式：
```
section{
display:flex;
flex-wrap:wrap;
height:100px;
}
.left{
width:300px;
}
.center{
flex-grow:1;
}
.right{
width:300px;
}
```
优点：解决上面布局不足存在，比较完美；缺点：ie8以下的浏览器不支持
**实现方法4：table布局**
html结构同上
css代码：

```
section{
display:table;
width:100%;
}
section div{
display:table-cell
}
.left{
width:300px;
}
.center{
width:auto;
}
.right{
width:300px;
}
```
优点：兼容性比较好；缺点：表格单元格超出，两侧的单元格都得调整高度；
**实现方法5：grid布局**
html结构同上
css代码：

```
section{
display:grid;
grid-template-rows:100px;/**设置列的高度**/
grid-tempate-columns:300px auto 300px;/**设置列的宽度**/
}

```
优点：写法简单；缺点：浏览器兼容性不好；
**如果高不固定的情况下，高度自动撑开只有flex布局和table布局可以做到，其他的都不行**



