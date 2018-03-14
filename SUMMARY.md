# Summary

* [Introduction](README.md)
* [2018最全Java面试通关秘籍汇总](2018zui-quan-java-mian-shi-tong-guan-mi-ji-hui-zong.md)
* 基础篇

  * Java基础
    * 面向对象的特征：继承，封装和多态
    * final,finally,finalize的区别
    * Exception,Error,运行时异常与一般异常有何区别
    * 请写出5中常见的runtime exception
    * int和Integer有什么区别，Integer的值缓存范围
    * 包装类，装箱和拆箱
    * String，StringBuilder，StringBuffer
    * 重载和重写的区别
    * 抽象类和接口有什么区别
    * 说说反射的用途及实现
    * 说说自定义注解的场景及实现
    * HTTP请求的GET与POST方式的区别
    * Session与Cookie的区别
    * 列出自己常用的JDK包
    * MVC设计丝子昂
    * equals与==的区别
    * hashCode和equals方法的区别与联系
    * 什么是Java序列化，如何实现Java序列化？或者请解释Serializable接口的作用
    * Object类中常见的方法，为什么wait notify会放在Object里边？
    * Java的平台无关性如何体现出来
    * JDK和JRE的区别
    * Java8有哪些新特性
  * 常见集合
    * List和Set区别
    * Set和hashCode以及equals方法的联系
    * List和Map的区别
    * ArrayList和LinkedList的区别
    * ArrayList和Vector的区别
    * HashMap和Hashtable的区别
    * HashSet和HashMap的区别
    * HashMap和ConcurrentHashMap的区别
    * HashMap的工作原理及代码实现，什么时候用到红黑树
    * 多线程情况下HashMap死循环的问题
    * HashMap出现Hash DOS攻击的问题
    * ConcurrentHashMap的工作原理及代码实现，如何统计所有的元素个数
    * 手写简单的HashMap
    * 看过哪些Java集合类的源码
  * 进程和线程
    * 线程和进程的概念，并行和并发的概念
    * 创建线程的方式及实现
    * 进程间通信的方式
    * 说说CountDownLatch，CyclicBarrier原理和区别
    * 说说Semaphore原理
    * 说说Exchanger原理
    * ThreadLocal原理分析，ThreadLocal为什么会出现OOM，出现的深层次原理
    * 讲讲线程池的实现原理
    * 线程池的几种实现方式
    * 线程的生命周期，状态是如何转移的
    * 可参考：《Java多线程编程核心技术》
  * 锁机制
    * 说说线程安全问题，什么是线程安全，如何保证线程安全
    * 重入锁的概念，重入锁为什么可以防止死锁
    * 产生死锁的四个条件（互斥，请求与保持，不剥夺，循环等待）
    * 如何检查死锁（通过jConsole检查死锁）
    * volatile实现原理（禁止指令重排，刷新内存）
    * synchronized实现原理（对象监视器）
    * synchronized与lock的区别
    * AQS同步队列
    * CAS无锁的概念，乐观锁和悲观锁
    * 常见的原子操作类
    * 什么是ABA问题，出现ABA问题JDK是如何解决的
    * 乐观锁的业务场景及实现方式
    * Java8并发包下常见的并发类
    * 偏向锁，轻量级锁，重量级锁，自旋锁的概念
    * 可参考：《Java多线程编程核心技术》
  * JVM
    * JVM运行时内存区域划分
    * 内存溢出OOM和堆栈溢出SOE的示例及原因，如何排查与解决
    * 如何判断对象是否可以回收或存活
    * 常见的GC回收算法及其含义
    * 常见的JVM性能监控和故障处理工具类：jps，jstat，jmap，jinfo，jconsole等
    * JVM如何设置参数
    * JVM性能调优
    * 类加载器，双亲委派模型，一个类的生命周期，类是如何加载到JVM中的
    * 类加载的过程：加载，验证，准备，解析，初始化
    * 强引用，软引用，弱引用，虚引用
    * Java内存模型JMM
  * 设计模式
    * 常见的设计模式
    * 设计模式的六大原则及含义
    * 常见的单例模式以及各种实现方式的优缺点，哪一个最好，手写常见的单例模式
    * 设计模式在实际场景中的应用
    * Spring中用到了哪些设计模式
    * MyBatis中用到了哪些设计模式
    * 你项目中有使用哪些设计模式
    * 说说常用开源框架中设计模式使用分析
    * 动态代理
  * 数据结构
    * 树（二叉查找树，平衡二叉树，红黑树，B树，B+树）
    * 深度有限算法，广度优先算法
    * 克鲁斯卡尔算法，普林姆算法，迪克拉斯算法
    * 什么是一致性Hash及其原理，Hash环问题
    * 常见的排序算法和查找算法：快排，折半查找，堆排序等
  * 网络/IO基础

* 数据存储和消息队列

  * 数据库
  * Redis
  * 消息队列

* 开源框架和容器

  * SSM/Servlet
  * Netty
  * Tomcat

* 分布式

  * Nginx
  * 分布式其他
  * Dubbo

* 微服务

  * 微服务
  * 安全问题
  * 性能优化

* 其他

  * 设计能力
  * 业务工程
  * 软实力



