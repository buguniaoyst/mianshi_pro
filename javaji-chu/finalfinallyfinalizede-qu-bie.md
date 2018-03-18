# final，finally，finalize的区别

## 1. final

final是java中的修饰符，常用来修饰类，成员变量和成员方法。

### 1.1 final修饰的类：不能够被其他类继承

在开发中，如果某个类不希望被其它的类继承，这时在该类添加final关键字。如java中的String类：

![](/assets/String_01.png)

### 1.2 final修饰的成员变量:成员变量就变成了常量

在开发中，如果某个成员变量不希望被修改，可以使用final修饰。

![](/assets/final_2.png)

### 1.3 final修饰的成员方法：不能够被子类重写

在开发中，如果希望成员方法不被子类重写，则使用final修饰这个方法。

## 2.finally

finally关键字是用来处理捕获异常之后的内容的，finally通常和try catch搭配使用，保证不管有没有发生异常，资源都能够被释放（释放连接、关闭IO流）。



