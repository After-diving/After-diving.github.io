# java Learning

## 包机制

为了更好的组织类，java提供了包机制，用于区别类名的命名空间。

包语句的语法格式：

```java
package pkg1[. pkg2[. pkg3...]];
```

包的本质就是一个文件夹

一般利用公式域名倒置建立包名, 为了能够使用某一个包的成员,我们需要在java程序中明确导入该包. 使用"import"语句可完成此功能.

```java
import package1[.package2...].(classname|*);
```

## Scanner 对象

java.util.Scanner是java5的新特性,我们可以通过Scanner类来获取用户的输入.

基本语法:

```java
Scanner s = new Scanner(System.in);
```

通过Scanner类的next()与nextLine()方法获取输入的字符串,在读取前我们一般需要使用hasNext()与hasNextLine()判断是否还有输入数据.

- `next()`
  1. 一定要读取到有效字符后才可以结束输入;
  2. 对输入的有效字符之前遇到的空白,next()方法会自动将其去掉;
  3. 只有输入有效字符后才将其后边输入的空白作为分隔符或者结束符;
  4. next()不能得到带有空格的字符串;

- `nextLine()`
  1. 以<kbd>enter</kbd>为结束符,也就是说 nextLine()方法返回的是输入回车之前所有字符;
  2. 可以获得空白;