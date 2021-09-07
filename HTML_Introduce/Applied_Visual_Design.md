# Applied Visual Design

## text-align 属性

web 内容大部分都是文本。CSS 里面的`text-align`属性可以控制文本的对齐方式。

`text-align: justify;`可以让除最后一行之外的文字两端对齐，即每行的左右两端都紧贴行的边缘。

`text-align: center;`可以让文本居中对齐。

`text-align: right;`可以让文本右对齐。

`text-align: left;`是`text-align`的默认值，它可以让文本左对齐。

## width 属性

你可以使用 CSS 里面的`width`属性来指定元素的宽度。属性值可以是相对单位（比如 em），绝对单位（比如 px），或者包含块（父元素）宽度的百分比。

## height 属性

和`width`属性类似，你可以使用 CSS 里面的`height`属性来指定元素的高度。

## 文字属性

`font-size`调整文字大小. `font-weight`设置字体的粗细. `line-height`设置行间距离;

## margin属性居中显示

应用设计中经常需要把一个块级元素水平居中显示。一种常见的实现方式是把块级元素的`margin`值设置为`auto`。

同样的，这个方法也对图片奏效。图片默认是内联元素，但是可以通过设置其`display`属性为`block`来把它变成块级元素。

## Transform scale 属性

CSS 属性`transform`里面的`scale()`函数，可以用来改变元素的显示比例。下面的例子把页面的段落元素放大了 2 倍：

```css
p {
  transform:scale(2);
}
```

### 鼠标悬停时缩放元素

`transform`属性有很多函数，可以对元素进行调整大小、移动、旋转、翻转等操作。当使用伪类描述元素的指定状态如`:hover`时，`transform`属性可以方便的给元素添加交互。

```css
p:hover {
  transform: scale(2.1);
}
```

### skeX 属性沿X轴倾斜元素

`transform`属性`skewX`，`skewX`使选择的元素沿着 X 轴（横向）翻转指定的角度。

```css
p {
  transform: skewX(-32deg);
}
```

### skeY 属性沿Y轴倾斜元素

`skewY`属性使指定元素沿 Y 轴（垂直方向）翻转指定角度。
```css
p {
  transform: skewY(-10deg);
}
```

<code>rotate(-45deg);/*用法和skeX,skeY一样,顺时针旋转*/</code>

## iframe 属性

```css
<iframe 
    height=450 
    width=800 
    src="//player.bilibili.com/player.html?aid=32640707&cid=57118032&page=1"
    scrolling="no"
    border="0"
    frameborder="0"
    framespacing="0"
    allowfullscreen="true"> </iframe>
```

## strong 标签加粗文本

术语：Strong => s => 加粗。

你可以使用`strong`标签来加粗文字。添加了`strong`标签后，浏览器会自动给元素应用`font-weight:bold;`。

## u 标签下划线

术语：Underline => u => 下划线。

你可以使用`u`标签来给文字添加下划线。添加了`u`标签后，浏览器会自动给元素应用`text-decoration: underline;`。

## em 标签强调文本

术语：emphasis => em => 强调。

你可以使用`em`标签来强调文本。由于浏览器会自动给元素应用`font-style: italic;`，所以文本会显示为斜体。

## s 标签删除线

术语：Strikethrough => s => 删除线。

你可以用`s`标签来给文字添加删除线，我是明晃晃的删除线，它代表着这段文字不再有效。添加了`s`标签后，浏览器会自动给元素应用`text-decoration: line-through;`。

## hr标签水平线

术语：Horizontal Rule => hr => 水平线。

你可以用`hr`标签来创建一条宽度撑满父元素的水平线。它一般用来表示文档主题的改变，在视觉上将文档分隔成几个部分。

<mark>注意: 在 HTML 里，hr是自关闭标签，所以不需要一个单独的关闭标签。</mark>

## 文本背景色

为了让页面更美观，除了设置整个页面的背景色以及文字颜色外，你还可以单独设置文字的背景色，即在文字的父元素上添加`background-color`属性。在本挑战里我们将使用`rgba()`颜色，而不是之前学到的`hex`编码或者`rgb()`颜色。

<pre style="background-color:rgba(45,45,45,0.2);pading:10px;box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);">rgba 代表：
 r = red 红色
 g = green 绿色
 b = blue 蓝色
 a = alpha 透明度</pre>

RGB 值可以在 0 到 255 之间。alpha 值可以在 0 到 1 之间，其中 0 代表完全透明，1 代表完全不透明。`rgba()`非常棒，因为你可以设置颜色的透明度，这意味着你可以做出一些很漂亮的半透明效果。

## box-shadow 元素阴影

`box-shadow`属性用来给元素添加阴影，该属性值是由逗号分隔的一个或多个阴影列表。

`box-shadow`属性的每个阴影依次由下面这些值描述：

- `offset-x`阴影的水平偏移量；
- `offset-y`阴影的垂直偏移量;
- `blur-radius`模糊距离；
- `spread-radius`阴影尺寸；
- 颜色。

其中`blur-raduis`和`spread-raduis`是可选的。

```css
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
```

## 降低元素的`opacity`透明度

CSS 里的`opacity`属性用来设置元素的透明度。

> 值 1 代表完全不透明。
> 值 0.5 代表半透明。
> 值 0 代表完全透明。

透明度会应用到元素内的所有内容，不论是图片，还是文本，或是背景色。

```css
<style>
  .links {
    text-align: left;
    color: black;
    opacity: 0.7;
  }
</style>
<a href="www.baidu.com" class="links">百度</a>
```

## text-transform属性

CSS 里面的`text-transform`属性来改变英文中字母的大小写。它通常用来统一页面里英文的显示，且无需直接改变 HTML 元素中的文本。

下面的表格展示了`text-transform`的不同值对文字 “Transform me” 的影响。

<table>
    <tr>
        <th>Value</th>
        <th>Result</th>
        <th>Value</th>
        <th>Result</th>
    </tr>
    <tr>
        <td><code>lowercase</code></td>
        <td>"transform me"</td>
        <td><code>uppercase</code></td>
        <td>"TRANSFORM ME"</td>
    </tr>
    <tr>
        <td><code>capitalize</code></td>
        <td>"Transform Me"</td>
        <td><code>initial</code></td>
        <td>使用默认值</td>
    </tr>
    <tr>
        <td><code>inherit</code></td>
        <td>使用父元素的<code>text-transform</code>值。</td>
        <td><code>none</code></td>
        <td>Default:不改变文字。</td>
    </tr>
</table>

## 元素的position

### 相对位置

在 CSS 里一切 HTML 元素皆为盒子，也就是通常所说的`盒模型`。块级元素自动从新的一行开始（比如标题、段落以及 div），行内元素排列在上一个元素后（比如图片以及 span）。元素默认按照这种方式布局称为文档的`普通流`，同时 CSS 提供了 position 属性来覆盖它。

当元素的 position 设置为`relative`时，它允许你通过 CSS 指定该元素在当前普通流页面下的相对偏移量。 CSS 里控制各个方向偏移量的对应的属性是`left`、`right`、`top`和`bottom`。它们代表着从原来的位置向对应的方向偏移指定的像素、百分比或者 ems。下面的例子展示了段落向上偏移 10 像素：

<pre style="color:red;">注: 元素将从当前位置，向属性相反的方向偏移</pre>

```css
p {
  position: relative;
  bottom: 10px;
}
```

### 绝对位置

CSS`position`属性的取值选项`absolute`，`absolute`相对于其包含块定位。和`relative`定位不一样，`absolute`定位会将元素从当前的文档流里面移除，周围的元素会忽略它。可以用 CSS 的 top、bottom、left 和 right 属性来调整元素的位置。

`absolute`定位比较特殊的一点是元素的定位参照于最近的已定位祖先元素。如果它的父元素没有添加定位规则（默认是`position:relative;`）,浏览器会继续寻找直到默认的 body 标签。

```css
<style>
  #searchbar {
    position:absolute;
    top:50px;
    right:50px;
  }
  section {
    position: relative;
  }
</style>
<body>
  <h1>欢迎！</h1>
  <section>
    <form id="searchbar">
      <label for="search">搜索：</label>
      <input type="search" id="search" name="search">
      <input type="submit" name="submit" value="Go!">
    </form>
  </section>
</body>
```

### 固定定位

`fixed`定位，它是一种特殊的绝对（absolute）定位，区别是其包含块是浏览器窗口。和绝对定位类似，`fixed`定位使用 top、bottom、left 和 right 属性来调整元素的位置，并且会将元素从当前的文档流里面移除，其它元素会忽略它的存在。

`fixed`定位和`absolute`定位的最明显的区别是`fixed`定位元素不会随着屏幕滚动而移动。

## folat属性

浮动元素不在文档流中，它向左或向右浮动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。通常需要用`width`属性来指定浮动元素占据的水平空间。

```css
  <style>
  #left {
    float:left;
    width: 50%;
  }
  #right {
    float:right;
    width: 40%;
  }
</style>
```

## 重叠元素z-index 属性

当一些元素重叠时，在 HTML 里后出现的元素会默认显示在更早出现的元素的上面。你可以使用`z-index`属性指定元素的堆叠次序。`z-index`的取值是整数，数值大的元素优先于数值小的元素显示。

```css
<style>
  div {
    width: 60%;
    height: 200px;
    margin-top: 20px;
  }
  
  .first {
    background-color: red;
    position: absolute;
    z-index:2;
  }
  .second {
    background-color: blue;
    position: absolute;
    left: 40px;
    top: 50px;
    z-index: 1;
  }
</style>

<div class="first"></div>
<div class="second"></div>
```

## 色彩

### 了解互补色

色彩理论以及设计色彩学很复杂，这里将只涉及很基础的部分。在网站设计里，颜色能让内容更醒目，能调动情绪，从而创造舒适的视觉体验。不同的颜色组合对网站的视觉效果影响很大，精妙的设计都需要适宜的颜色来美化页面内容。

一半是科学，一半是艺术，色环是我们认识颜色关系的好工具 - 它是一个近色相邻异色相离的圆环。当两个颜色恰好在色环的两端时，这两个颜色叫做补色。绘画中两只补色在混合后会变成灰色。补色搭配能形成强列的对比效果，传达出活力、能量、兴奋等意义。

下面是一些十六进制码（hex code）补色的例子：

```css
红色（#FF0000）和蓝绿色 (#00FFFF)
绿色（#00FF00）和品红色（#FF00FF）
蓝色（#0000FF）和黄色（#FFFF00）
```

### 了解三原色

电脑显示器和手机屏幕是一种加色模型，将红（R）、绿（G）、蓝（B）三原色的色光以不同的比例相加，以产生多种多样的色光。

两种原色相加产生二次色：蓝绿（G+B）、品红（R+B）和黄色（R+G）。这些二次色恰好是在合成它们时未使用的原色的补色，即在色环中位于两端。例如，品红色是红色和蓝色相加产生，它是绿色的补色。

三次色是由原色和二次色相加产生的颜色，例如红色（原色）和黄色（二次色）相加产生橙色。将这六种颜色中相邻的颜色相加，便产生了十二色色环。

设计里面有很多种颜色搭配方法。涉及到三次色的一种配色方法是分裂补色搭配法。选定主色之后，在色环上选择与它的补色相邻的两种颜色与之搭配。此种搭配既有对比，又不失和谐。

```css
橙色	 #FF7D00
蓝绿色	#00FFFF
树莓红	#FF007D
```

### 颜色的色相

HSL 色彩空间模型是一种将 RGB 色彩模型中的点放在圆柱坐标系中的表示法，描述了色相（hue）、饱和度（saturation）、亮度（lightness）。CSS3 引入了对应的`hsl()`属性做为对应的颜色描述方式。

- **色相**是色彩的基本属性，就是平常所说的颜色名称，如红色、黄色等。以颜色光谱为例，光谱左边从红色开始，移动到中间的绿色，一直到右边的蓝色，色相值就是沿着这条线的取值。在`hsl()`里面，色相用色环来代替光谱，色相值就是色环里面的颜色对应的从 0 到 360 度的角度值。

- **饱和度**是指色彩的纯度，也就是颜色里灰色的占比，越高色彩越纯，低则逐渐变灰，取0-100%的数值。

- **亮度**决定颜色的明暗程度，也就是颜色里白色或者黑色的占比，100% 亮度是白色， 0% 亮度是黑色，而 50% 亮度是“一般的”。

下面是一些使用`hsl()`描述颜色的例子，颜色都为满饱和度，中等亮度:

```css
红	 hsl(0, 100%, 50%)
黄	 hsl(60, 100%, 50%)
绿	 hsl(120, 100%, 50%)
蓝绿	hsl(180, 100%, 50%)
蓝	 hsl(240, 100%, 50%)
品红	hsl(300, 100%, 50%)
```

### 线性渐变(颜色过渡)

TML 元素的背景色并不局限于单色。CSS 还提供了颜色过渡，也就是渐变。可以通过`background`里面的`linear-gradient()`来实现线性渐变，下面是它的语法：

<code>background: linear-gradient(gradient_direction, 颜色 1, 颜色 2, 颜色 3, ...);</code>

第一个参数指定了颜色过渡的方向 - 它的值是角度，90deg 代表垂直渐变，45deg 的渐变角度和反斜杠方向差不多。剩下的参数指定了渐变颜色的顺序：

```css
background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));
```

### 线性渐变条纹元素

`repeating-linear-gradient()`函数和`linear-gradient()`很像，主要区别是`repeating-linear-gradient()`重复指定的渐变。

角度就是渐变的方向。起止渐变颜色值代表渐变颜色及其宽度值，由颜色值和起止位置组成，起止位置用百分比或者像素值表示。

在代码编辑器的例子里，渐变开始于 0 像素位置的`yellow`，然后过渡到距离开始位置 40 像素的`blue`。由于下一个起止渐变颜色值的起止位置也是 40 像素，所以颜色直接渐变成第三个颜色值`green`，然后过渡到距离开始位置 80 像素的`red`。

下面的代码可以帮助理解成对的起止渐变颜色值是如何过渡的。

```css
0px [黄色 -- 过渡 -- 蓝色] 40px [绿色 -- 过渡 -- 红色] 80px
```

如果每对起止渐变颜色值的颜色都是相同的，由于是在两个相同的颜色间过渡，那么中间的过渡色也为同色，接着就是同色的过渡色和下一个起止颜色，最终产生的效果就是条纹。

```css
<style>
  div{ 
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin:  50 auto;
    background: repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    );
  }
</style>
<div></div>
```
<div align="center">结果:<img src="C:\Users\Yuling.You\AppData\Roaming\Typora\typora-user-images\image-20210403185323798.png" style="zoom:20%"></div>

### 背景图片

添加一个精致的背景图，可以增加页面的质感，让页面更美观。关键是要找到一个平衡点，抢了内容的风头，喧宾夺主可就不妙了。`background`属性支持使用`url()`函数通过链接的方式引入一个指定纹理或样式的图片。图片链接地址在括号内，一般会用引号包起来。

```css
<style>
  body {
    background:url("https://i.imgur.com/MJAkxbh.png");
  }
</style>
```

## 创建图形

<table>
    <caption style="text-align:center;">术语表</caption>
    <tr>
        <th>属性</th>
        <th>功能</th>
        <th>属性</th>
        <th>功能</th>
    </tr>
    <tr>
        <td><code>blur-radius</code></td>
        <td>模糊半径</td>
        <td><code>spread-radius</code></td>
        <td>辐射半径</td>
    </tr>
    <tr>
        <td><code>transparent</code></td>
        <td>透明的</td>
        <td><code>border-radius</code></td>
        <td>圆角边框</td>
    </tr>
</table>
通过使用选择器选择不同的元素并改变其属性，你可以创造一些有趣的形状。比如新月。你可以使用`box-shadow`属性来设置元素的阴影，`border-radius`属性控制元素的圆角边框。

```css
<style>
.moon{
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 100px;
  height: 100px;
  background-color: transparent;
  border-radius: 50%;
  box-shadow: 25px 10px 0px 0px blue; 
}
</style>
<div class="moon"></div>
```



  <div style="position: absolute;margin: auto;top: 0;right: 0;bottom: 0;left: 0;width: 100px;height: 100px;background-color: transparent;border-radius: 50%;box-shadow: 25px 10px 0px 0px yellow;"> </div>

## 伪类

### `:hover`悬停样式

伪类是可以添加到选择器上的关键字，用来选择元素的指定状态。

如，超链接可以使用`:hover`伪类选择器定义它的悬停状态样式。下面是悬停超链接时改变超链接颜色的 CSS：

```css
<style>
  a {
    color: #000;
  }
  a:hover {
  color: blue;
}
</style>
<a href="http://www.baidu.com/" target="_blank">Baidu 知道</a>
```

### `:before`和`:after`

用来在选择元素之前和之后添加一些内容

<b>创建心形为例:</b>

`:before`伪类元素用来给 class 为`heart`的元素添加一个正方形。

```css
.heart:before {
  content: "";
  background-color: yellow;
  border-radius: 25%;
  position: absolute;
  height: 50px;
  width: 70px;
  top: -50px;
  left: 5px;
}
```

`:before`和`:after`必须配合`content`来使用。这个属性通常用来给元素添加内容诸如图片或者文字。当`:before`和`:after`伪类用来添加某些形状而不是图片或文字时，`content`属性仍然是必需的，但是它的值可以是空字符串。

在上面的例子里，class 为`heart`元素的`:before`伪类添加了一个黄色的长方形，长方形的`height`和`width`分别为 50px 和 70px。由于设置了其边框半径为 25%，所以长方形为圆角长方形，同时其相对位置为距离`left`5px，以及向`top`偏移 50px。

```html
<style>
.heart {
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: pink;
  height: 50px;
  width: 50px;
  transform: rotate(-45deg);/*用法和skeX,skeY一样,顺时针旋转*/
}
.heart:after {
  background-color: pink;
  content: "";
  border-radius: 50%;
  position: absolute;
  width: 50px;
  height: 50px;
  top: 0px;
  left: 25px;
}
.heart:before {
  content:"" ;
  background-color: pink;
  border-radius: 50%;
  position: absolute;
  width: 50px;
  height: 50px;
  top: -25px;
  left: 0px;
}
</style>
<div class = "heart"></div>
```

## 关键帧和动画

如果要给元素添加动画，需要了解`animation`属性以及`@keyframes`规则。`animation`属性控制动画的外观，`@keyframes`规则控制动画中各阶段的变化。总共有 8 个`animation`属性。为了便于理解，本关暂时只涉及到两个最常用的属性。

`animation-name`设置动画的名称， 也就是要绑定的选择器的`@keyframes`的名称。

`animation-duration`设置动画所花费的时间。

`@keyframes`能够创建动画。 创建动画的原理是将一套 CSS 样式逐渐变化为另一套样式。具体是通过设置动画期间对应的“frames”的 CSS 的属性，以百分比来规定改变的时间，或者通过关键词“from”和“to”，等价于 0% 和 100%。打个比方，CSS 里面的 0% 属性就像是电影里面的开场镜头。CSS 里面的 100% 属性就是元素最后的样子，相当于电影里的演职员表或者鸣谢镜头。CSS 在对应的时间内给元素过渡添加效果。下面举例说明`@keyframes`和动画属性的用法：

```css
#anim {
  animation-name: colorful;
  animation-duration: 3s;
}
@keyframes colorful {
  0% {
    background-color: blue;
  }
  100% {
    background-color: yellow;
  }
}
```

id 为`anim`的元素，代码设置`animation-name`为`colorful`，设置`animation-duration`为 3 秒。然后把`@keyframes`引用到名为`colorful`的动画属性上。`colorful`在动画开始时（0%）设置颜色为蓝色，在动画结束时（100%）设置颜色为黄色。注意不是只有开始和结束的过渡可以设置，0% 到 100% 间的任意百分比你都可以设置。

### 按钮悬停时动画

如果想要的效果是按钮在悬停时始终高亮。这可以通过把`animation-fill-mode`设置成`forwards`来实现。`animation-fill-mode`指定了在动画结束时元素的样式

```css
<style>
  button {
    border-radius: 5px;
    color: white;
    background-color: #0F5897;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    animation-name: background-color;
    animation-duration: 500ms;
    animation-fill-mode: forwards;/*悬停时按钮始终高亮*/
  }
  @keyframes background-color {
    100% {
      background-color: #4791d0;
    }
  }
</style>
<button>注册</button>
```

### 动画创建运动

当元素的`position`被指定，如`fixed`或者`relative`时，CSS 偏移属性`right`、`left`、`top`和`bottom`可以用在动画规则里创建动作。

就像下面的例子展示的那样，你可以在`50%`keyframe 处设置`top`属性为 50px， 在开始（0%）和最后（100%）keframe 处设置为 0px，以产生项目向下运动，然后返回的动作效果。

```css
@keyframes rainbow {
  0% {
    background-color: blue;
    top: 0px;
  }
  50% {
    background-color: green;
    top: 50px;
  }
  100% {
    background-color: yellow;
    top: 0px;
  }
}
```

### 通过淡化元素来创建视觉方向

改变动画元素的`opacity`，使其在到达屏幕右侧时渐隐。

```css
  @keyframes fade {
    50% {
      left: 60%;
      opacity:0.1;
    }
  }
```

###  永不停止的动画

还有一个常用的动画属性是`animation-iteration-count`，这个属性允许你控制动画循环的次数。下面是一个例子：

```css
animation-iteration-count: 3;
```

在这里动画会在运行 3 次后停止，如果想让动画一直运行，可以把值设置成 infinite。

### 动画定时器

在 CSS 动画里，`animation-timing-function`规定动画的速度曲线。速度曲线定义动画从一套 CSS 样式变为另一套所用的时间。如果要描述的动画是一辆车在指定时间内（`animation-duration`）从 A 运动到 B，那么`animation-timing-function`表述的就是车在运动中的加速和减速等过程。

已经有了很多预定义的值可以直接使用于大部分场景。比如，默认的值是`ease`，动画以低速开始，然后加快，在结束前变慢。其它常用的值包括`ease-out`，动画以高速开始，以低速结束;`ease-in`，动画以低速开始，以高速结束；`linear`，动画从头到尾的速度是相同的。

```css
<style>
  .balls {
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;  
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 { 
    left:27%;
    animation-timing-function:linear;
  }
  #ball2 { 
    left:56%;
    animation-timing-function:ease-out;
  }

@keyframes bounce {
  0% {
    top: 0px;
  } 
  100% {
    top: 249px;
  }
} 
</style>
<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```

#### 贝塞尔曲线原理

`animation-timing-function`除了预定义值之外，CSS 还提供了贝塞尔曲线（Bezier curves）来更出色的控制动画的速度曲线。

在 CSS 动画里，用`cubic-bezier`来定义贝塞尔曲线。曲线的形状代表了动画的速度。曲线在 1*1 的坐标系统内，曲线的 X 轴代表动画的时间间隔（类似于时间比例尺）(<span style="color:red">X最大为1</span>)，Y 轴代表动画的改变(<span style="color:red">Y可以大于1</span>)。

`cubic-bezier`函数包含了 1 * 1 网格里的4个点：`p0`、`p1`、`p2`和`p3`。其中`p0`和`p3`是固定值，代表曲线的起始点和结束点，坐标值依次为 (0, 0) 和 (1, 1)。你只需设置另外两点的 x 值和 y 值，设置的这两点确定了曲线的形状从而确定了动画的速度曲线。在 CSS 里面通过`(x1, y1, x2, y2)`来确定`p1`和`p2`。综上，下面就是 CSS 贝塞尔曲线的例子：

```css
animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
```

在上面的例子里，两个点的 x 和 y 值相等（x1 = 0.25 = y1 和 x2 = 0.75 = y2），如果你还记得初中几何，结果是从原点到点 (1, 1) 的一条直线。动画速度呈线性，效果和`linear`一致。换言之，元素匀速运动。