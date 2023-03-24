# 1.注意养成编写注释的习惯<!-- -->

a.注释不能嵌套
b.标签成对出现，但也存在一些自结束标签

# 2.在标签中可以设置属性<font color="red">我</font>

a.用来设置标签中的内容如何显示
b.有些属性有属性值，有些没有，color就有
c.标签和属性用空格隔开，可以写多个属性 color size

# 3.网页的基本结构

a.文档声明(doctype)用来告诉浏览器当前网页的版本<!doctype html>

# 4.字符编码

a.编码：将字符转换为二进制码的过程
b.解码：将二进制码转换为字符的过程
c.字符集(charset)：编码和解码采用的规则
d.乱码问题：编码和解码采用的字符集不同
e.开发时使用的字符集都是UTF-8
f.可以通过meta标签来设置网页的字符集，避免乱码问题<meta charset="utf-8">

# 5.实体

a.在网页中编写的多个空格默认情况会自动被浏览器解析为一个空格
b.需要用html中的实体(转义字符)来表达这些特殊的符号
c.&实体的名字：
	&nbsp;空格
	&gt;大于号
	&lt;小于号
	&copy;版权符号

# 6.meta标签

a.charset 指定网页的字符集
b.name 指定数据的名称
c.content 指定数据的内容
       keywords 表示网站的关键字，可以同时指定多个关键字，关键字间使用，隔开
       <meta name="keywords" content="网上购物，网上商城，手机，笔记本，电脑"
       description 用于指定网站的描述

# 7.语义化标签

a.标题标签：h1-h6(递减)，h1在网页中重要性仅次于title标签，一个页面只有一个h1
b.在页面中独占一行的元素称为块元素（block element）
c.p标签表示页面中的一个段落，也是一个块元素
d.<hgroup>用来标题分组
e.<em>标签用来加重语句
f.在页面中不会独占一行的元素称为行内元素(inline element)
g.<strong>标签表示强调，重要内容
h.<blockquote>表示引用，会缩进，块元素
i.<q>表示一个短引用
j.<br>标签表示页面中的换行

# 8.列表

a.有序列表 ol li表示列表项
b.无序列表 ul li表示列表项
c.定义列表 dl dt表示定义的内容 dd解释说明

9.超链接
a.<a href="http://www.baidu.com">超链接</a>
b.<a href="07.列表.html">超链接2</a>
c.target属性 _self当前页面打开 _blank新页面打开
d.<a href="#">回到顶部</a>     
e.id属性唯一不重复  #bottom
f.可以使用javascript来作为href的属性，点这个超链接什么也不会发生

# 10.图片标签

a.<img src="./img/1.gif" alt="松鼠">
b.jpg 一般显示照片
c.gif 颜色单一的图片，动图
d.png 颜色丰富 专为网页而生
e.webp 谷歌推出专为网页 比较小 兼容性不好

# 11.内联框架<iframe src ="http..."hetght="600" frameborder ="0"></iframe>

# 12.音视频<audio src="" controls></audio>

a.controls 允许用户控制播放
b.aotoplay 自动播放（第一次不会自动播放）
c.loop 重复播放