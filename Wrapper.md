# Wrapper包装类

##八种基本数据类型 及其包装类

<img src="http://img.tomato530.com/Wrapper.png" style="zoom:1000%;" />

## 基本数据类型 包装类 和String类之间的转化

![](http://img.tomato530.com/WrapperTrans.png)

***

**两个没有子父类关系的类之间不能强转** 

比如下面的代码 会报错！ 会报错！

```java
String str = "123";
Integer i = (Integer) str;

Date date = new Date();
String str = (String) date;
```

## 常见面试题

```java
Object o = true ? new Integer(1) : new Double(2.0);
System.out.println(o);

// 输出为1.0 因为三元运算符要统一两侧的类型 低的向高的转
```

```java
Integer i = new Integer(1);
Integer j = new Integer(1);
System.out.println(i == j); // 不是同一个对象 false

Integer m = 1;
Integer n = 1;
System.out.println(m == n); // 自动装箱 1==1 true

Integer x = 128; // 相当于new了个Integer对象
Integer y = 128; // 相当于new了个Integer对象
System.out.println(x == y); 
// Integer 类中的 IntegerCache 
// 中的 cache[] 保存了范围是 -128 ～ 127的整数 在此范围内直接使用数组中的元素 不用再new 提高效率 超过这个范围会新new个Integer对象 so false 
```