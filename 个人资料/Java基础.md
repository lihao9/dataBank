# Java基础 #
## ==和eques、hashCode区别 ##
- ==在比较基本数据时比对的是值；在比较对象时，比较的是对象的地址。
- eques是Object类的方法，在未重写该方法时，会调用 == 方法。但大多数类都重写了该方法，比对对象是否相等
- hashCode获取一个hash值，（对象的内存地址基础上经过特定算法返回一个hash码）

## int和Integer的区别 ##
- int为java中的基本数据类型默认值为0
- Integer为int的封装类型默认值为null
- 为了对数字的重复利用，java会对int和Integer进行自动装箱和拆箱操作

        Integer x = new Integer(100);
        Integer y = new Integer(100);
        int z = 100;
        Integer q = 100;
        Integer w = 100;
		//    x==y  false  对象地址
		//    z==x   true  自动拆箱
		//    q==w   true  -128-127数值相等


## JVM内存划分 ##
- 程序计数器：可以看作当前线程所执行的字节码的指示器（字节码的地址）**线程私有**
- 栈（Java栈）：每当一个线程去执行方法时，就会创建一个栈帧，用于存储局部变量表、操作数栈，动态链接、每一个方法从被调用到执行完成的过程，都对应着一个栈帧从入栈到出栈的过程**线程私有**
- 本地方法栈：和栈差不多，为Native方法（Java调用非Java代码--JNI）服务**线程私有**
- 堆：几乎存放对象（并非所有对象都在堆中）GC工作的**多线程共享**
- 方法区：用于存储已被虚拟机加载的类信息、常量、静态变量、即时编译器编译后的代码等数据**多线程共享**

## String、StringBuffer、StringBuilder区别 ##
- String常量字符串，不可变，每次操作都会生成新的对象
- StringBuilder和StringBuffer类的对象被多次修改不会产生新对象
- StringBuffer线程安全，效率低
- StringBuilder线程不安全，效率高

## 接口和抽象类的理解、区别 ##
- 抽象类：可以理解为对象方法的抽象（同一类对象有同类的方法，但是其具体对象的方法不一样）--多态性体现
- 接口：抽象类的极端情况，多个对象公共行为的提取（能够被调用的方法）；为了把模块固化的契约，为了降低耦合度。

### 区别 ###
**接口**

- 接口中可以又自己的成员变量--但是会被隐式的指定为public static final
- 接口只定义抽象方法
- 实现接口必须实现其所有方法

**抽象类**

- 被abstracta修饰的类为抽象类
- 含有抽象方法的类一定是抽象类，但是抽象类不一定含有抽象方法；且抽象方法必须是public或protected，否则不能被子类继承。默认为public。
- 抽象类中可以定义自己的成员变量和成员方法；
  

