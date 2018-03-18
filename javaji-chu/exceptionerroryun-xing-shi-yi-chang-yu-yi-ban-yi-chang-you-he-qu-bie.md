# Exception，Error，运行时异常与一般异常有何区别

Exception和Error都是Throwable类的子类

## 1.Exception

Exception\(异常类\)：属于异常类。异常属于程序级别的。异常通常是在程序运行中发生了问题，例：空指针异常、角标越界异常、类型转换异常等。

通常在开发中，异常是不可估计的，而程序在运行中发生了异常后，java有提供解决异常的处理方案\(声明、捕获\)。通常异常是可以解决并保证程序正常执行。Exception又分为运行时异常（Runtime Exception）和一般异常（非运行时异常）。

### 1.1 Runtime Exception

运行异常类对应于编译错误，它是指Java程序在运行时产生的由解释器引发的各种异常。运行异常可能出现在任何地方，且出现频率很高，因此为了避免巨大的系统资源开销，编译器不对异常进行检查。所以Java语言中的运行异常不一定被捕获。出现运行错误往往表示代码有错误，如：java.lang.ArithmeticException、java.lang.ArrayIndexOutOfBoundsException等

### 1.2 Checked Exception

## 2. Error



