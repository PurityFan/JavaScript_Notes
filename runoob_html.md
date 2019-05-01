# HTML usage

## basic content

> HTML5 通用声明

```html
<!DOCTYPE html>
```

> 使用中文编码

```html
<meta charset="UTF-8">
```

> HTML标题(Heading) 是通过`<h1>`-`<h6>`来定义的

```html
<h1>This is a heading</h1>
```

> 段落

```html
<p>这是一个段落.</p>
```

>HTML链接，通过标签`<a>`定义

```html
<a href="http://www.runoob.com">link repo</a>
```

> HTML图象，通过标签`<img>`定义

```html
<img src="/images/logo.png" width="258" height="39 />
```

> 换行 (是没有关闭标签的空元素)

```html
<br>
```

## HTML 属性

Example: 链接由`<a>`标签定义,链接地址在href属性中指定

```html
<a href="http://www.runoob.com">这是一个链接</a>
```

常用html属性

* class: 为html元素定义一个或多个类名（classname）(类名从样式文件引入)
* id: 定义元素的唯一id
* style: 规定元素的行内样式（inline style）
* title: 描述了元素的额外信息 (作为工具条使用)

[更多属性](http://www.runoob.com/tags/html-reference.html)

## HTML 标题

`<h1>-><h6>`

HTML水平线：`<hr>`

HTML注释：

```
<!-- 这是一个注释 -->
```

注释: 开始括号之后（左边的括号）需要紧跟一个叹号，结束括号之前（右边的括号）不需要，合理地使用注释可以对未来的代码编辑工作产生帮助。

查看源代码： 单击右键->查看源文件（view page source）

## HTML 段落

```html
<p>这是一个段落</p>
```

注意：浏览器会自动地在段落的前后添加空行。（`</p>` 是块级元素）, 如果希望在不产生一个新段落的情况下进行换行（新行），使用 `<br>` 标签

## HTML 文本格式化

用于定义粗体与斜体

`<b>`(bold) 代表粗体， `<i>`(italic)代表斜体

`<strong>`，`<em>`还意味着文本重要突出显示

Example:

```html
<b>这个文本是加粗的</b>
<br />
<strong>这个文本是加粗的</strong>
<br />
<big>这个文本字体放大</big>
<br />
<em>这个文本是斜体的</em>
<br />
<i>这个文本是斜体的</i>
<br />
<small>这个文本是缩小的</small>
<br />
这个文本包含
<sub>下标</sub>
<br />
这个文本包含
<sup>上标</sup>
```

`<pre>`用于对空行和空格进行控制

```html
<pre>
此例演示如何使用 pre 标签
对空行和    空格
进行控制
</pre>
```

计算机相关
```html
<code>计算机输出</code>
<kbd>键盘输入</kbd>
<tt>打字机文本</tt>
<samp>计算机代码样本</samp>
<var>计算机变量</var>
```

更多： `<address>`, `<bdo>`定义文字方向，`<ins>`	定义插入字, `<del>`定义删除字, `<abbr>`, 定义缩写, `<cite>`定义引用、引证, `<blockquote>`定义长的引用, `<dfn>`定义一个定义项目 ..."

## HTML <head>

`<title>` - 定义了HTML文档的标题

`<base>` - 使用 `<base>` 定义页面中所有链接默认的链接目标地址。

`<meta>` - 提供了HTML文档的meta标记
使用 `<meta>` 元素来描述HTML文档的描述，关键词，作者，字符集等

## HTML <head>

`<head>` 元素包含了所有的头部标签元素。在`<head>`元素中你可以插入脚本（scripts）, 样式文件（CSS），及各种meta信息。

可以添加在头部区域的元素标签为: `<title>`, `<style>`, `<meta>`, `<link>`, `<script>`, `<noscript>`, and `<base>`.

> meta

meta标签描述了一些基本的元数据。

`<meta>` 标签提供了元数据.元数据也不显示在页面上，但会被浏览器解析。

META 元素通常用于指定网页的描述，关键词，文件的最后修改时间，作者，和其他元数据。

元数据可以使用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他Web服务。

```html
每30秒钟刷新当前页面:
<meta http-equiv="refresh" content="30">
```

> script

`<script>`标签用于加载脚本文件，如： JavaScript。

`<script>` 元素在以后的章节中会详细描述。

## HTML+CSS

对于CSS在HTML中如何添加：

* 内联样式- 在HTML元素中使用"style" 属性
* 内部样式表 -在HTML文档头部 `<head>` 区域使用`<style>` 元素 来包含CSS
* 外部引用 - 使用外部 CSS 文件

最好的方式是通过外部引用CSS文件.

内联样式的例子：

```html
<p style="color:blue;margin-left:20px;">This is a paragraph.</p>
```

> 定义background-colo(背景色), font-family（字体），color（颜色），和font-size（字体大小）

```
<body style="background-color:yellow;">
<h2 style="background-color:red;">这是一个标题</h2>
<p style="font-family:arial;color:red;font-size:20px;">这是一个段落。</p>
</body>
```

> 文本对齐： text-align：center;

## HTML 插入图象

图象标签（img）和源属性（src）

```html
<img src="url" alt="some_text">
```

在浏览器无法载入图像时，替换文本属性告诉读者她们失去的信息。此时，浏览器将显示这个替代性的文本而不是图像。

```html
<img src="boat.gif" alt="Big Boat">
```

> 高度与宽度

```html
<img src="pulpit.jpg" alt="Pulpit rock" width="304" height="228">
```

`<img>`定义图像， `<map>`定义图像地图， `<area>`定义图像地图中的可点击区域

## HTML 表格

每个表格从一个`<table>`标签开始。 每个表格行从`<tr>`标签开始。 每个表格的数据从`<td>`标签开始。

## HTML 布局

大多数 HTML 元素被定义为块级元素或内联元素。块级元素在浏览器显示时，通常会以新行来开始（和结束）。

例: `<h1>`, `<p>`, `<ul>`, `<table>`

内联元素在显示时通常不会以新行开始。

例: `<b>`, `<td>`, `<a>`, `<img>`

HTML`<div>`元素是块级元素，它可用于组合其他 HTML 元素的容器。`<div>`元素没有特定的含义。除此之外，由于它属于块级元素，浏览器会在其前后显示折行。如果与 CSS 一同使用，`<div>`元素可用于**对大的内容块设置样式属性**。`<div>`元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用`<table>`元素进行文档布局不是表格的正确用法`<table>`元素的作用是显示表格化的数据。

HTML `<span>` 元素是内联元素，可用作文本的容器, `<span>` 元素也没有特定的含义。当与 CSS 一同使用时，`<span>` 元素可用于为部分**文本设置样式属性**。

## HTML表单

提供输入的表单 `<form>`

`<input>` 定义输入域

## HTML 框架

可以在同一个浏览器窗口中显示不止一个页面

```html
<iframe src="URL"></iframe>
```

## HTML脚本

插入 JavaScript 使 HTML 页面具有更强的动态和交互性

```html
<script>
document.write("Hello World!")
</script>
<noscript>抱歉，你的浏览器不支持 JavaScript!</noscript>
```

## 字符实体

例如 < > 空格 这样的字符会被HTML解析，所以要使用字符实体。

如：小于号: `&lt`, 或 `&#60` 或 `&#060`
空格 `&nbsp`

实体名称对大小写敏感