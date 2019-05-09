# CSS usage

CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明

* 选择器通常是您需要改变样式的 HTML 元素。
* 每条声明由一个属性和一个值组成。属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开

example:

CSS声明总是以分号(;)结束，声明组以大括号({})括起来:

```html
p 
{
color:red;
text-align:center;
}
```

CSS注释：以 `/*` 开始, 以 `*/` 结束

## CSS id 与 class

> id 选择器

关键字`#`, 以下的样式规则应用于元素属性 id = "para1"

```html
#para1
{
    text-align:center;
    color:red;
}
```

> class 选择器

class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用。class 选择器在HTML中以class属性表示, 在 CSS 中，类选择器以一个点"."号显示

```html
/* 所有拥有 center 类的 HTML 元素均为居中 */
.center {text-align:center;}

/* 所有的 p 元素使用 class="center" 让该元素的文本居中*/
p.center {text-align:center;}
```

注： ID属性和类名不要以数字开头，数字开头的ID在 Mozilla/Firefox 浏览器中不起作用

## CSS 创建

插入CSS的三种办法：外部样式表(External style sheet)， 内部样式表(Internal style sheet)， 内联样式(Inline style)

1. 外部样式表(External style sheet)

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 <link> 标签链接到样式表。 <link> 标签在（文档的）头部：

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

浏览器会从文件 mystyle.css 中读到样式声明，并根据它来格式文档。外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的 html 标签。样式表应该以 .css 扩展名进行保存。

```html
/* example of .css file */
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("/images/back40.gif");}
```

2. 内部样式表(Internal style sheet)

当单个文档需要特殊的样式时，就应该使用内部样式表。可以使用 <style> 标签在文档头部定义内部样式表。

```html
<head>
<style>
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("images/back40.gif");}
</style>
</head>
```

3. 内联样式(Inline style)

由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势。请慎用这种方法，例如当样式仅需要在一个元素上应用一次时。要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性。

```html
/* 展示如何改变段落的颜色和左外边距 */
<p style="color:sienna;margin-left:20px">这是一个段落。</p>
```

**多重样式优先级: (内联样式）Inline style > （内部样式）Internal style sheet >（外部样式）External style sheet > 浏览器默认样式**

注意：如果外部样式放在内部样式的后面，则外部样式将覆盖内部样式

## CSS 背景

* background-color
* background-image
* background-repeat
* background-attachment
* background-position

## CSS 文本格式

颜色：代号表示，对于W3C标准的CSS：如果你定义了颜色属性，你还必须定义背景色属性。

对齐方式：text-align设置为`justify`，每一行被展开为宽度相等，左，右外边距是对齐（如杂志和报纸）

文本修饰：text-decoration（下划线等）

文本转换：`p.uppercase {text-transform:uppercase;}`大小写转换

文本缩进：`{text-indent:50px;}`是用来指定文本的第一行的缩进

CSS 字体：有`通用字体系列`(拥有相似外观的字体系统组合（如 "Serif" 或 "Monospace"))或者`特定字体系列`（一个特定的字体系列（如 "Times" 或 "Courier"））- font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。`font-size`可以控制文本大小

```html
p.normal {font-style:normal;} 普通
p.italic {font-style:italic;} 斜体
p.oblique {font-style:oblique;} 斜体
```

## CSS 链接

链接有四种状态：

```html
a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
```

note: `a:hover` 必须跟在 `a:link` 和 `a:visited`后面, `a:active` 必须跟在 `a:hover`后面

## CSS 列表

比HTML更丰富的列表标记，也可用图像作列表项标记

* 设置不同的列表项标记为有序列表 
* 设置不同的列表项标记为无序列表 
* 设置列表项标记为图像 

不同的列表标记：

```html
<head>
<style>
ul.a {list-style-type:circle;}
ul.b {list-style-type:square;}
</style>
</head>

/* 使用 a 格式 */
<ul class="a">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ul>

/* 使用 b 格式 */
<ul class="b">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ul>
```

使用图标进行列表标记

```html
<style>
ul 
{
	list-style-image:url('sqpurple.gif');
}
</style>

<ul>
<li>Coffee</li>
<li>Tea</li>
<li>Coca Cola</li>
</ul>
```

## CSS 表格

指定CSS表格边框，使用border属性， 显示一个表的单个边框，使用 border-collapse属性，text-align属性设置表格水平对齐方式， Width和height属性设置表格宽度和高度，使用td和th元素的填充属性

```html
<style>
table, td, th
{
	border:1px solid green;
}
th
{
	background-color:green;
	color:white;
}
</style>
```

## CSS 盒子模型（Box Model）

CSS盒模型本质上是一个盒子，封装周围的HTML元素，包括四部分： Margin(外边距) - 清除边框外的区域，外边距是透明的， Border(边框) - 围绕在内边距和内容外的边框， Padding(内边距) - 清除内容周围的区域，内边距是透明的， Content(内容) - 盒子的内容，显示文本和图像。

当指定一个CSS元素的宽度和高度属性时，你**只是设置内容区域**的宽度和高度。要知道，完全大小的元素，还必须添加填充，边框和边距。

下面的例子中的元素的总宽度为300px：

```html
div {
    width: 300px;
    border: 25px solid green;
    padding: 25px;
    margin: 25px;
}
```

即： 总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距

总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距

Note: 一旦为页面设置了恰当的 DTD，大多数浏览器都会按照上面的图示来呈现内容。然而 **IE 5 和 6** 的呈现却是不正确的。根据 W3C 的规范，元素内容占据的空间是由 width 属性设置的，而内容周围的 padding 和 border 值是另外计算的。不幸的是，IE5.X 和 6 在怪异模式中使用自己的非标准模型。`这些浏览器的 width 属性不是内容的宽度，而是内容、内边距和边框的宽度的总和`。虽然有方法解决这个问题。但是目前最好的解决方案是回避这个问题。也就是，不要给元素添加具有指定宽度的内边距，而是尝试将内边距或外边距添加到元素的父元素和子元素。IE8 及更早IE版本不支持设置填充的宽度和边框的宽度属性。解决IE8及更早版本不兼容问题可以在HTML页面声明 <!DOCTYPE html>即可

## CSS 边框

`border-style`属性用来定义边框的样式， `border-width` 属性为边框指定宽度， `border-color` 边框颜色， 

```html
/* 单独设置各边的样子 */
p
{
    border-top-style:dotted;
    border-right-style:solid;
    border-bottom-style:dotted;
    border-left-style:solid;
}
```

## CSS 轮廓（outline）

轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。轮廓（outline）属性指定元素轮廓的样式、颜色和宽度。

```html
<style>
p 
{
	border:1px solid red;
	outline-style:dotted;
	outline-color:#00ff00;
}
</style>
```

## CSS 外边距

CSS margin(外边距)属性定义元素周围的空间

可能的值：

* auto：设置浏览器边距。这样做的结果会依赖于浏览器
* length：定义一个固定的margin（使用像素，pt，em等）
* %：定义一个使用百分比的边距

```html
<style>
p
{
	background-color:yellow;
}
p.margin
{
	margin-top:100px;
	margin-bottom:100px;
	margin-right:50px;
	margin-left:50px;
}
</style>
```

## CSS padding (填充)

CSS padding（填充）是一个简写属性，定义元素边框与元素内容之间的空间，即上下左右的内边距

可能的值：

* length：定义一个固定的margin（使用像素，pt，em等）
* %：定义一个使用百分比的边距

## CSS 分组和嵌套

> 分组选择，为了减少代码，把样式相同的分组

也就是说：

```html
h1
{
    color:green;
}
h2
{
    color:green;
}
p
{
    color:green;
}
```

可以简记为：

```html
h1,h2,p
{
    color:green;
}
```

> 嵌套：适用于选择器内部的选择器(就是一种组合)

example:

* p{ }: 为所有 p 元素指定一个样式。
* .marked{ }: 为所有 class="marked" 的元素指定一个样式。
* .marked p{ }: 为所有 class="marked" 元素内的 p 元素指定一个样式。
* p.marked{ }: 为所有 class="marked" 的 p 元素指定一个样式。

## CSS 尺寸

height	设置元素的高度。
line-height	设置行高。
max-height	设置元素的最大高度。
max-width	设置元素的最大宽度。
min-height	设置元素的最小高度。
min-width	设置元素的最小宽度。
width	设置元素的宽度。

## CSS Display（显示）与 Visibility（可见性）

display属性设置一个元素应如何显示，visibility属性指定一个元素应可见还是隐藏。

隐藏一个元素可以通过把display属性设置为**none**，或把visibility属性设置为**hidden**。但是请注意，这两种方法会产生不同的结果。

`visibility:hidden`可以隐藏某个元素，但隐藏的元素**仍需占用与未隐藏之前一样的空间**。也就是说，该元素虽然被隐藏了，但仍然会影响布局。`display:none`可以隐藏某个元素，且隐藏的元素不会占用任何空间。也就是说，该元素不但被隐藏了，而且该元素原本占用的空间也会从页面布局中消失。

CSS Display - 块和内联元素

块元素是一个元素，占用了全部宽度，在前后都是换行符。块元素的例子：`<h1>`, `<p>`, `<div>`
内联元素只需要必要的宽度，不强制换行。内联元素的例子：`<span>`, `<a>`

把列表项显示为内联元素：

```html
li{display:inline;}
```

把span元素作为块元素：

```html
span {display:block;}
```

Note: 注意：变更元素的显示类型看该元素是如何显示，它是什么样的元素。例如：一个内联元素设置为display:block是不允许有它内部的嵌套块元素

## CSS Position (定位)

position 属性指定了元素的定位类型。position属性的5个值：static，relative，fixed, absolute, sticky

> static

HTML 元素的默认值，即没有定位，遵循正常的文档流对象。

> fixed

元素的位置相对于浏览器窗口是固定位置。即使窗口是滚动的它也不会移动。Fixed定位使元素的位置与文档流无关，因此不占据空间。Fixed定位的元素可能和其他元素重叠。

Note： Fixed 定位在 IE7 和 IE8 下需要描述 !DOCTYPE 才能支持。

> relative

相对定位元素的定位是相对其正常位置。相对定位元素经常被用来作为绝对定位元素的容器块。可能和其他元素重叠。

> absolute 

绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于`<html>`。absolute 定位使元素的位置与文档流无关，因此不占据空间。absolute 定位的元素和其他元素重叠。

> sticky

所以可以把它称之为粘性定位。position: sticky; 基于用户的滚动位置来定位。粘性定位的元素是依赖于用户的滚动，在 position:relative 与 position:fixed 定位之间切换。它的行为就像 position:relative; 而当页面滚动超出目标区域时，它的表现就像 position:fixed;，它会固定在目标位置。元素定位表现为在跨越特定阈值前为相对定位，之后为固定定位。

这个特定阈值指的是 top, right, bottom 或 left 之一，换言之，指定 top, right, bottom 或 left 四个阈值其中之一，才可使粘性定位生效。否则其行为与相对定位相同。

Note: Internet Explorer, Edge 15 及更早 IE 版本不支持 sticky 定位。 Safari 需要使用 -webkit- prefix (查看以下实例)。

Example：小球不出框，永远显示的条幅

> 重叠元素的顺序

元素的定位与文档流无关，所以它们可以覆盖页面上的其它元素。`z-index`属性指定了一个元素的堆叠顺序（哪个元素应该放在前面，或后面）。一个元素可以有正数或负数的堆叠顺序：

```html
img
{
    position:absolute;
    left:0px;
    top:0px;
    z-index:-1;
}
```

具有更高堆叠顺序的元素总是在较低的堆叠顺序元素的前面。如果两个定位元素重叠，没有指定z - index，最后定位在HTML代码中的元素将被显示在最前面。

## CSS 布局 Overflow

CSS overflow 属性可以控制内容溢出元素框时在对应的元素区间内添加滚动条。

overflow属性有以下值：

* visible	默认值。内容不会被修剪，会呈现在元素框之外。
* hidden	内容会被修剪，并且其余内容是不可见的。
* scroll	内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。
* auto	如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。
* inherit	规定应该从父元素继承 overflow 属性的值。

注意:overflow 属性只工作于指定高度的块元素上。
注意: 在 OS X Lion ( Mac 系统) 系统上，滚动条默认是隐藏的，使用的时候才会显示 (设置 "overflow:scroll" 也是一样的)。

example:

```html
<style>
#overflowTest {
    background: #4CAF50;
    color: white;
    padding: 15px;
    width: 80%;
    height: 100px;
    overflow: scroll;
    border: 1px solid #ccc;
}
</style>

<div id="overflowTest">
<p> ... </p>
</div>
```

## CSS Float (浮动)

CSS 的 Float（浮动），会使元素向左或向右移动，其周围的元素也会重新排列。Float（浮动），往往是用于图像，但它在布局时一样非常有用。

元素的水平方向浮动，意味着元素只能左右移动而不能上下移动。一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。浮动元素之后的元素将围绕它。浮动元素之前的元素将不会受到影响。如果图像是右浮动，下面的文本流将环绕在它左边。

> 这样就能实现图片放置于最右的功能

```html
img
{
    float:right;
}
```

如果你把几个浮动的元素放到一起，如果有空间的话，它们将彼此相邻。而且还可以根据浏览器的宽度动态调整

清除浮动 - 使用 clear

元素浮动之后，周围的元素会重新排列，为了避免这种情况，使用 clear 属性。
clear 属性指定元素两侧不能出现浮动元素。也就是说在换行的时候，新的文字应该使用clear，免得新的一行字黏上前面的浮动图片

## CSS 布局 - 水平 & 垂直对齐

要水平居中对齐一个元素(如 <div>), 可以使用 margin: auto;

> 居中对齐

```html
.center {
    margin: auto;
    width: 50%;
    border: 3px solid green;
    padding: 10px;
}
```

Note: 如果没有设置 `width` 属性(或者设置 100%)，居中对齐将不起作用

> 还可以使用 position: absolute; 属性来对齐元素:

```html
.right {
    position: absolute;
    right: 0px;
    width: 300px;
    border: 3px solid #73AD21;
    padding: 10px;
}
```

## CSS 组合选择符

* 后代选择器(以空格分隔)
* 子元素选择器(以大于号分隔）
* 相邻兄弟选择器（以加号分隔）
* 普通兄弟选择器（以破折号分隔）

> 后代选择器

后代选择器用于选取某元素的后代元素。

example:

```html
div p
{
  background-color:yellow;
}
```

这样设置之后，所有在`<div>`里的`<p>`都带有黄色的背景颜色

> 子元素选择器

子元素选择器（Child selectors）只能选择作为某元素子元素的元素

```html
div>p
{
  background-color:yellow;
}
```

这样只有div中只有p的会有黄色背景，`<span><p>`都不行

> 相邻兄弟选择器

相邻兄弟选择器（Adjacent sibling selector）可选择紧接在另一元素后的元素，且二者有相同父元素。如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。

```html
div+p
{
  background-color:yellow;
}
```

在一个`<div></div>` 结束之后，出现的下一个连着的`<p>`会被赋予黄色背景

> 后续兄弟选择器

后续兄弟选择器选取所有指定元素之后的相邻兄弟元素。即选取了所有 `<div>` 元素之后的所有相邻兄弟元素 `<p> `

```html
div~p
{
    background-color: yellow;
}
```

## CSS 伪类

CSS伪类是用来添加一些选择器的特殊效果。

伪类的语法：

`selector:pseudo-class {property:value;}`

CSS类也可以使用伪类：

`selector.class:pseudo-class {property:value;}`

> anchor伪类

在支持 CSS 的浏览器中，链接的不同状态都可以以不同的方式显示

```html
a:link {color:#FF0000;} /* 未访问的链接 */
a:visited {color:#00FF00;} /* 已访问的链接 */
a:hover {color:#FF00FF;} /* 鼠标划过链接 */
a:active {color:#0000FF;} /* 已选中的链接 */
```

Note：伪类的名称不区分大小写。

> 伪类与CSS类

伪类可以与 CSS 类配合使用：

a.red:visited {color:#FF0000;}
 
<a class="red" href="css-syntax.html">CSS 语法</a>

> CSS :first-child 伪类

您可以使用 :first-child 伪类来选择父元素的第一个子元素。

注意：在IE8的之前版本必须声明<!DOCTYPE> ，这样 :first-child 才能生效。

Example：匹配第一个 `<p>` 元素

```html
<style>
p:first-child
{
	color:blue;
} 
</style>
```

这样写之后只有第一个`<p>`的字体会变成蓝色

Example: 匹配所有<p> 元素中的第一个 <i> 元素

```html
p > i:first-child
{
    color:blue;
}
```
style 里这样写了之后，所有`<p>`中的第一个`<i>`都会变蓝

Example: 匹配所有作为第一个子元素的 <p> 元素中的所有 <i> 元素

```html
p:first-child i
```

> CSS - :lang 伪类

:lang 伪类使你有能力为不同的语言定义特殊的规则

注意：IE8必须声明<!DOCTYPE>才能支持;lang伪类。

Example:

```html
<style>
q:lang(no)
{
	quotes: "~" "~";
}
</style>
```

在声明之后，所有`<q lang="no">`都会被显示成是`~`

> CSS: focus伪类

Example:

```html
<style>
input:focus
{
	background-color:yellow;
}
</style>
```

这样设置之后，`<input type="text" name="fname" />`会在点击框框的时候背景变成黄色


## CSS伪元素

CSS伪元素是用来添加一些选择器的特殊效果。

伪元素的语法：

`selector:pseudo-element {property:value;}`

CSS类也可以使用伪元素：

`selector.class:pseudo-element {property:value;}`

> :first-line 伪元素

"first-line" 伪元素用于向文本的首行设置特殊样式。

在下面的例子中，浏览器会根据 "first-line" 伪元素中的样式对 p 元素的第一行文本进行格式化：

```
p:first-line 
{
    color:#ff0000;
    font-variant:small-caps;
}
```

对于这个里面每一个`<p>`的第一行都会改变字体颜色

`first-line`可以有的属性：
* font properties
* color properties 
* background properties
* word-spacing
* letter-spacing
* text-decoration
* vertical-align
* text-transform
* line-height
* clear

> : first-letter 伪元素

"first-letter" 伪元素用于向文本的首字母设置特殊样式


> 伪元素可以结合CSS类： 

```html
p.article:first-letter {color:#ff0000;}

<p class="article">文章段落</p>
```

上面的例子会使所有 class 为 article 的段落的首字母变为红色

Note: 可以结合多个伪元素来使用。

> CSS - :before 伪元素

":before" 伪元素可以在元素的内容前面插入新内容。

下面的例子在每个 <h1>元素前面插入一幅图片：

```html
h1:before 
{
    content:url(smiley.gif);
}
```

同理还有after伪元素

## CSS导航栏

熟练使用导航栏，对于任何网站都非常重要。

使用CSS你可以转换成好看的导航栏而不是枯燥的HTML菜单。

### 导航栏=链接列表

作为标准的HTML基础一个导航栏是必须的。在我们的例子中我们将建立一个标准的HTML列表导航栏。

导航条基本上是一个链接列表，所以使用 `<ul>` 和 `<li>` 元素非常有意义：

```html
<ul>
  <li><a href="#home">主页</a></li>
  <li><a href="#news">新闻</a></li>
  <li><a href="#contact">联系</a></li>
  <li><a href="#about">关于</a></li>
</ul>
```

在这里加入对ul元素的描述，从列表中删除边距和填充：

```html
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
}
```

* list-style-type:none - 移除列表前小标志。一个导航栏并不需要列表标记
* 移除浏览器的默认设置将边距和填充设置为0

> 垂直导航栏

上面的代码，我们只需要 <a>元素的样式，建立一个垂直的导航栏：

```html
<style>
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    width: 200px;
    background-color: #f1f1f1;
}
 
li a {
    display: block;
    color: #000;
    padding: 8px 16px;
    text-decoration: none;
}

/* 鼠标移动到选项上修改背景颜色 */
li a:hover {
    background-color: #555;
    color: white;
}
</style>

<body>
<ul>
<li><a href="#home">主页</a></li>
</ul>
</body>
```

* `display:block` - 显示块元素的链接，让整体变为可点击链接区域（不只是文本），它允许我们指定宽度
* `width:60px` - 块元素默认情况下是最大宽度。我们要指定一个60像素的宽度

Note: 请务必指定 `<a>` 元素在垂直导航栏的的宽度。如果省略宽度，IE6可能产生意想不到的效果。

> 激活/当前导航栏条实例

在点击了选项后，我们可以添加 "active" 类来标准哪个选项被选中：

```html
.active {
    background-color: #4CAF50;
    color: white;
}
```

当前被选中的项就会展现`.active`里面的内容

> 创建链接并添加边框

可以在 `<li>` or `<a>` 上添加text-align:center 样式来让链接居中。

可以在 border `<ul>` 上添加 border 属性来让导航栏有边框。如果要在每个选项上添加边框，可以在每个 `<li>` 元素上添加border-bottom :

```html
ul {
    border: 1px solid #555;
}
 
li {
    text-align: center;
    border-bottom: 1px solid #555;
}
 
li:last-child {
    border-bottom: none;
}
```

