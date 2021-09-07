# HTML basic learning

## 开篇

### 声明HTML 文档的文档类型

可以通过`<!DOCTYPE ...>`来告诉浏览器你使用的是 HTML 的哪个版本，"`...`" 部分就是版本的数字信息。`<!DOCTYPLE html>`对应的就是 HTML5。`!`和大写的`DOCTYPE`是很重要的，特别是对于老的浏览器。但`html`大写小写都可以。接下来，所有的 HTML 代码都必须位于`html`标签中。其中`<html>`位于`<!DOCTYPE html>`的后面，`</html>`位于网页的结尾。

```html
<!DOCTYPE html>
<html>
  <!-- Your HTML code goes here -->
</html>
```

### HTML 书写结构

`html`的结构主要分为两大部分：`head`、`body`。关于网页的描述都应该放入`head`标签，网页的内容都应该放入`body`标签。

比如`link`、`meta`、`title`和`style`都应该放入`head`标签

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- metadata elements -->
  </head>
  <body>
    <!-- page contents -->
  </body>
</html>
```

## 标题

```html
<h1>title</h1>
<h2>...</h2>
.....<h6>...</h6>
up to h6
```

## 段落

- p 是 paragraph 的缩写,通常用来创建一个段落.

  ```html
  <p> This is a paragraph !</p>
  ```
  <p> This is a paragraph !</p>
- Web 开发者通常用 `lorem ipsum text` 来做占位符，占位符就是占着位置的一些文字，没有实际意义。

  为什么叫`lorem ipsum text`呢?是因为`lorem ipsum`是古罗马西塞罗谚语的前两个单词。从公元16世纪开始`lorem ipsum text`就被当做占位符了，这种传统延续到了互联网时代。

## 注释

注释是为了给代码添加说明, 方便团队合作和自己阅读, 但又不影响代码本身.

HTML中, 注释标记为`<!--    -->`

```html
<!--
<p> This is a paragraph !</p>
-->
```

## 列表

### 有序列表

HTML 有一个特定的元素用于创建有序列表`ordered lists（缩写 ol）`.

有序列表以`<ol>`开始，中间包含一个或多个`<li>`元素，最后以`</ol>`结尾。

```html
<ol>
    <li>第一个序列</li>
    <li>第二个序列</li>
</ol>
```

<ol>
    <li>第一个序列</li>
    <li>第二个序列</li>
</ol>

### 无序列表

HTML 有一个特定的元素用于创建有序列表`unordered lists（缩写 ul）`.

有序列表以`<ul>`开始，中间包含一个或多个`<li>`元素，最后以`</ul>`结尾。

```html
<ul>
    <li>第一个序列</li>
    <li>第二个序列</li>
</ul>
```

<ul>
    <li>第一个序列</li>
    <li>第二个序列</li>
</ul>

## 输入框

可以使用`form`创建一个表单, 用`input`输入框获取用户输入.

`Placeholder`占位符是用户在`input`输入框中输入任何东西前的预定义文本.

```html
<input type="text" placeholder="only input number">  <!-- input输入框是没有结束标记的 -->
```

通过给`form`表单添加一个`action`属性，你可以使用纯 HTML 来构建向服务器提交数据的 Web 表单.

```html
<form action="xxxx"><input type="text" placeholder="only input number"></form>
```

表单添加一个`submit`提交按钮，当点击提交按钮时，表单中的数据将会被发送到`action`属性指定的地址上.

在`input`元素中加上`required`属性就实现此输入框是必填项

```html
<form action="xxxx">
    <input type="text" placeholder="only input number" required>
    <button type="submit">提交</button>
</form>
```

<form action="xxxx">
    <input type="text" placeholder="only input number" required>
    <button type="submit">提交</button>
</form>

### 单选按钮

`radio buttons`（单选按钮）就好比单项选择题，正确答案只有一个。

单选按钮只是`input`输入框的一种类型。

每一个单选按钮都应该嵌套在它自己的`label`（标签）元素中。

所有关联的单选按钮应该拥有相同的`name`属性。

在`label`元素上设置for属性，让其值与单选按钮的`id`属性值相等，这样就在`label`元素和它的子元素单选按钮之间创建了一种链接关系

```html
<label for="group1">
    <input id="group1" type="radio" name="this is a group">group1
</label>
```

### 复选框

`checkbox`（复选框）就好比多项选择题，正确答案有多个。

复选框是`input`输入框的另一种类型。

每一个复选框都应该嵌套在它自己的`label`（标签）元素中。

所有关联的复选框应该拥有相同的`name`属性。

最佳实践是在`label`元素上设置`for`属性，让其值与复选框的`id`属性值相等，这样就在`label`元素和它的子元素复选框之间创建了一种链接关系

```html
<label for="group1">
    <input id="group1" type="checkbox" name="this is a group" checked>group1
</label>
```

通过添加`checked`属性，你可以设置某个单选按钮或多选按钮被默认选中。

为此，只需给`input`元素添加 "checked" 属性

## 元素嵌套

`div`元素，也叫division（层）元素，是一个盛装其他元素的通用容器。

它也是 HTML 中出现频率最高的元素。

和其他普通元素一样, 你可以用`<div>`来标记一个`div`元素的开始，用`</div>`来标记一个`div`元素的结束。

## HTML5 元素介绍

HTML5 引入了很多更具描述性的 HTML 元素，例如：`header`、`footer`、`nav`、`video`、`article`、`section`等等。

这些元素让 HTML 更易读，同时有助于搜索引擎优化和无障碍访问。

### `main`元素

`main`元素让搜索引擎和开发者瞬间就能找到网页的主要内容。

```html
<main>
    <p>...</p>
    <p>...</p>
</main>    
```

### `img`元素

`img`元素为网站添加图片, 其中`src`属性指向一个图片的地址

<sub style="color:#CCCC00;">注 : `img`元素是没有结束标记的</sub>

所有`img`元素必须有`alt`属性, `alt`属性文本时图片无法加载时显示的替代文本.

```html
<img src="C:\Users\yuling.you\Pictures\Saved Pictures\日落山湖.jpg" alt="这是一张壁纸">
```

### `a`元素

- `a`锚点(Anchor)可以用来实现网页跳转.

  锚点`a`需要需要一个`href`属性指向目的地, 他还需要锚点文本, 例如:	

	```html
	<a href="C:\Users\yuling.you\Pictures\Saved Pictures\" target="_blank">点击这里</a>
	```

	<a href="C:\Users\yuling.you\Pictures\Saved Pictures\" target="_blank">点击这里</a> <span style="color:red;">target="_blank"</span> 打开新的元素页

- `a`锚点网页内部跳转

  设置锚点的`href`属性值为井号`#`加上想跳转区域对应的`id`属性值，这样就可以创建一个内部跳转。`id`是用来描述网页元素的一个属性，它的值在整个页面中唯一。

	```html
	<h1 id="Demo">xxxxxxxx</h1>
	<a href="#Demo">这是一个内部跳转演示</a>
	```

- 用`#`来创建固定链接

  有时你想为网站添加一个锚点，但如果你还不确定要将它链接到哪儿，这时可以使用固定链接。

  ```html
  <a href="#">xxx</a>
  ```

  
