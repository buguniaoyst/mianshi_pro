# 说说反射的用途及实现

---

JAVA反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法；这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制。

## 1.反射的用途

反射在一些通用的框架中用的比较多，如注解或者通过xml配置中的类路径来实例化类。如struts2框架的请求分发机制就是通过反射技术动态加载struts.xml中配置的各个Action的。

## 2.反射的实现

反射技术在开发中的实现过程：

* 1.动态加载类；

* 2.实例化这个类的对象，获取这个类的成员变量，成员方法；

* 3.改变这个类的属性或者调用这个类的方法（invoke）；

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

### 2.2 通过反射技术动态创建类的对象

通过反射技术动态创建类的对象通常有两种方法：

* 通过Class对象的newInstance\(\)方法调用默认构造实例化对象；
* 手动获取构造方法，然后通过构造方法的newInstance\(\)方法实例化对象；

通过Class对象的newInstance\(\)方法调用类的默认构造来实例化对象：

```java
/**
 * 1.通过静态方法Class.forName("")方法获取
 * 2.通过newInstance()方法来创建User类的对象
 */
Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
System.out.println(userClass1);

User u = (User) userClass1.newInstance();
u.setName("张三");
u.setAge(12);
System.out.println(u);
```

通过构造方法实例化对象：

```java
/**
 * 1.通过静态方法Class.forName("")方法获取
 * 2.获取这个类的构造方法，然后通过构造方法实例化对象
 */
Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
System.out.println(userClass1);

//获取构造方法
Constructor<?> constructor = userClass1.getConstructors()[0];
User u = (User) constructor.newInstance();
u.setName("张三");
u.setAge(13);
System.out.println(u);
```

### 2.3 获取反射类中的成员变量

#### 2.3.1 获取非私有的成员变量

* getField\(String filedName\)：通过成员变量名获取指定非私有的成员变量，返回Field对象；
* getFields\(\)：获取的是反射类下所有的非私有的成员变量；

```java
/**
 * 1.通过静态方法Class.forName("")方法获取；
 * 2.通过成员变量名获取指定的成员变量；
 */
Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
User u = (User) userClass1.newInstance();

//获取指定非私有的成员变量
Field stuNo = userClass1.getField("stuNo");
stuNo.set(u,"1001");
System.out.println(u);
```

#### 2.3.2 获取私有的成员变量

* getDeclaredField\(String name\)：通过成员变量名获取指定的成员变量，返回Field对象；
* getDeclaredFields\(\)：获取所有的成员变量；

```java
/**
 * 1.通过静态方法Class.forName("")方法获取；
 * 2.通过成员变量名获取指定的成员变量；
 */
Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
User u = (User) userClass1.newInstance();

//获取指定非私有的成员变量
Field stuName = userClass1.getDeclaredField("name");
//取消java程序中默认的权限检查
stuName.setAccessible(true);
stuName.set(u,"张三");
System.out.println(u);
```

#### 2.3.3 获取反射类中非私有，非静态的成员方法

* getMethod\(String name,Class&lt;?&gt;... paeameterTypes\)：name为方法名，第二个参数为方法中需要的参数类型，返回一个Method对象；
* getMethods\(\)：返回反射类中的所有非私有，非静态的方法；

```java
/**
* 1.通过静态方法Class.forName("")方法获取；
* 2.通过成员方法名获取指定的成员方法；
*/
Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
User u = (User) userClass1.newInstance();

//获取指定非私有的成员变量
Method setName = userClass1.getMethod("setName", String.class);
setName.invoke(u, "张三");

//打印输出
System.out.println(u);
```

#### 2.3.4获取反射类中私有的成员方法

* getDeclaredMethod\(String name,Class&lt;?&gt;...parameterType\)：获取指定方法名的成员方法；
* getDeclaredMethods\(\)：获取所有的成员方法；

```java
/**
* 1.通过静态方法Class.forName("")方法获取；
* 2.通过成员方法名获取指定的成员方法；
*/
Class<?> userClass1 = Class.forName("com.heima.classdemo.User");
User u = (User) userClass1.newInstance();

//获取指定非私有的成员变量
Method setNameMethod = userClass1.getDeclaredMethod("setName2", String.class);
//取消安全检查
setNameMethod.setAccessible(true);
setNameMethod.invoke(u,"张三");
System.out.println(u);
```



