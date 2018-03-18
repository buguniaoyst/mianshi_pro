# 包装类，装箱和拆箱

## 1 .Java中的基本类型和包装类

### 1.1 Java中的8种基本数据类型

byte   short    int       long     float    double    char       boolean

### 1.2 Java中8种基本类型的数据对应的包装类型

Byte   Short    Integer   Long     Float    Double   Character   Boolean

注：包装类型中还有：BigInteger、BigDecmail没有相对应的基本类型，主要应用于高精度的运算，BigInteger 支持任意精度的整数，BigDecimal支持任意精度带小数点的运算。

### 1.3 包装类型的作用

使用包装类主要是因为包装类中提供了很多方法帮助我们进行数据类型之间的转换。基本类型时无法做到的。如：将一个字符串类型的数字转换成可进行算术运算的数据类型。

```java
String strNum = "12";

Integer intNum = Integer.valueOf(strNum);

 System.out.println(intNum+1);
```

## 2. 装箱和拆箱

从JDK1.5以后，可以使用基本类型数据给包装类在赋值。在赋值的底层其实JVM帮助我们完成的类型之间的转换

把基本类型数据赋值给包装类称为：装箱

把包装类赋值给基本类型数据称为：拆箱

![](/assets/zhuangxiang_chaixiang.png)

