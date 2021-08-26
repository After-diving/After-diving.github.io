---
sort:6
---
# Data Type Extension

## Java 关键字

<div align=left><img src="C:\Users\Yuling.You\AppData\Roaming\Typora\typora-user-images\image-20210328181422766.png" width="50%",hight="50%" alt="java关键字"></div>

## 整数扩展

```java
public class Demo {
    public static void main(String[] args){
        /**整数扩展
         *@进制   二进制0b  八进制0 十进制  十六进制0x
         */
        int num  = 0b10;
        int num1 = 010;
        int num2 = 10;
        int num3 = 0x10;

        System.out.println(num);
        System.out.println(num1);
        System.out.println(num2);
        System.out.println(num3);
    }
}
```

输出结果:`2 8 10 16`

---

## 浮点数扩展

```java
        float f  = 0.1f;
        double d = 1.0/10;
        System.out.println(f==d);
        System.out.println(f);
        System.out.println(d);
```

输出结果:`false  0.1  0.1`

```java
        float f1 = 23333333342f;
        float f2 = f1 + 1;
        System.out.println(f1==f2);
```

输出结果:`true`

> **float 特性**: 有限, 离散, 舍入误差,  大约, 接近但不等于
>
> **因此尽量少用浮点数进行比较**
>
> 像银行业务,可以调用 java 类<font color=red>**BigDecimal **</font>数学工具类

---

## 字符扩展

```java
        char a = 'a';
        char b = '游';
        System.out.println(a);
        System.out.println((int)a);
        System.out.println(b);
        System.out.println((int)b);
```

输出结果:`a  97 游 28216 `

> 所有字符的本质还是数字;
>
> 编码 unicode  2字节 0 - 65536  Execl最大表格数 2^16=65536

```java
        //U0000 - UFFFF
		char a1 = '\u0061';
        System.out.println(a1);
```

输出结果:`a`

- **转义字符**

| 字符 |功能|
| :-: | :-: |
| \t |制表符tab|
|\n|换行|

<table border="1" align="center">
    <caption>转义字符</caption>
    <tr>
        <th align="center">字符</th>
        <th align="center">功能</th>
    </tr>
    <tr>
    	<td align="center"><b>\t</b></td>
        <td align="center">制表符 tab</td>
    </tr>
    <tr>
    	<td align="center">\n</td>
        <td align="center">换行符</td>
    </tr>
</table>

```java
        String sa = new String("Hello World");
        String sb = new String("Hello World");
        System.out.println(sa==sb);
        String sc = "Hello World";
        String sd = "Hello World";
        System.out.println(sc==sd);
		//对象 从 内存分析
```

输出结果:`false  true`

## Boolean扩展

```java
		boolean flag = true;
        if(flag == true){};
		if(flag){};
		//两者表达是一样的!
```

