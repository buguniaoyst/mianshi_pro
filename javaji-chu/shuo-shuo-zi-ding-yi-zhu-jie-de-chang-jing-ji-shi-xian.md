# 说说自定义注解的场景及实现

## 1.注解的基本概念

Java 注解就像修饰符一样，可以用于从java代码中抽取文档、跟踪代码中的依赖性或者在编译时做检查。注解可以被应用在包、类、方法、成员变量、参数和本地变量的声明中。我们大多数人最先接触的注解就是@Override。

注解的工作原理就是，先使用注解修饰java代码，然后另一块叫做注解处理器的代码会解析这段注解和被修饰的代码并做相应的处理。

## 2.JDK内置的标准注解

JavaSE中内置了三个标准注解，都是定义在java.lang中，它们是：

* @Override:用于修饰子类的方法覆盖了父类中的方法；

* @Deprecated:用于修饰已经过时了的方法，不推荐使用的方法；

* @SuppressWarnnings:告诉java编译器禁止编译警告。

### 2.1 @Override

@Override很简单，只是一个标记，用于标注一个方法。它表示，被它标注的方法覆盖了父类的方法。如果一不小心，子类的方法名写错了，有了@Override之后，编译时会报错。也就是说被@Override标注的方法如果没有覆盖父类的方法，编译时报错。

### 2.2 @Deprecated

@Deprecated也是一个标记注解，用于修饰一个方法。它表示此方法不推荐使用。无论是继承、覆盖或直接使用此方法，编译器都会给出警告。

### 2.3 @SuppressWarnings

字面翻译就是抑制警告，它用于告诉编译器，对被标注的这句代码不要给出特定的警告。

@SuppressWarnings有一些参数用于表示特定的警告：

## 3.自定义注解

java允许我们自己定义注解，它提供了元注解用于自定义注解。

### 3.1 元注解

java提供元注解的目的就是让开发者自定义注解，元注解负责注解自定义注解。

@Target；

@Retention；

@Documented；

@Inherited。

Java5.0定义了4个元注解。接下来，分别分析这四个元注解：

#### 3.1.1 @Target

@Target用来说明自定义注解可以用在什么地方，其ElementType取值有：

1. CONSTRUCTOR:用于描述构造方法

2. FIELD:用于描述成员变量

3. LOCAL\_VARIABLE:用于描述局部变量

4. METHOD:用于描述方法

5. PACKAGE:用于描述包

6. PARAMETER:用于描述参数

7. TYPE:用于描述类、接口\(包括注解类型\) 或enum声明

使用示例：@Target\(ElementType.FIELD\)

#### 3.1.2 @Retention

@Retention用来描述自定义注解的生命周期，其RetentionPoicy取值有：

1. SOURCE:在源文件中有效

2. CLASS:在class文件中有效

3. RUNTIME:在运行时有效

使用示例：@Retention\(RetentionPolicy.RUNTIME\)

#### 3.1.3 @Documented

@Documented用于表示自定义注解可以被javadoc之类的工具文档化，没有成员。

使用示例：@Documented

#### 3.1.4 @Inherited

@Inherited 元注解是一个标记注解，@Inherited阐述了某个被标注的类型是被继承的。如果一个使用了@Inherited修饰的annotation类型被用于一个class，则这个annotation将被用于该class的子类。

@Inherited annotation类型是被标注过的class的子类所继承。类并不从它所实现的接口继承annotation，方法并不从它所重载的方法继承annotation。

当@Inherited annotation类型标注的annotation的Retention是RetentionPolicy.RUNTIME，则反射API增强了这种继承性。如果我们使用java.lang.reflect去查询一个@Inherited annotation类型的annotation时，反射代码检查将展开工作：检查class和其父类，直到发现指定的annotation类型被发现，或者到达类继承结构的顶层。

使用示例：@Inherited

### 3.2 自定义注解实现

#### 3.2.1 创建一个注解

```java
//在成员变量上使用
@Target(ElementType.FIELD)
//在代码运行期间起作用
@Retention(RetentionPolicy.RUNTIME)
//注解将被包含在javadoc中
@Documented
public @interface PhoneName {
    String value() default "";
}
```

#### 3.2.2 使用注解

```java
public class MyPhone {
    @PhoneName(value = "华为手机")
    private String name;
}
```

#### 3.2.3 解析注解

```java
public class AnnUtil {
    /**
     * 解析注解的方法
     *
     * @param clazz
     */
    public static void getPhoneInfo(Class<?> clazz) {
        Field[] fields = clazz.getDeclaredFields();
        for (Field field : fields) {
            if (field.isAnnotationPresent(PhoneName.class)) {
                PhoneName phoneName =  field.getAnnotation(PhoneName.class);
                String pName = phoneName.value();
                System.out.println("手机的名字："+pName);
            }
        }

    }
}
```

#### 3.2.4测试

```java
public class AnnTest {
    public static void main(String[] args) {
        AnnUtil.getPhoneInfo(MyPhone.class);
    }
}

```



