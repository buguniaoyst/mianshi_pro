# 说说反射的用途及实现

JAVA反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法；这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制。

## 1.反射的用途

反射在一些通用的框架中用的比较多，如注解或者通过xml配置中的类路径来实例化类。如struts2框架通过struts.xml中配置的Action路径，帮我们实例化Action，然后调用里边的方法。

## 2.反射的实现

### 2.1获取Class对象的方法

* 1.通过静态方法Class.forName\(\)方法获取；

* 2.通过类自身来获取；

* 3.通过Object类中的getClass方法获取；

```java
        /**
         * 获取User类的Class对象的三种方式：
         * 1.通过静态方法Class.forName("")方法获取
         * 2.通过类自身来获取
         * 3.通过Object类中的getClass方法获取
         */
        Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
        System.out.println(userClass1);

        Class<User> userClass2 = User.class;
        System.out.println(userClass2);

        User u = new User();
        Class<? extends User> uClass3 = u.getClass();
        System.out.println(uClass3);
```



