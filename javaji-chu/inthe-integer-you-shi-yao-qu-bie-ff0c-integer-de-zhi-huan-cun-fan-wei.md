# int与Integer有什么区别，Integer的值缓存范围

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



