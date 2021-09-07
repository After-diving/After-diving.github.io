# CSS Basic Learning

## Introduction

CSS 的全称是 Cascading Style Sheet（层叠样式表），它主要用来控制网页的样式。

<sub style="color:#CCCC00;">注意: CSS 的选择器区分大小写, 因此要谨慎使用大写.</sub>

CSS 早已被所有主流浏览器采用，它允许你轻松控制以下样式：

- 颜色 color
- 背景 background
- 字体 font
- 位置 position
- 显示 display
- 边框 border
- 内边距 padding
- 外边距 margin
- 行高 line-height
- 装饰 text-decoration
- 过渡 transtion
- 变化 transform
- 动画 animation

使用 CSS 样式主要有三种方式：

- 内联样式--你可以直接在 HTML 元素里使用`style`属性。
- 内部样式--你可以在`style`标签里面声明样式规则。
- 外部样式--你可以创建一个`.css`文件，然后在文件中编写样式规则，最后在文档中引用该文件。

尽管前两个方式也有人使用，但大部分开发人员更喜欢外部样式表，因为它可以将样式与元素分开，这提高了代码的可读性和重用性。

CSS 背后的思想是，通过选择器来定位 DOM（文档对象模型）的元素，然后将各种样式规则应用在元素上，从而改变元素在页面上的显示方式。

## 更改文本颜色

通过修改元素的`style`属性的`color`值来改变文本颜色

```html
<p style="color:red;">注:行内<code>style</code>最好以<code>;</code>来结束</p>
```

<p style="color:red;">注:行内<code>style</code>最好以<code>;</code>来结束</p>

## 层叠样式表

当我们只需要改变元素的某个样式时，行内样式最简单直观。当我们需要同时改变元素的很多样式时，`层叠样式表`往往是一个更好的选择。

在代码的顶部，创建一个`style`声明区域：

在`style`样式声明区域内，可以创建一个`元素选择器`，应用于所有的`h2`元素。例如，如果你想所有`h2`元素变成红色，可以添加下方的样式规则：

```html
<style> 
code{color: red;}
</style>
<p>在每个元素的样式声明区域里，左右花括号<code>{</code>和 <code>}</code>一定要写全。</p>
```

<style> 
code{color: red;}
</style>
<p>在每个元素的样式声明区域里，左右花括号<code>{</code>和 <code>}</code>一定要写全。</p>

## Class 选择器

CSS 的`class`具有可重用性，可应用于各种 HTML 元素。

一个 CSS`class`声明示例，如下所示：

```css
<style>
  .blue-text {
    color: blue;
  }
</style>
```

可以看到，我们在`<style>`样式声明区域里，创建了一个名为`blue-text`的`class`选择器。

你可以将 CSS`class`选择器应用到一个HTML元素里，如下所示：

```html
<p class="blue-text">CatPhotoApp</p>
```
<style> 
.blue-text{color: blue;}
</style>
<p class="blue-text">CatPhotoApp</p>

注意：在`style`样式区域声明里，`class`需以`.`开头。而在 HTML 元素里，`class`属性的前面不能添加`.`。

## 元素字体

### 字体大小

字体大小由`font-size`属性控制.

```css
<style> 
p{font-size: 36px;}
</style>
<p>在每个元素的样式声明区域里，左右花括号<code>{</code>和 <code>}</code>一定要写全。</p>
```

### 字体样式

通过`font-family`属性，可以设置元素里面的字体样式.

```css
<style> 
p{font-family: "Fira Code";}
</style>
```

### 引用Google字体

```css
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  h2 {font-family: Lobster,monospace;}
</style>
<h2>标题</h2>
```

注: 字体有空格需要加引号, 如`"Fira Code"`,否则可以不用加引号, 如`Lobster`. 当字体不可用时, 浏览器会通过降级去找其他字体. 可以通过上面注释掉`link`试验.

## 图片大小

CSS 的`width`属性可以控制元素的宽度。图片的`width`宽度类似于字体的`px`（像素)值. 

```css
<style> 
.larger-image{width:500px;}
</style>
```

## 边框

CSS 边框具有`style`，`color`和`width`属性。

创建一个 5px 的红色实线边框包围一个 HTML 元素，我们可以这样做：

```html
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
    border-radius: 10px; <!-- 可以使用border-radius属性来让它变得圆润。也可以用%来设置值,如50%-->
  }
</style>
<!-- 在一个元素上可以同时应用多个class，通过使用空格来分隔-->
<img class="class1 class2">
```

## 背景色

```html
<style>  
.silver-background{background-color:silver;}
</style>
<div class="silver-background">xxxx</div>
```

## ID属性设置元素

`id`不可以重用，只应用于一个元素上。同时，在 CSS 里，`id`的优先级要高于`class`，如果一个元素同时应用了`class`和`id`，并设置样式有冲突，会优先应用`id`的样式。

```html
<style>
#cat-photo-element {background-color: green;}
</style>
<div id="cat-photo-element">xxxx</div>
```

注意在`style`标签里，声明 class 的时候必须在名字前插入`.`符号。同样，在声明 id 的时候，也必须在名字前插入`#`符号。

## 元素的内边距

所有的 HTML 元素基本都是以矩形为基础。

每个 HTML 元素周围的矩形空间由三个重要的属性来控制：`padding（内边距）`，`margin（外边距）`和`border（边框）`。

- `padding`控制着元素内容与`border`之间的空隙大小

- CSS 允许你使用`padding-top`，`padding-right`， `padding-bottom`和`padding-left`属性来设置四个不同方向的`padding`值。
- 如果不想每次都要分别声明`padding-top`，`padding-right`，`padding-bottom`和`padding-left`属性，可以把它们汇总在`padding`属性里面声明，如:`padding: 10px 20px 10px 20px;` 顺序为顺时针 上->右->下->左

- `margin（外边距）`控制元素的边框与其他元素之间的距离。如果你设置元素`margin`为负值，元素会变得更大。

- CSS 允许你使用`margin-top`，`margin-right`，`margin-bottom`和`margin-left`属性来设置四个不同方向的`margin`值。
- 同样，每个方向的外边距值可以在`margin`属性里面汇总声明，来代替分别声明`margin-top`，`margin-right`，`margin-bottom`和`margin-left`属性的方式，代码如下：`margin: 10px 20px 10px 20px;`顺序为顺时针 上->右->下->左

<pre style="height:300px;overflow-y:auto;">&lt;style&gt;
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }
  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }
  .yellow-box {
    background-color: yellow;
    padding: 10px;
  }
  .red-box {
    background-color: crimson;
    color: #fff;
    padding: 20px;
    margin: 20px;
  }
  .blue-box {
    background-color: blue;
    color: #fff;
    padding: 20px;
    margin: 10px;
  }
&lt;/style&gt;
&lt;h5 class="injected-text"&gt;margin&lt;/h5&gt;
&lt;div class="box yellow-box"&gt;
  &lt;h5 class="box red-box"&gt;padding&lt;/h5&gt;
  &lt;h5 class="box blue-box"&gt;padding&lt;/h5&gt;
&lt;/div&gt;</pre>

## 属性选择器

使用`[attr=value]`属性选择器修改复选框的样式。这个选择器使用特定的属性值来匹配和设置元素样式。例如，下面的代码会改变所有`type`为`radio`的元素的外边距。

```html
<style>
[type='radio'] {
  margin: 20px 0px 20px 0px;
}
</style>
<label><input type="radio" name="indoor-outdoor">室内</label>
<label><input type="radio" name="indoor-outdoor">室外</label><br>
```

## 相对单位和绝对单位

单位长度的类型可以分成 2 种，一种是相对的，一种是绝对的。绝对长度单位会接近屏幕上的实际测量值，不过不同屏幕的分辨率会存在差异，可能会导致一些误差。相对单位长度，就像`em`和`rem`，它们会依赖其他长度的值。就好像`em`的大小基于元素的字体的`font-size`值，如果你使用`em`单位来设置`font-size`值，它的值会跟随父元素的`font-size`值来改变。

```html
<style>
    .lang{padding:1.5em}
</style>
```

## 优先级

```html
<style>
  .pink-text {
    color: pink !important;
  }
</style>
<!-- 加important 优先级最高 -->
```

## CSS变量

- 创建一个 CSS 变量，你只需要在变量名前添加两个`破折号`，并为其赋值，例子如下：

  `--penguin-skin: gray;`

    ```html
    <style>
      .pink-text {
        color: pink !important;
        --penguin-skin: gray;
      }
    </style>
    ```

- 创建变量后，CSS 属性可以通过引用变量名来使用它的值。

  `background: var(--penguin-skin);`

  ```html
    <style>
      .pink-text {
        color: pink !important;
        --penguin-skin: gray;
      }
        .right.hand{
        background: var(--penguin-skin);
        }
    </style>
  ```

- 使用变量来作为 CSS 属性值的时候，可以设置一个备用值来防止由于某些原因导致变量不生效的情况。

  或许有些人正在使用着不支持 CSS 变量的旧浏览器，又或者，设备不支持你设置的变量值。为了防止这种情况出现，那么你可以这样写：
  
   `background: var(--penguin-skin, black);`

### 层级CSS变量

你创建的变量，不但可以在你声明变量的元素里面使用，同时也可以在该元素的子元素里面使用。这种效应称为cascading（层叠）。

因为层叠的效果，CSS 变量通常会定义在:root元素里。

就像`html`是`body`的容器一样，你也可以认为`:root`元素是你整个 HTML 文档的容器。

在`:root`创建的变量，在整个网页里面都能生效。

当你在`:root`里创建变量时，这些变量的作用域是整个页面。

如果在元素里创建相同的变量，会重写`:root`变量设置的值。

```css
<style>
  :root {
    --penguin-size: 300px;
    --penguin-skin: gray;
    --penguin-belly: white;
    --penguin-beak: orange;
  }
.top-hand{
    --penguin-belly: black;
}
</style>
```

### 媒体查询更改变量

CSS 变量可以简化媒体查询的方式。

例如，当屏幕小于或大于媒体查询所设置的值，通过改变变量的值，那么应用了变量的元素样式都会得到响应修改。

可以通过缩放页面来查询是否生效.

[网页地址尝试](https://learn.freecodecamp.one/responsive-web-design/basic-css/use-a-media-query-to-change-a-variable)

```css
<style>  
@media (max-width: 350px) {
    :root {
      --penguin-size:200px;
      --penguin-skin:black;
    }
  }
</style>
```

