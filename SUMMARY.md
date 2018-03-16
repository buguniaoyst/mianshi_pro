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
    * MVC设计思想
    * JDBC流程
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
    * BIO,NIO,AIO的概念
    * 什么是长连接和短连接
    * Http1.0和2.0相比有什么区别，可参考《HTTP 2.0》
    * Https的基本概念
    * 三次握手和四次握手，为什么挥手需要四次
    * 从浏览器中输入URL到页面的加载发生了什么？

* 数据存储和消息队列

  * 数据库
    * MySQL索引使用的注意事项
    * DDL,DML,DCL分别指什么
    * explain命令
    * left join,right join,inner join
    * 数据库事务ACID（原子性，一致性，隔离性，持久性）
    * 脏读，幻读，不可重复读
    * 数据库的几大范式
    * 数据库常见的命令
    * 说说分库与分表设计
    * 分库与分表带来的分布式困境与对应之策（如何解决分布式下的分库分表，全局表？）
    * 说说SQL的优化之道
    * MySQL遇到的死锁问题，如何排查与解决
    * 存储引擎的InnoDB与MyISAM区别，优缺点，使用场景
    * 索引类别（B+树索引，全文索引，哈希索引），索引的原理
    * 什么是自适应哈希索引（AHI）
    * 为什么要用B+tree作为MySQL索引的数据结构
    * 聚集索引与非聚集索引的区别
    * 遇到过索引失效的情况没，什么时候可能会出现，如何解决
    * limit 20000加载很慢怎么解决
    * 如何选择合适的分布式主键方案
    * 选择合适的数据存储方案
    * 常见的几种分布式ID的设计方案
    * 常见的数据库优化方案，在你的项目中数据库如何进行优化的
  * Redis
    * Redis有哪些数据类型，可参考《Redis常见的5种不同的数据类型详解》
    * Redis内部结构
    * Redis使用场景
    * Redis持久化机制，可参考《使用快照和AOF将Redis数据持久化到硬盘中》
    * Redis集群方案与实现
    * Redis为什么是单线程的？
    * 缓存雪崩，缓存穿透，缓存预热，缓存更新，缓存降级
    * 使用缓存的合理性问题
    * Redis常见的回收策略
  * 消息队列
    * 消息队列的使用场景
    * 消息的重发补偿解决思路
    * 消息的幂等性解决思路
    * 消息的堆积解决思路
    * 自己如何实现消息队列
    * 如何保证消息的有序性

* 开源框架和容器

  * SSM/Servlet
    * Servlet的生命周期
    * 转发与重定向的区别
    * BeanFactory和ApplicationContext有什么区别
    * Spring Bean的生命周期
    * Spring IOC如何实现
    * Spring中Bean的作用域，默认的是哪一个
    * 说说Spring AOP，Spring AOP实现原理
    * 动态代理（CGlib与JDK），优缺点，性能对比，如何选择
    * Spring事务实现方式，事务的传播机制，默认的事务类别
    * Spring事务底层原理
    * Spring事务失效（事务嵌套），JDK动态代理给Spring事务埋下的坑，可参考《JDK动态代理给Spring事务埋下的坑！》
    * 如何自定义注解实现功能
    * Spring MVC运行流程
    * Spring MVC启动流程
    * Spring 的单例实现原理
    * Spring 框架中用到了哪些设计模式
    * Spring 其他产品（Spring Boot，Spring Cloud，Spring Secuirity，Spring Data,Spring AMQP等）
    * 有没有用到Spring Book，Spring Boot的认识，原理
    * MyBatis的原理
  * Netty
    * 为什么选择Netty
    * 说说业务中，Netty的使用场景
    * 原生的NIO在JDK1.7版本存在epoll bug
    * 什么是TCP粘包/拆包
    * Netty线程模型
    * 说说Netty的零拷贝
    * Netty内部执行流程
    * Netty重连实现
  * Tomcat
    * Tomcat的基础架构（Server，Service，Connector，Container）
    * Tomcat如何加载Servlet
    * Pipeline-Value机制

* 分布式

  * Nginx
    * 请解释什么是10K问题或者知道什么是10K问题吗？
    * Nginx简介
    * 正向代理和反向代理
    * Nginx几种常见的负载均衡策略
    * Nginx服务器上的Master和Worker进程分别是什么
    * 使用“反向代理”的优点是什么？
  * 分布式其他
    * 谈谈业务中使用分布式的场景
    * Session分布式方案
    * Session分布式处理
    * 分布式锁的应用场景，分布式锁的产生原因，基本概念
    * 分布式锁的常见解决方案
    * 集群与负载均衡的算法与实现
    * 说说分库与分表设计
    * 分库与分表带来的分布式困境与应对之策
  * Dubbo
    * 什么是Dubbo
    * 什么是RPC，如何实现RPC,RPC的实现原理
    * Dubbo中的SPI是什么概念
    * Dubbo的基本原理，执行流程

* 微服务

  * 微服务
    * 前后端分离是如何做的？
    * 微服务有哪些框架
    * Spring Cloud的常见组件有哪些
    * 领域驱动有了解吗？什么是领域驱动模型？充血模型，贫血模型
    * JWT有了解吗，什么是JWT
    * 你怎么理解RESTful
    * 说说如何设计一个良好的API
    * 如何理解RESTful API的幂等性
    * 如何保证接口的幂等性
    * 说说CAP定理，BASE理论
    * 怎么考虑数据一致性问题
    * 说说最终一致性的实现方案
    * 微服务与SOA的区别
    * 如何拆分服务，水平分割，垂直分割
    * 如何应对微服务的链式调用异常
    * 如何快速追踪与定位问题
    * 如何保证微服务的安全，认证
  * 安全问题
    * 如何防范常见的Web攻击，如何防止SQL注入
    * 服务端通信安全攻防
    * HTTPS原理剖析，降级攻击，HTTP与HTTPS的对比
  * 性能优化
    * 性能指标有哪些
    * 如何发现性能瓶颈
    * 性能调优的常见手段
    * 说说你在项目中如何进行性能调优

* 其他

  * 设计能力
    * 说说你在项目中使用过的UML图
    * 如何考虑组件化，服务化，系统拆分
    * 秒杀场景如何设计
  * 需求分析
    * 你如何对需求原型进行理解和拆分
    * 说说你对功能性需求的理解
    * 说说你对非功能性需求的理解
    * 你针对产品提出哪些交互和改进意见
    * 你如何理解用户痛点
  * 业务工程
    * 说说你的开发流程，如何进行自动化部署
    * 你和团队是如何沟通的
    * 你如何进行代码评审
    * 说说你对技术与业务的理解
    * 说说你在项目中遇到感觉最难的Bug，是如何解决的
    * 介绍一下工作中的一个你认为最有价值的项目，以及在这个过程中的角色，解决的问题，你觉得你们项目还有哪些不足的地方
  * 软实力
    * 说说你的优缺点，亮点
    * 说说你最近再开什么书，什么博客，在研究什么新技术，再看哪些开源项目的源代码
    * 说说你觉得最有意义的技术书籍
    * 工作之余做什么事情，平时是如何学习的，怎样提升自己的能力
    * 说说个人发展方向方面的思考
    * 说说你认为的服务端开发工程师应该具备哪些能力
    * 说说你认为的架构师是什么样的，架构师主要做什么
    * 如何看待加班的问题



