# int与Integer有什么区别，Integer的值缓存范围

---

## 1.int与Integer的区别

* int是java中的基本数据类型，Integer是int的包装类；
* int类型的变量直接存储数值，Integer在表示数值时必须实例化后才能使用；
* int的默认值是0，Integer的默认值是null；

## 2.Integer的值缓存范围

Integer的值缓存范围是：-128~127

因为Java里面对处在在-128~127之间的Integer值，用的是原生数据类型int，会在内存里供重用，

也就是说这之间的Integer值进行==比较时只是进行int原生数据类型的数值比较，而超出-128~127的范围，进行==比较时是进行地址及数值比较。

如代码1所示：

```java
    Integer a = 127;
    Integer b = 127;
    System.out.println(a == b);//true

    Integer c = 128;
    Integer d = 128;
    System.out.println(c == d);//false
```

IntegerCache有一个静态的Integer数组，在类加载时就将-128 到 127 的Integer对象创建了，并保存在cache数组中，一旦程序调用valueOf 方法，如果i的值是在-128 到 127 之间就直接在cache缓存数组中去取Integer对象。

```java
/**
     * Cache to support the object identity semantics of autoboxing for values between
     * -128 and 127 (inclusive) as required by JLS.
     *
     * The cache is initialized on first usage.  The size of the cache
     * may be controlled by the {@code -XX:AutoBoxCacheMax=<size>} option.
     * During VM initialization, java.lang.Integer.IntegerCache.high property
     * may be set and saved in the private system properties in the
     * sun.misc.VM class.
     */

    private static class IntegerCache {
        static final int low = -128;
        static final int high;
        static final Integer cache[];

        static {
            // high value may be configured by property
            int h = 127;
            String integerCacheHighPropValue =
                sun.misc.VM.getSavedProperty("java.lang.Integer.IntegerCache.high");
            if (integerCacheHighPropValue != null) {
                try {
                    int i = parseInt(integerCacheHighPropValue);
                    i = Math.max(i, 127);
                    // Maximum array size is Integer.MAX_VALUE
                    h = Math.min(i, Integer.MAX_VALUE - (-low) -1);
                } catch( NumberFormatException nfe) {
                    // If the property cannot be parsed into an int, ignore it.
                }
            }
            high = h;

            cache = new Integer[(high - low) + 1];
            int j = low;
            for(int k = 0; k < cache.length; k++)
                cache[k] = new Integer(j++);

            // range [-128, 127] must be interned (JLS7 5.1.7)
            assert IntegerCache.high >= 127;
        }

        private IntegerCache() {}
    }
```



