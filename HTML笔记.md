<html>html 根标签</html>

<p>p 段落标签</p>

<h1>h1-h6 标题标签</h1>

<strong>strong 加粗标签</strong>

<em>em 斜体标签</em>

<del>del 定义被删除标签</del>

<address>address 地址标签（成段展示+斜体）=p+em</address>

<div style="width: 50px; height: 50px; background-color:red;">div 分块容器</div>

div*n    <!--回车后创建n个div框架-->

```html
div*3
<div></div>
<div></div>
<div></div>
```

空格/回车仅为分隔符，多个空格/回车也仅为一个分隔符

`&nbsp;` 空格标签

`&lt;` < 小于符号（less than）

`&gt;` > 大于符号（great than）

<br/> 换行标签

li定义列表项目

ol 定义有序列表 

> 属性: 
>
> ​	type=”1” 按照数字排序
>
> ​    type=”a/A” 按照小写/大写字母排序
>
> ​    type=”i/I” 按照小写/大写罗马数字排序
>
> ​    reversed=”reversed” 按照倒数排序
>
> ​    start=”n” 从n开始排序
>

`eg:`

<ol type="I" reversed="reversed" start="7">
     <li>Green Light</li>
     <li>Sober</li>
</ol>

<ol type="A" reversed="reversed" start="2">
     <li>Green Light</li>
     <li>Sober</li>
</ol>

ul 定义无序列表

>    属性: 
>
> ​	type=”disc” 按照实心点排序（discircle）
>
> ​    type=”square” 按照方块排序
>
> ​    type=”circle” 按照空心圆排序
>

注：ul/li非常常用在父子类的需求中，比如网页中的导航栏

``eg:``

<ul type="circle">
    <li>Perfect Place</li>
    <li>Homemade Dynamite</li>
    <li>The Louvre</li>
    <li>Write In The Dark</li>
</ul>

img 图片插入标签

>    属性: 
>
> ​	src=”图片的来源url”
>
> ​    alt=”简单概括图片的说明从而在图片出错时显示”
>
> ​    title=”当鼠标悬停在图片上时显示的说明”
>

<img src="D:\photos\Melodrama.jpg" alt="Melodrama" title="Melodrama" style="width: 200px; height: 200px;">

<a>a标签</a> 

1. 超链接标签

> 属性:
>
> href="http://www.baidu.com" 指向链接目标的属性(需要具体带上http://否则无法跳转)
>
> target="_self" 默认值，在相同的页面打开链接
>
> target="_blank" 在新窗口打开链接

2. a标签也可以当作`锚点`实现回到顶部功能

``eg:``

在顶部放置一个空div并给与id`<div id="top"></div>`

再使用a标签用来识别空div的id并回到顶部`<a href="#top">return top</a>`

3. a标签也可以跳转打电话(多用于手机端)

`<a href="cal:176xxxx5519">点击此处便会跳转打电话</a>`

4.协议限定符，可以在a标签内写入JavaScript代码

``eg：``

点击后进入无限警告循环窗口

<a href="javascript:while(1){alert('Do you want to close me?')}">Please click me!:cry:</a>
1234
