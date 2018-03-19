# String，StringBuffer，StringBuilder

Java语言为我们提供了字符串String，能让我们方便地使用字符串类型的数据。但是，在实际应用中单纯地使用String类无法满足我们的需求，于是又衍生出了StringBuffer和StringBuilder。它们三者之间的区别：

* String ：字符串常量；
* StringBuffer：字符串变量（线程安全）；

* StringBuilder ：字符串变量（非线程安全）；

## 1. String

String类在java.lang包下，被final修饰，不能够被其他类继承。

通过API的查阅，我们可以了解到：

* 1，  String是一个字符串类，只要被””包含的内容都属于String类的实例

* 2，  String实例引用的都是字符串常量，换句来讲，就是String字符串在初始化完后不能修改其原值\(原有数据\)

String类的创建：

* 1，  String  str = new String\(“字符串”\);

* 2，  String  str = ”字符串”;

```java
/** Strings are constant; their values cannot be changed after they
 * are created. String buffers support mutable strings.
 * Because String objects are immutable they can be shared. 
 * 字符串是不变的，他们的值在创造后不能改变。
 * 字符串缓冲区支持可变字符串，因为字符串对象是不可变的，所以它们可以共享。
 * 
 * @see StringBuffer
 * @see StringBuilder
 * @see Charset
 * @since 1.0
 */
public final class String implements Serializable, Comparable<String>, CharSequence {
    private static final long serialVersionUID = -6849794470754667710L;
    private static final char REPLACEMENT_CHAR = (char) 0xfffd;
```

## 2. StringBuffer\(字符串变量-线程安全\)

StringBuffer是java提供的一个可以用来存储字符的容器。（其实就是在StringBuffer类中有一个内部的字符数组，这个字符数组是可变长度的数组）

（注意：StringBuffer这个容器中只能存储字符数据，存储到StringBuffer中的任何数据都会转为字符数据）

```java
public final class StringBuffer
    extends AbstractStringBuilder
    implements java.io.Serializable, Appendable, CharSequence
{
    /**
     * Constructs a string buffer with no characters in it and an
     * initial capacity of 16 characters.
     */
    public StringBuffer() {
        super(16);
    }
    public synchronized StringBuffer append(int i) {
        super.append(i);
        return this;
    }
    public synchronized StringBuffer delete(int start, int end) {
        super.delete(start, end);
        return this;
    }
}
```

## 3. StringBuilder（字符串变量-线程不安全）

StringBuilder类中的方法和StringBuffer类中的方法完全一样。

StringBuffer和StringBuilder的区别：

* StringBuffer属于线程安全的字符缓冲区对象。 在使用时因为线程安全，所以效率比较低。效率低的原因是因为StringBuffer在操作时都会去检查数据同步。在开发中，如果对线程安全有要求时，使用StringBuffer类

* StringBuilder属于线程不安全的的字符缓冲区对象。在使用时因为线程不安全所以效率比较高。不会去检查数据同步。在开发中，如果对线程安全没有要求时，使用StringBuilder类



```java
public final class StringBuilder 
    extends AbstractStringBuilder 
    implements java.io.Serializable, Appendable, CharSequence {
   public StringBuilder() {
        super(16);
   }
   public StringBuilder append(String str) {
        super.append(str);
        return this;
    }
    public StringBuilder delete(int start, int end) {
        super.delete(start, end);
        return this;
    }
}
```



