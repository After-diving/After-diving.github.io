# Applied Accessibility

## img标签

```html
<img src="图片链接/地址" alt="图片加载失败后显示的文本内容">
```

`alt`属性中的文本作为备用文字描述了图片的内容，这可以帮助用户在图片加载失败或者不可见的情况下理解图片内容，也有助于搜索引擎理解图片内容，并将其加入到搜索结果中.

良好的`alt`文本可以简明扼要地描述图片信息，所以你应该为图片添加`alt`属性。另外，HTML5 标准也在考虑强制要求对图片添加`alt`属性。(可以将其设置为空,即`alt=""`或`src=""`)

## h1-h6表层提层次

页面中的标题标签也应该是有序的，并且能表明内容的层次关系。

标题标签之间以及标签本身都应语义化，不应仅仅为了获得不同字号而使用不同级别的标题标签。

*语义化*：标签名能准确地表达它所含内容的信息类型。

在使用中，相同级别（或者更高级别）的标题标签用于开启新的章节，低一级别的标题标签用于开启上一级标题标签的子小节。

## main元素包裹主题内容

HTML5 添加了诸如`main`、`header`、`footer`、`nav`、`article`、`section`等大量新标签，这些新标签为开发人员提供更多的选择和辅助特性。

默认情况下，浏览器呈现这些新标签的方式与`div`相似。然而，合理地使用它们，可以使你的标签更加的语义化。辅助技术（如：屏幕阅读器）可以通过这些标签为用户提供更加准确的、易于理解的页面信息。

`main`标签用于呈现网页的主体内容，且每个页面只能有一个。这意味着它只应包含与页面中心主题相关的信息，而不应包含如导航连接、网页横幅等可以在多个页面中重复出现的内容。

`main`标签的语义化特性可以使辅助技术快速定位到页面的主体。有些页面中有 “跳转到主要内容” 的链接，使用`main`标签可以使辅助设备自动获得这个功能。

## article元素包裹文章内容

默认情况下，浏览器呈现这些新标签的方式与`div`相似。然而，合理地使用它们，可以使你的标签更加的语义化。辅助技术（如：屏幕阅读器）可以通过这些标签为用户提供更加准确的、易于理解的页面信息。

`main`标签用于呈现网页的主体内容，且每个页面只能有一个。这意味着它只应包含与页面中心主题相关的信息，而不应包含如导航连接、网页横幅等可以在多个页面中重复出现的内容。

`main`标签的语义化特性可以使辅助技术快速定位到页面的主体。有些页面中有 “跳转到主要内容” 的链接，使用`main`标签可以使辅助设备自动获得这个功能。

**请注意`section`和`div`的区别：**
`section`也是一个 HTML5 新标签，与`article`标签的语义含义略有不同。`article`用于独立的、完整的内容，而`section`用于对与主题相关的内容进行分组。它们可以根据需要嵌套着使用。举个例子：如果一本书是一个`article`的话，那么每个章节就是`section`。当内容组之间没有联系时，可以使用`div`。

```html
<div> - 内容组
<section> - 有联系的内容组
<article> - 独立完整的内容
```

## header元素让屏幕阅读器更易导航

`header`也是一个具有语义化的、提升页面可访问性的 HTML5 标签。它可以为父级标签呈现简介信息或者导航链接，适用于那些在多个页面顶部重复出现的内容。

与`main`类似，`header`的语义化特性也可以使辅助技术快速定位到它的内容。

<b style="color:#FF007D;">注意：</b>
`header`用在 HTML 文档的`body`标签中。这点与包含页面标题、元信息的`head`标签不同。

## nav元素导航

`nav`也是一个具有语义化特性的 HTML5 标签，用于呈现页面中的主导航链接。它可以使屏幕阅读器快速识别页面中的导航信息。

对于页面底部辅助性质的站点链接，不需要使用`nav`，用`footer`

```html
<nav>
    <ul>
        <li><a href="#stealth">导航A</a></li>
        <li><a href="#combat">导航B</a></li>
        <li><a href="#weapons">导航C</a></li>
    </ul>
</nav>
```

<nav style="">
    <ul>
        <li><a href="#stealth">导航A</a></li>
        <li><a href="#combat">导航B</a></li>
        <li><a href="#weapons">导航C</a></li>
    </ul>
</nav>

## footer元素让屏幕阅读器更易导航

与`header`和`nav`类似，`footer`也具有语义化特性，可以使辅助设备快速定位到它。它位于页面底部，用于呈现版权信息或者相关文档链接。

## audio 元素提高音频内容可访问

HTML5 的`audio`标签用于呈现音频内容，它也具有语义化特性。可以在`audio`上下文中为音频内容添加文字说明或者字幕链接.

`audio`支持`controls`属性，可以使浏览器为音频提供具有开始、暂停等功能的播放控件。`controls`属性是一个布尔属性，只要这个属性出现在`audio`标签中，浏览器就会开启播放控件。

```html
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```

<b style="color:#FF007D;">注意：</b>
多媒体内容通常同时包含音频与视频部分，它需要同步音频与字幕，以使视觉或听觉障碍用户可以获取它的内容。一般情况下，网页开发者不需要创建音频与字幕，但是需要将它们添加到多媒体中

## figure元素提高图表可访问性

HTML5 引入了`figure`标签以及与之相关的`figcaption`标签。它们一起用于展示可视化信息（如：图片、图表）及其标题。这样通过语义化对内容进行分组并配以用于解释`figure`的文字，可以极大的提升内容的可访问性。

```html
<figure>
  <img src="地址,链接" alt="文字说明">
  <br>
  <figcaption>
    图片下的文字
  </figcaption>
</figure>
```

<b style="color:#FF007D;">注意：</b>`figcaption`包含在`figure`标签中，并且可以与其他标签组合使用.

## label元素提高表单可访问性

`label`标签用于呈现特定表单控件的文本，通常是选项的名称。这些文本代表了选项的含义，使表单具有更好的可读性。`label`标签的`for`属性指定了与`label`绑定的表单控件，并且屏幕阅读器也会读取`for`属性。

`for`属性的值必须与表达控件的`id`属性的值相同。

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
</form>
```

## 单选按钮包裹在 fieldset 元素中

使用`fieldset`标签将单选按钮组包含在里面就可以实现单选按钮成组出现，用户必须其中选择一项，通常还会使用`legend`标签来为单选按钮组提供文字说明。

```html
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one">
    <label for="one">Choice One</label><br>
    <input id="two" type="radio" name="items" value="two">
    <label for="two">Choice Two</label><br>
    <input id="three" type="radio" name="items" value="three">
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```

<form>
 <fieldset>
  <legend>Choose one of these three items:</legend>
  <input id="one" type="radio" name="items" value="one">
  <label for="one">Choice One</label><br>
  <input id="two" type="radio" name="items" value="two">
  <label for="two">Choice Two</label><br>
  <input id="three" type="radio" name="items" value="three">
  <label for="three">Choice Three</label>
 </fieldset>
</form>

## 日期选择器

表单中经常出现`input`标签，它可以用来创建多种表单控件。它的`type`属性指定了所要创建的`input`标签类型。

在之前已经见过`text`与`submit`类型的`input`标签，HTML5 引入了`date`类型来创建时间选择器。依赖于浏览器的支持，当点击`input`标签时，时间选择器会显示出来，这可以让用户填写表单更加容易。

对于旧版本的浏览器，`type`属性的默认值是`text`。这种情况下，可以利用`label`标签或者占位文本来提示用户`input`标签的输入类型为日期。

```html
<label for="input1">Enter a date:</label>
<input type="date" id="input1" name="input1">
```

HTML5 还引入了`time`标签与`datetime`属性来标准化时间。`time`是一个行内标签，用于在页面中呈现日期或时间，而`datetime`属性保存了日期的有效格式，辅助设备可以访问这个值。通过标准化时间格式，即使时间在文本中是以非正式的或口语化的形式编写，辅助设备依然可以获取准确的时间和日期。

```html
<p>Master Camper Cat officiated the cage match between Goro and Scorpion <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.</p>
```

## 仅对屏幕阅读器可见

如果我们需要在页面中添加一些只对屏幕阅读器可见的内容时，CSS 可以提升页面的可访问性。当信息以可视化形式（如：图表）展示，而屏幕阅读器用户需要一种替代方式（如：表格）来获取信息时，就会出现这种情况。CSS 被用来将这些仅供屏幕阅读器使用的信息定位到浏览器可见区域之外.

```html
</style>
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}</style>
```

- `display: none;`或`visibility: hidden;`会把内容彻底隐藏起来，对于屏幕阅读器也不例外。

- 如果把值设置为 0px，如`width: 0px; height: 0px;`，意味着让元素脱离文档流，这样做也会让元素被屏幕阅读器忽略。

## 高对比度提高文本可读性

低对比度的前景色与背景色会使文本难以阅读。足够的对比度可以提高内容的可读性，但是怎样的对比度才算是 “足够” 的？

Web 内容无障碍指南（WCAG）建议正常文本的对比度至少为 4.5 : 1。对比度是通过比较两种颜色的相对亮度值来计算的，其范围是从相同颜色的 1 : 1（无对比度）到白色与黑色的最高对比度 21 : 1。网上有很多可以帮助你计算对比度的工具。

## accesskey 属性快速导航

HTML 提供`accesskey`属性，用于指定激活标签或者使标签获得焦点的快捷键，这可以使键盘用户的导航更加有效。

HTML5 允许在任何标签上使用这个属性。该属性对于交互类标签（如链接、按钮、表单控件等）十分有用。

```html
<button accesskey="b">Important Button</button>
```

<button accesskey="b">important Button</button>

##  tabindex 添加键盘焦点

HTML 的`tabindex`属性有三个不同与标签焦点的功能。当它在标签上时，表示标签可以获得焦点。它的值可以是零、负整数及正整数，并决定了标签的行为。

当用户在页面中使用 tab 键时，有些标签，如：链接、表单控件，可以自动获得焦点。它们获得焦点的顺序与它们出现在文档流中的顺序一致。我们可以通过将`tabindex`属性值设为 0，来给其他标签赋予相同的功能，如：`div`、`span`、`p`等。

`tabindex`属性还可以指定标签的 tab 键顺序，将它的值设置为大于或等于 1 就可以实现这个功能。

`tabindex`属性值为 1 的标签将首先获得键盘焦点，然后焦点将按照指定的`tabindex`的值（如：2，3 等）的顺序进行移动，直到回到默认的或`tabindex`值为 0 的标签上，如此循环。举个例子：

```css
  <style>
  p:focus {
    background-color: yellow;
  }
  </style>
<div tabindex="0">I need keyboard focus!</div>
```

<b style="color:#FF007D;">注意：</b>
`tabindex`属性值为负整数（通常为 -1）的标签也是有焦点的，只是不可以通过 tab 键来获得焦点。这种方法通常用于以编程的方式使内容获得焦点（如：激活用于弹出框的`div`标签, 使用`tabindex`属性可以使 CSS 伪类`:focus`在`p`标签上生效。）

##  Responsive Web Design

### 创建媒介查询

媒体查询是 CSS3 中引入的一项新技术，它可以根据不同的可视窗口大小显示不同的布局。可视窗口是用户在网页上的可见区域，根据访问网站的设备不同而不同。

媒体查询由媒体类型组成，如果媒体类型与展示网页的设备类型匹配，则应用对应的样式。你可以在媒体查询中用上你想用的选择器和样式。	下面是一个媒体查询的例子，当设备宽度小于或等于 100px 时返回内容：

```css
@media (max-width: 100px) { /* CSS Rules */ }
```

以下定义的媒体查询，是当设备高度大于或等于 350px 时返回内容：

```css
@media (min-height: 350px) { /* CSS Rules */ }
```

只有当媒体类型与当前设备匹配时，才应用媒体查询中的 CSS。

### 让图片根据设备尺寸自如响应

用 CSS 来让图片自适应其实很简单。不要使用绝对单位：

```
img { width: 720px; }
```

你应该使用：

```css
img {
  max-width: 100%;
  display: block;
  height: auto;
}
```

`max-width`属性能让图片以 100% 的最大宽度适应其父容器的宽度，但图片不会拉伸得比原始宽度还宽。将 `display`属性设置为 `block`可以让 image 标签从内联元素（默认值）更改为块级元素。设置 `height`属性为 auto 保持图片的原始宽高比。

### 视网膜图片

为优化图片在高分辨率设备下的显示效果，最简单的方式是定义它们的 `width`和 `height`值为源文件宽高的一半。

这是一个图片宽高设置为源文件一半的例子：

```css
<style>
  img { height: 250px; width: 250px; }
</style>
<img src="coolPic500x500" alt="一张高质量的图片">
```

### 依设备尺寸排版

除了用 `em`或 `px`去设置文本大小, 你还可以用视窗单位来做响应式排版。视窗单位还有百分比，它们都是相对单位，但却基于不同的参照物。视窗单位相对于设备的视窗尺寸 (宽度或高度) ，百分比是相对于父级元素的大小。

四个不同的视窗单位分别是：

- `vw`：如 `10vw`的意思是视窗宽度的 10%。
- `vh：`如 `3vh`的意思是视窗高度的 3%。
- `vmin：`如 `70vmin`的意思是视窗中较小尺寸的 70% (高度 VS 宽度)。
- `vmax：`如 `100vmax`的意思是视窗中较大尺寸的 100% (高度 VS 宽度)。

## CSS弹性盒子

### display：flex定位两个盒子

只要在一个元素的 CSS 中添加`display: flex;`，就可以使用其他 flex 属性来构建响应式页面了。

```html
<style>
  #box-container {
    height: 500px;
    display:flex;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 50%;
    height: 50%;
  }
  #box-2 {
    background-color: orangered;
    width: 50%;
    height: 50%; 
  }
</style>
<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

###  flex-direction 属性创建一行

添加了`display: flex`的元素会成为 flex 容器。只要把`flex-direction`属性添加到父元素，并设置其为 row 或 column 即可轻易横或竖排列它的子元素。设为 row 可以让子元素水平排列，column 可以让子元素垂直排列。

`flex-direction`的其他可选值还有 row-reverse 和 column-reverse。

<b style="color:#FF007D;">注意：</b>
`flex-direction`的默认值为 row。

### justify-content 属性对齐元素

flex 容器里的 flex 子元素有时不能充满整个容器，所以我们需要告诉 CSS 如何以特定方案排列和调整 flex 子元素。幸运的是，我们有`justify-content`属性处理这个问题。

<img src="https://www.w3.org/TR/css-flexbox-1/images/flex-direction-terms.svg" alt="flex元素图形描述" style="zoom:80%">

把 flex 容器设为一个行，它的子元素会从左到右逐个排列，把 flex 容器设为一个列，它的子元素会从上到下逐个排列。子元素排列的方向被称为 **main axis（主轴）**。对于行，主轴水平贯穿每一个项目；对于列，主轴垂直贯穿每一个项目。

关于 flex 子元素在主轴排列方式，可以选择以下值：其中一个很常用的是`justify-content: center;`，可以让 flex 子元素排列在 flex 容器中间。其他可选值还有：

- `flex-start`：从 flex 容器的前端开始排列项目。对行来说是把项目都靠左放，对于列是把项目都靠顶部放。
- `flex-end`：从 flex 容器的后端开始排列项目。对行来说是把项目都靠右放，对于列是把项目都靠底部放。
- `space-between`：项目间保留一定间距地在主轴排列。第一个和最后一个项目会被挤到容器边沿。例如，在行中第一个项目会紧贴着容器左侧，最后一个项目会紧贴着容器右侧，然后其他项目均匀排布。
- `space-around`：与`space-between`相似，但头尾两个项目不会紧贴容器边缘，空间会均匀分布在所有项目两边

###  align-items 属性对齐元素

`align-items`属性与`justify-content`类似。

`justify-content`属性使 flex 子元素沿主轴排列。行的主轴是水平线，列的主轴是垂直线。

Flex 容器中，与主轴垂直的叫做 **cross axis（交叉轴）**。行的交叉轴是垂直的，列的交叉轴是水平的。

CSS 提供了`align-items`属性，可以用于在交叉轴调整 flex 子元素。对于行，它规定了项目在容器中应该靠上还是靠下，而对于列，就是靠左或靠右。

`align-items`的可选值包括：

- `flex-start`：从 flex 容器的前端开始排列项目。对行来说是把项目都靠顶部放，对于列是把项目都靠左放。
- `flex-end`：从 flex 容器的后端开始排列项目。对行来说是把项目都靠底部放，对于列是把项目都靠右放。
- `center`：把项目的位置调整到中间。对于行，垂直居中（项目上下方空间相等）。对于列，水平居中（项目左右方空间相等）。
- `stretch`：拉伸项目，填满 flex 容器。例如，排成行的项目从容器顶部拉伸到底部。
- `baseline`：基线对齐地排列。基线是字体相关的概念，可以认为字体坐落在基线上。

### flex-wrap 属性包裹

CSS flexbox 有一个把 flex 子元素拆分为多行（或多列）的特性。默认情况下，flex 容器会调整项目大小，把它们都塞到一起。如果是行的话，所有项目都会在一条直线上。

不过，使用`flex-wrap`属性可以使项目换行。这意味着多出来的项目会被移到新的行或列。换行发生的断点由项目和容器的大小决定。

换行方向的可选值有这些：

- `nowrap`：默认值，不换行。
- `wrap`：行从上到下排，列从左到右排。
- `wrap-reverse`：行从下到上排，列从右到左排。

### flex-shrink 属性收缩项目

`flex-shrink`属性使用之后，如果 flex 容器太小，该项目会自动缩小。当容器的宽度小于里面所有项目的宽度，项目就会自动压缩。

`flex-shrink`属性接受 number 类型的值。数值越大，与其他项目相比会被压缩得更厉害。例如，如果一个项目的`flex-shrink`为 1 ，另一个项目`flex-shrink`为 3，那么 3 的那个与另一个相比会受到 3 倍压缩。

### flex-grow 属性扩展项目

与`flex-shrink`相对的是`flex-grow`。`flex-shrink`会在容器太小时对元素作出调整。相应地，`flex-grow`会在容器太大时对元素作出调整。

如果一个项目`flex-grow`属性的值为 1，另一个`flex-grow`为 3，那么 3 的会比 1 的扩大三倍。

### flex-basis 属性设置初始大小

`flex-basis`属性指定了项目在 CSS 进行`flex-shrink`或`flex-grow`调整前的初始大小。

`flex-basis`属性的单位与其他 size 属性一致（`px`、`em`、`%`等）。如果值为`auto`，项目的大小依赖于自身内容。

### flex 短方法属性

上面几个 flex 属性有一个简写方式。`flex-grow`、`flex-shrink`和`flex-basis`属性可以在`flex`中一同设置。

例如，`flex: 1 0 10px;`会把项目属性设为`flex-grow: 1;`、`flex-shrink: 0;`以及`flex-basis: 10px;`。

属性的默认设置是`flex: 0 1 auto;`。

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    flex:2 2 150px;
    height: 200px;
  }

  #box-2 {
    background-color: orangered;
    flex:1 1 150px;
    height: 200px;
  }
</style>
<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

上面设置的属性，在容器大于 300px 时，会让`#box-1`填充倍率为`#box-2`的两倍；在容器小于 300px 时，缩小倍率为`#box-2`的两倍。300px 是两个盒子的`flex-basis`的值之和。

### order 属性重新排列项目

`order`属性告诉 CSS flex 容器里项目的顺序。默认情况下，项目排列顺序与源 HTML 文件中顺序相同。这个属性接受数字作为参数，可以使用负数。

### align-self 属性

这个属性允许你调整每个项目自己的对齐方式，而不是一次性设置全部项目。因为`float`、`clear`和`vertical-align`等调整使用的属性都不能应用在 flex 子元素，所以这个属性显得十分有用。

`align-self`的允许值与`align-items`一样，并且它会覆盖`align-items`的值。

## CSS网格

### 创建CSS网格

通过将属性`display`的值设为`grid`，使 HTML 元素变为网格容器。通过前面的操作，你可以对该容器使用与 CSS 网格（CSS Grid）相关的属性。

<b style="color:#FF007D;">注意：</b>
在 CSS 网格中，父元素称为容器（container），它的子元素称为项（items）。

### grid-template-columns 添加多列

简单地添加一个网格元素并不能取得很大的进展。你还需要明确网格的结构。在一个网格容器中使用`grid-template-columns`属性可以添加一些列，示例如下：

```css
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

上面的代码可以在网格容器中添加两列，宽度均为 50px。

`grid-template-columns`属性值的个数表示网格的列数，而每个值表示对应列的宽度。

### grid-template-rows 添加多行

使用方法同添加多列.

### 更改网格列和行的大小

在 CSS 网格中，可以使用绝对定位和相对定位单位如`px`和`em`来确定行或列的大小。下面的单位也可以使用：

`fr`：设置列或行占剩余空间的一个比例，

`auto`：设置列宽或行高自动等于它的内容的宽度或高度，

`%`：将列或行调整为它的容器宽度或高度的百分比，

```css
grid-template-columns: auto 50px 10% 2fr 1fr;
```

### grid-column-gap列之间的间距

到目前为止，在你所建立的网格中列都相互紧挨着。如果需要在列与列之间添加一些间隙，我们可以使用`grid-column-gap`：
```css
grid-column-gap: 10px;
```
这会在我们创建的所有列之间添加 10px 的空白间隙。

同样, 可以用`grid-row-gap`在两行之间添加间隙。

`grid-gap`是`grid-row-gap`和`grid-column-gap`的简写，它更方便使用。如果`grid-gap`有一个值，行与行之间和列与列之间将添加等于该值的间隙。但是，如果有两个值，第一个值将作为行间隙的高度值，第二个值是列间隙的宽度值。

```css
grid-gap:10px 20px;
```

### grid-column 来控制剩余部分

之前网格的讨论都是围绕网格容器的。`grid-column`属性是第一个用于网格项本身的属性。

网格的假想水平线和垂直线被称为线（lines）。这些线在网格的左上角从 1 开始编号，垂直线向右、水平线向下累加计数。

这是一个 3x3 网格的线条：

<img src="data:image/png;base64,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" style="zoom:80%"/>

你可以用`grid-column`属性定义网格项开始和结束的位置，进而控制每个网格项占用的列数。

示例如下：
```css
grid-column: 1 / 3;
```
这会让网格项从左侧第一条线开始到第三条线结束，占用两列。

你可以像列一样使网格项跨越多行。对于一个网格项，你可以用`grid-row`属性来确定开始和结束的水平线。

### 对齐项目

- `justify-self`**水平对齐**

在 CSS 网格中，每个网格项的内容分别位于被称为单元格（cell）的框内。你可以使用网格项的`justify-self`属性，设置其内容的位置在单元格内沿行轴对齐的方式。默认情况下，这个属性的值是`stretch`，这将使内容占满整个单元格的宽度。该 CSS 网格属性也可以使用其他的值：

`start`：使内容在单元格左侧对齐，

`center`：使内容在单元格居中对齐，

`end`：使内容在单元格右侧对齐，

- `align-self`**垂直对齐**

值同`justify-self`一样

- `justify-items` **水平对齐所有项目**
- `align-items` **垂直对齐所有项目**

### 网格划分为区域模板

将网格中的一些网格单元格组合成一个区域（area），并为该区域指定一个自定义名称。你可以通过给容器加上`grid-template-areas`来实现：

```css
grid-template-areas:
  "header header header"
  "advert content content"
  "footer footer footer";
```

上面的代码将顶部三个单元格合并成一个名为`header`的区域，将底部三个单元格合并为一个名为`footer`的区域，并在中间行生成两个区域————`advert`和`content`。

<b style="color:#FF007D;">注意：</b>
在代码中，每个单词代表一个网格单元格，每对引号代表一行。

除了自定义标签，你还能使用句点（`.`）来表示一个空单元格

### grid-area 属性

在为网格容添加区域模板后，你可以通过添加你定义的名称将网格项放入自定义区域。为此，你需要对网格项使用`grid-area`：

```css
.item1 { grid-area: header; }
```

这样，类名为`item1`的网格项就被放到了`header`区域里。这种情况下，网格项将使用整个顶行，因为这一行被名为 header 区域。

`grid-area`属性还有另一种使用方式。如果网格中没有定义区域模板，你也可以像这样为它添加一个模板：

```css
item1 { grid-area: 1/1/2/4; }
grid-area: 起始水平线 / 起始垂直线 / 末尾水平线 / 终止垂直线 ;
```

因此，示例中的网格项将占用第 1 条和第 2 条水平线之间的行及第 1 条和第 4 条垂直线之间的列。

### repeat 函数减少重复

当使用`grid-template-columns`和`grid-template-rows`定义网格结构时，你需要为添加的每一行和每一列都输入一个值。

如果要添加带 100 行高度相同的网格，单独放入 100 个值不太实际。幸运的是，有一种更好的方法——使用`repeat`方法指定行或列的重复次数，后面加上逗号以及需要重复的值。

```css
grid-template-rows: repeat(100, 50px);/*添加 100 行网格的例子，使每行高度均为 50px：*/

grid-template-columns: repeat(2, 1fr 50px) 20px;
/*效果等效于*//*==*/
grid-template-columns: 1fr 50px 1fr 50px 20px;
```

### minmax 函数限制项目大小

置函数`minmax`也可以可用于设置`grid-template-columns`和`grid-template-rows`的值。它的作用是在网格容器改变大小时限制网格项的大小。为此，你需要指定网格项允许的尺寸范围。例如：

```css
grid-template-columns: 100px minmax(50px, 200px);
```

在上面的代码中，`grid-template-columns`被设置为添加两列，第一列 100px 宽，第二列宽度最小值是 50px，最大值是 200px

### auto-fill 创建弹性布局

重复方法带有一个名为自动填充（auto-fill）的功能。它的功能是根据容器的大小，尽可能多地放入指定大小的行或列。你可以通过结合`auto-fill`和`minmax`来更灵活地布局。

```css
repeat(auto-fill, minmax(60px, 1fr));
```

上面的代码效果：列的宽度会随容器大小改变，在可以插入一个 60px 宽的列之前，当前行的所有列会一直拉伸.

<b style="color:#FF007D;">注意：</b>
如果容器无法使所有网格项放在同一行，余下的网格项将移至新的一行。

### auto-fit 创建弹性布局

`auto-fit`效果几乎和`auto-fill`一样。不同点仅在于，当容器的大小大于各网格项之和时，`auto-fill`将会持续地在一端放入空行或空列，这样就会使所有网格项挤到另一边；而`auto-fit`则不会在一端放入空行或空列，而是会将所有网格项拉伸至合适的大小。

<b style="color:#FF007D;">注意：</b>
如果容器无法使所有网格项放在同一行，余下的网格项将移至新的一行。

### 媒体查询创建响应式布局

通过使用媒体查询重新排列网格区域，更改网格尺寸以及重新排列网格项位置，CSS 网格能轻松地使网站更具响应性。

