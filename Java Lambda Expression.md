# Java Lambda Expression

**Lambda表达式就是解决了匿名内部类方法冗余的语法现象**

1. 函数式接口里只能有一个方法
2. 小公式
   + 拷贝小括号（拷贝接口里的方法括号包括参数）
   + 写死右箭头
   + 落地大括号（里面写业务逻辑方法）
3. **@FunctionalInterface**
4. **default** Java8 接口可以有一定的实现 可以有多个
5. **static** 还可以定义静态方法 可以多个

## 源码举例

Runnable接口

```java
@FunctionalInterface
public interface Runnable {
		public abstract void run();
}
```

## Demo

```java
   /**
     * @FunctionalInterface 可写可不写 只要保证接口里只有一个方法
     *
     */
    @FunctionalInterface
    interface Foo {
    //	public void sayHello();

        public int add(int x, int y);

        public default int mul(int x, int y) {
            return x * y;
        }

        public default int mul2(int x, int y) {
            return x * y;
        }

        public static int div(int x, int y) {
            return x / y;
        }

        public static int div2(int x, int y) {
            return x / y;
        }

    }    


    public static void main(String[] args) {
//        Foo foo = new Foo() {
//            @Override
//            public void sayHello() {
//
//                System.out.println("test....test");
//
//            }
//
//            @Override
//            public int add(int x, int y) {
//                return 0;
//            }
//        };
//
//        foo.sayHello();

//        Foo foo = () -> {
//            System.out.println("test....Lambda");
//        };
//        foo.sayHello();


        Foo foo = (int x, int y) -> {
            System.out.println("test Lambda with param and return");
            return x + y;
        };
        System.out.println(foo.add(1, 2));

        System.out.println(foo.mul(3, 1));

        System.out.println(Foo.div(6, 2));
    }
```

