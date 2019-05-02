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
