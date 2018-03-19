# String，StringBuffer，StringBuilder

Java语言为我们提供了字符串String，能让我们方便地使用字符串类型的数据。但是，在实际应用中单纯地使用String类无法满足我们的需求，于是又衍生出了StringBuffer和StringBuilder。它们三者之间的区别：

* String ：字符串常量；
* StringBuffer：字符串变量（线程安全）；

* StringBuilder ：字符串变量（非线程安全）；

## 1. String

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

String类在java.lang包下，被final修饰，不能够被其他类继承。

## 2. StringBuffer

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

## 3. StringBuilder

```java
public final class StringBuilder extends AbstractStringBuilder implements java.io.Serializable, Appendable, CharSequence {
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



