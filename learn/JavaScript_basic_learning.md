---
sort:4
---
# javascript basic learning

## 注释

被注释的代码块在 JavaScript 之中是不会执行的。在代码中写注释是一个非常好的方式让你自己和其他人理解代码。

JavaScript 中的注释方式有以下两种：

```javascript
//  单行注释
/* ------------*/ 多行注释
```

## 变量声明

JavaScript 提供七种不同的数据类型，如下:

| 数据类型    | 名词解释 | 数据类型 | 名词解释 | 数据类型  | 名词解释 |
| :---------: | :-----: | :------: | :-----: | :------: | :------: |
| `undefined` | 未定义   | `null`   | 空       | `boolean` | 布尔型   |
| `string`    | 字符串   | `symbol` | 符号     | `number`  | 数字     |
| `object`    | 对象     |

变量允许计算机以一种动态的形式来存储和操作数据，通过操作指向数据的指针而不是数据本身来避免了内存泄露，以上的七种数据类型都可以存储到一个变量中。

`变量`非常类似于你在数学中使用的 x，y 变量，都是以一个简单命名的名称来代替我们赋值给它的数据。计算机中的`变量`与数学中的变量不同的是，计算机可以在不同的时间存储不同类型的变量。

通过在变量的前面使用关键字`var`，声明一个变量，例如：

```javascript
var yourname;
```

上面代码的意思是创建一个名为`yourname`的`变量`，在 JavaScript 中我们以分号结束语句。

`变量`名称可以由数字、字母、美元符号`$`或者 下划线`_`组成，但是不能包含空格或者以数字为开头。

## 赋值运算符存储值

在 JavaScript 中，你可以使用赋值运算符将值存储在变量中。

```javascript
myVariable = 5;
```

这条语句把`Number`类型的值`5`赋给变量`myVariable`。

赋值过程是从右到左进行的。在将值分配给运算符左侧的变量之前，将解析`=`运算符右侧的所有内容。

通常在声明变量的时候会给变量初始化一个初始值。

```javascript
var myVar = 0;
```

当 JavaScript 中的变量被声明的时候，程序内部会给它一个初始值`undefined`。当你对一个值为`undefined`的变量进行运算操作的时候，算出来的结果将会是`NaN`，`NaN`的意思是"Not a Number"。当你用一个值是`undefined`的变量来做字符串拼接操作的时候，它会输出字符串`"undefined"`。

<b style="color:#000FFF">驼峰命名法</b>:Javascript 变量一般使用驼峰命名法，变量名的第一个单词的首写字母小写，后面的单词的第一个字母大写,如`var anotherVariableName;`。

## 运算

示例

```javascript
var myVar = 5 + 10; // 赋值为 15
var myVar = 12 - 6; // 赋值为 6
var myVar = 13 * 13; // 赋值为169
var myVar = 16 / 2; // 赋值为8
var i++;  //对变量i+1运算
/*等效于*/ var i = i + 1;
var i--;  //对变量i-1运算
/*等效于*/ var i = i - 1;
var myRemainder =5 % 2 ; //f赋值为1, 求余运算
```

- 复合运算

  在编程当中，通常通过赋值来修改变量的内容。记住，赋值时 Javascript 会先计算`=`右边的内容，所以我们可以写这样的语句：
  ` myVar = myVar + 5;`

  以上是最常见的运算赋值语句，即先运算、再赋值。还有一类操作符是一步到位既做运算也赋值的。

  其中一种就是`+=`运算符。

  ```javascript
  var myVar = 1;
  myVar += 5;
  console.log(myVar); // 返回 6
  /* 同理*/
  myVar = myVar - 5; /*等于*/ myVar -=5;
  myVar = myVar * 5; /*等于*/ myVar *=5;
  myVar = myVar / 5; /*等于*/ myVar /=5;
  myVar = myVar % 5; /*等于*/ myVar %=5;
  ```

## 转义字符串的引号

转义一个字符串必须要用单引号或双引号来包裹它。那么当你的字符串里面包含：`"`或者`'`时该怎么办呢?

在 JavaScript 中，你可以通过在引号前面使用反斜杠（`\`）来转义引号。

```javascript
var sampleStr = "Alan said, \"Peter is learning JavaScript\".";
```

有了转义符号，JavaScript 就知道这个单引号或双引号并不是字符串的结尾，而是字符串内的字符。所以，上面的字符串打印到控制台的结果为：

```javascript
Alan said, "Peter is learning JavaScript".
```

<table border="2" cellpadding="1" cellspacing="2">
    <caption><b style="color:#000FFF">转义序列</b></caption>
    <tr align="center">
        <th>代码</th>
        <th>序列</th>
        <th>代码</th>
        <th>序列</th>
        <th>代码</th>
        <th>序列</th>
    </tr>
    <tr align="center">
        <td><code>\'</code></td>
        <td>单引号</td>
        <td><code>\"</code></td>
        <td>双引号</td>
        <td><code>\\</code></td>
        <td>反斜杠</td>
    </tr>
        <tr align="center">
        <td><code>\n</code></td>
        <td>换行符</td>
        <td><code>\r</code></td>
        <td>回车符</td>
        <td><code>\t</code></td>
        <td>制表符</td>
    </tr>
        <tr align="center">
        <td><code>\b</code></td>
        <td>退格</td>
        <td><code>\f</code></td>
        <td>换页符</td>
        <td colspan="2"><s>|||||||||||||||||||||||||||</s></td>
    </tr>
</table>

```javascript
myStr="FirstLine\n\t\\\SecondLine\nThirdLine"
/*result:*/
FirstLine
    \SecondLine
ThirdLine
```

## 查找字符串长度

- 你可以通过在字符串变量或字符串后面写上`.length`来获得字符串变量`字符串`值的长度。

```javascript
"Alan Peter".length; // 10
```

- 使用方括号查找字符串中的第一个字符

方括号表示法是一种在字符串中的特定`index`（索引）处获取字符的方法。

例如, 在单词 "Charles" 中索引 0 上的字符为 "C"，所以在`var firstName = "Charles"`中，你可以使用`firstName[0]`来获得第一个位置上的字符。

你也可以使用方括号来获得一个字符串中的其他位置的字符。

- 字符串的不变性

在 JavaScript 中，`字符串`的值是 不可变的，这意味着一旦字符串被创建就不能被改变。

例如，下面的代码：
```javascript
 var myStr = "Bob";
 myStr[0] = "J";
```

是不会把变量`myStr`的值改变成 "Job" 的，因为变量`myStr`是不可变的。注意，这*并不*意味着`myStr`永远不能被改变，只是字符串字面量 string literal 的各个字符不能被改变。改变`myStr`中的唯一方法是重新给它赋一个值，例如：

```javascript
var myStr = "Bob";
myStr = "Job";
```

## 数组

使用`数组`，我们可以在一个地方存储多个数据。

- **一维数组**

以左方括号`[`开始定义一个数组，以右方括号`]`结束，里面每个元素之间用逗号隔开，例如：

`var sandwich = ["peanut butter", "jelly", "bread",100]`.

- **多维数组**

你也可以在数组中包含其他数组，例如：`[["Bulls", 23], ["White Sox", 45]]`。

- **数组索引**

我们可以像操作字符串一样通过数组索引`[index]`来访问数组中的数据。

数组索引的使用与字符串索引一样，不同的是，通过字符串的索引得到的是一个字符，通过数组索引得到的是一个元素。与字符串类似，数组也是基于零的索引，因此数组的第一个元素的索引是`0`。

```javascript
var array = [50,60,70];
array[0]; // 值为 50
var data = array[1]; // 值为 60
```

<b style="color:red;">提示:</b>
数组名称和方括号之间不应有任何空格，如`array [0]`尽管 JavaScript 能够正确处理，但可能会让看你代码的其他程序员感到困惑

- **修改数组数据**

与字符串的数据不可变不同，数组的数据是可变的，并且可以自由地改变。

```javascript
var ourArray = [50,40,30];
ourArray[0] = 15; // 等于 [15,40,30]
```

- **索引多维数组**

可以把 多维 数组看作成是一个 *数组中的数组*。当使用方括号去访问数组的时候，第一个`[index]`访问的是第 N 个子数组，第二个`[index]`访问的是第 N 个子数组的第N个元素。

```javascript
var arr = [
  [1,2,3],
  [4,5,6],
  [7,8,9],
  [[10,11,12], 13, 14]
];
arr[3]; // 等于 [[10,11,12], 13, 14]
arr[3][0]; // 等于 [10,11,12]
arr[3][0][1]; // 等于 11
```

### push()操作数组

一个简单的方法将数据添加到一个数组的末尾是通过`push()`函数。

`.push()`接受把一个或多个参数，并把它“推”入到数组的末尾。

```javascript
var arr = [1,2,3];
arr.push(4);
// 现在arr的值为 [1,2,3,4]
```

### pop()操作数组

改变数组中数据的另一种方法是用`.pop()`函数。

`.pop()`函数用来“抛出”一个数组末尾的值。我们可以把这个“抛出”的值赋给一个变量存储起来。换句话说就是`.pop()`函数移除数组末尾的元素并返回这个元素。

数组中任何类型的元素（数值，字符串，甚至是数组）可以被“抛出来” 。

```javascript
var threeArr = [1, 4, 6];
var oneDown = threeArr.pop();
console.log(oneDown); // 输出 6
console.log(threeArr); // 输出 [1, 4]
```

### shift()操作数组

`.shift()`的工作原理就像`.pop()`，但它移除的是第一个元素，而不是最后一个。

### unshift()操作数组

你不仅可以`shift`（移出）数组中的第一个元素，你也可以`unshift`（移入）一个元素到数组的头部。

`.unshift()`函数用起来就像`.push()`函数一样, 但不是在数组的末尾添加元素，而是在数组的头部添加元素。

## 函数编写可重用代码

在 JavaScript 中，我们可以把代码的重复部分抽取出来，放到一个函数中。

举个例子：
```javascript
 function functionName() {
  console.log("Hello World");
 }
/*你可以通过函数名`functionName`加上后面的小括号来调用这个函数，就像这样：*/
functionName();
```

每次调用函数时，它都会在控制台上打印消息`"Hello World"`。每次调用函数时，大括号之间的所有代码都将被执行。

## 全局作用域和函数

在 JavaScript 中，作用域涉及到变量的作用范围。在函数外定义的变量具有 全局 作用域。这意味着，具有全局作用域的变量可以在代码的任何地方被调用。

<span style="color:red;">这些没有使用`var`关键字定义的变量，会被自动创建在全局作用域中，形成全局变量</span>。当在代码其他地方无意间定义了一个变量，刚好变量名与全局变量相同，这时会产生意想不到的后果。因此你应该总是使用var关键字来声明你的变量。

## 局部作用域和函数

在一个函数内声明的变量，以及该函数的参数都是局部变量，意味着它们只在该函数内可见。

这是在函数`myTest`内声明局部变量`loc`的例子：

```javascript
function myTest() {
var loc = "foo";
console.log(loc);
}
myTest(); // 打印出 "foo"
console.log(loc); // loc 没有定义
```

