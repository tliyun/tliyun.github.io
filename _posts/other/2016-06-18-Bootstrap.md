---
layout: post
title:  "Bootstrap学习（一）"
date:   2016-06-18
---

>Bootstrap是基于HTML、CSS和JAvaScript的前端框架，它灵活简洁，使得web开发更加方便快捷。

#### 一、Bootstrap的基本内容

下载Bootstrap文件，将jquery.js、bootstrap.css和bootstrap.js引入html文件中，就可以使用bootstrap了。如下面的HTML模板：

	<!DOCTYPE html>  
	<html>  
    <head>  
    <title>Bootstrap 101 Template</title>  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <!-- Bootstrap -->  
    <link href="css/bootstrap.min.css" rel="stylesheet" media="screen">  
    </head>  
    <body>  
    <h1>Hello, world!</h1>  
    <script src="http://code.jquery.com/jquery.js"></script>  
    <script src="js/bootstrap.min.js"></script>  
    </body>  
    </html>

Bootstrap主要包括以下几部分：

  1、基本结构（脚手架）  
Bootstrap提供了带有栅格系统、链接样式、重置背景等的全局性样式文件。

  2、基本样式  
Bootstrap自带以下特性：全局的CSS设置、定义基本的 HTML 元素样式、可扩展的 class，以及一个先进的网格系统。

  3、功能组件  
Bootstrap 包含了十几个可重用的组件，用于创建图像、下拉菜单、导航、警告框、弹出框等等。

  4、JavaScript插件  
Bootstrap 包含了十几个自定义的 jQuery 插件。您可以直接包含所有的插件，也可以逐个包含这些插件。

  5、定制组件  
可以定制 Bootstrap 的组件、LESS 变量和 jQuery 插件来得到自己的版本。

#### 二、Bootstrap基本结构

##### 一、全局样式
1、必须使用HTML5文档类型  
2、排版和链接  
  Bootstrap 为屏幕、排版和链接设置了基本的全局样式。  
3、用Normalize重置样式
  
##### 二、栅格系统
1、默认栅格系统  
Bootstrap默认的栅格系统为12列 ，形成一个940px宽的容器。如果加入响应式布局CSS文件，栅格系统会自动根据可视窗口的宽度从724px到1170px进行动态调整。在可视窗口低于767px宽的情况下，列将不再固定并且会在垂直方向堆叠。  
对于简单的两列式布局，创建一个 .row 容器，并在容器中加入合适数量的 .span* 列即可。由于默认是12列的栅格，所有 .span* 列所跨越的栅格数之和最多是12，或者等于其父容器的栅格数（可以嵌套）。 
 
2、流式栅格系统  
流式栅格系统对每一列的宽度使用百分比而不是像素数量。它和固定栅格系统一样拥有响应式布局的能力，这就保证它能对不同的分辨率和设备做出适当的调整。  
将 .row 替换为 .row-fluid 就能让任何一行“流动”起来。应用于每一列的类不用改变，这样能方便的在流式与固定栅格之间切换。
流式山歌的偏移定义方式和固定网格系统相同，即给任何想偏移的列添加 .offset* 即可。  

##### 三、基本布局
1、固定布局  
提供了一个通用的固定宽度(也可以变为响应式)的布局方式，仅仅定义div的类为container即可。  
2、流式布局  
定义div的类为container-fluid可以创建一个流式页面，如以下代码可以创建一个流式两列的页面。

    <div class="container-fluid">
    <div class="row-fluid">
    <div class="span2">
      <!--Sidebar content-->
    </div>
    <div class="span10">
      <!--Body content-->
    </div>
    </div>
    </div>  



##### 四、响应式设计  
Bootstrap在默认情况下是没有引入响应式特性的，因为不是任何情况都需要使用到。通过在文档中的 <head> 标签里添加合适的meta标签并引入一个额外的样式表即可启用响应式CSS。  

    <link href="assets/css/bootstrap-responsive.css" rel="stylesheet">  


Media queries（媒体查询）允许在一些条件基础上自定义CSS 例如：—ratios、widths、display type, etc— 但通常都是围绕着 min-width 和 max-width 这两者。

	/* 大屏幕 */  
	@media (min-width: 1200px) { ... }  
 
	/* 平板电脑和小屏电脑之间的分辨率 */
	@media (min-width: 768px) and (max-width: 979px) { ... }
 
	/* 横向放置的手机和竖向放置的平板之间的分辨率 */
	@media (max-width: 767px) { ... }
 
	/* 横向放置的手机及分辨率更小的设备 */
	@media (max-width: 480px) { ... }


为了更快的针对移动设备做开发, 下面列出的辅助class用于针对不同设备显示和隐藏内容。下表是可用的class列表, 以及它们在各个media query布局下的效果。这些class可以在 responsive.less 文件中找到。

![](http://i.imgur.com/wuIE9RD.png)

#### 三、Bootstrap基本样式

##### 一、排版

1、标题  
HTML中定义的所有标题标签, 从h1 到 h6 都是可用的。  

2、Body主体布局  
Bootstrap定义的全局 font-size 是 14px，line-height 是 20px。另外，对 (段落)还定义了1/2行高(默认为10px)的底部外边距(margin)属性。可以通过添加 .lead 让段落突出显示。  

3、强调和对齐  
对于不需要强调的inline或block类型的文本，可以使用small标签。使用strong标签可以加粗强调一段文本，使用em标签可以斜体强调一段文本。

使用muted、text-warning、text-error、text-info和text-success等类可以通过不同颜色来表示强调。  

使用text-left、text-center和text-right可以分别将文字左对齐、居中和右对齐。

4、列表  
和HTML中的定义一样，使用ol和ul标签分别表示有序和无序列表。使用list-style类表示无样式列表，使用inline-block类表示行内列表，即让列表水平排列一行。

5、描述  
使用dl、dt和dd标签对一个列表（条目）进行关联描述。使用dl-horizontal类使dl中的每个条目和其描述一对一水平显示。

##### 二、代码

可以使用code标签内嵌一段代码，使用pre标签展示多行代码。

##### 三、表格

table标签中可以使用table类增加基本样式，即很少的内边距和水平分割线。

使用table-striped类可以为表格增加斑马纹样式。

使用table-bordered类可以为表格增加边框和圆角。

使用table-hover类可以为表格中每一行赋予鼠标悬停样式。

使用table-condensed类可以使每个单元格的内边距减半，表格更紧凑。

使用情景类为表格添加颜色。如下表所示：

![](http://i.imgur.com/1C2USPI.png)

还有一些其他的表格标签也受支持，如下表：

![](http://i.imgur.com/fQxI86v.png)

##### 四、表单

1、默认样式

无需对form标签添加任何类或改变标签结构，每个单独的表单控件都已经被赋予了样式。默认是堆叠、label左侧对齐并在控件之上。

2、搜索表单

为表单增加.form-search类，并为input标签增加.search-query类，可将输入框变成圆角状。

3、行内表单

为表单增加.form-inline类， 结果是一个压缩型排列的表单，其中label左侧对齐、控件为inline-block类型，各个标签水平排布。

4、水平表单

右侧对齐并且左侧浮动的label和控件排列在同一行。这需要对默认的表单格式做修改：

为表单添加.form-horizontal类；将label和控件包裹在.control-group中；为label添加.control-label类；将任何相关的控件包裹在.controls中，以确保最佳的对齐。

5、支持的表单控件

输入框（input）:大部分常用的表单控件、文本输入控件。包括所有HTML5所支持的：text、password、datetime、 datetime-local、date、 month、time、week、number、email、url、search、tel 和 color。

文本域（textarea）:此表单控件支持多行文本。可根据需要修改rows属性。

复选框（type="checkbox"）和单选框（type="radio"）:复选框是用于在一个列表中选择一个或多个选项，而单选框是在众多选择中选择一个选项。为复选框或单选框控件添加inline类，可以使他们排列在同一行。

下拉框（select）：默认一次显示一个选项。可使指定multiple="multiple"属性一次显示多个选项。

6、扩展表单控件（input-prepend类）

前缀和附加输入框：将add-on和input进行组合，在input前面或者后面添加span标签并添加add-on类属性，可以将文本放到输入框前或后面。

	<div class="input-prepend">
    <span class="add-on">@</span>
    <input class="span2" id="prependedInput" type="text" placeholder="Username">
    </div>
    <div class="input-append">
    <input class="span2" id="appendedInput" type="text">
    <span class="add-on">.00</span>
    </div>  

附加按钮的输入框：用btn类代替span标签即可将一个（或两个）按钮添加到输入框前或后。

按钮下拉菜单：点击按钮出现下拉菜单，使用btn和dropdown-toggle类实现，可以添加到输入框前或后。

搜索表单：使用search-query类实现。

7、表单控件大小

使用input-mini、input-small、input-medium、input-large、input-large、input-xxlarge等类可以改变控件的相对大小；也可以使用span1 到span12类将控件的大小对齐到网格大小。

##### 五、按钮

任何赋予btn类的页面元素都会显示按钮样式。  

![](http://i.imgur.com/Z9njLvt.png)

添加btn-large、btn-small 或 btn-mini类即可改变按钮大小。通过添加btn-block类，可使按钮变为块级元素，同时会填充整个父级元素。添加disabled类属性可以禁用按钮。

##### 六、图标

下面展示的140个图标均提供了深灰色（默认）和白色两种颜色。由Glyphicons提供。  

![](http://i.imgur.com/W0EaUdX.png)

![](http://i.imgur.com/64FqSTw.png)
