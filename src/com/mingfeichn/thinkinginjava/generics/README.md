# 泛型（Generics）

## 为什么要使用泛型程序设计？

## 定义简单的泛型类

## 泛型方法

## 类型变量的限定

## 泛型代码和虚拟机
    1. 翻译泛型表达式
    2. 翻译泛型方法
    3. 调用遗留代码

## 泛型约束和局限性
    1. 不能用基本类型实例化类型参数
    2. 运行时类型检查只适用于原始类型
    3. 不能创建参数化类型的数组
    4. Varargs警告
    5. 不能实例化类型变量
    6. 泛型类的静态上下文中类型变量无效
    7. 不能抛出或捕获泛型类的实例
    8. 注意擦除后的冲突


## 泛型类型的继承原则


## 通配符类型
    1. 通配符的超类型限定
    2. 无限定通配符
    3. 通配符捕获

## 反射和泛型
    1. 使用Class<T>参数进行类型匹配
    2. 虚拟机中的泛型类型信息

## class Holder1
Holder1类中引用了内部类Automobile,它无法持有其他类型的对象

## class Holder2
Java SE5前，可以让Holder1持有Object类，这样Holder2就可以存储任何类型的对象

## class Holder3
与其使用object，不如暂时不指定类型，而是稍后决定具体使用什么类型。
要达到这个目的，需要使用类型参数，用尖括号括住，放在类名后面，然后在使用这个类的时候用实际的类型替换此类型参数。
泛型的主要目的之一就是用来指定容器要持有什么类型的对象，由编译器来保证类型的正确性。

现在，当创建Holder3对象时，必须指明想持有什么类型的对象，将其置于<>中。从Holder3中取出持有的对象时，自动地就是正确的类型。

## class TwoTuple
使用泛型解决仅一次方法调用就能返回多个对象，这个概念称为元组，即将一组对象直接打包存储于其中一个单一的对象，这个容器对象允许读取其中元素，
但不允许向其中放新的对象（这个概念也称为数据传送对象，或信使）

元组隐含地保持了其中元素的次序。

final声明使容器中的对象可以被随意读取，但无法被改变，如果想要使用具有不同元素的元组，就强求要求创建一个新的TwoTuple对象。

## class ThreeTuple, FourTuple, FiveTuple
利用继承机制实现长度更长的元素

## class TupleTest
使用泛型实现原则，并测试元组返回多个对象

## class LinkedStack
泛型的只要作用之一是创建容器类。
该类使用泛型实现了链式栈

## class RandomList
使用泛型实现一个列表，每次调用列表的select()方法，会从列表中随机获取一个元素

## package coffee
该包演示了泛型用于接口，实现了一个咖啡类的生成器  
参数化的Generator接口确保next()返回值是参数的类型  
由于CoffeeGenerator实现了Iterator接口，所以可以在循环语句中使用  
第二个构造器作为“末端哨兵”判断了何时停止  

## class Fibonacci
实现了Generator<T>接口，生成Fibonacci数列
基本类型无法作为类型参数，可以通过JAVA SE5后支持的自动封包和自动拆包在基本类型和响应的包装器之间进行转换

## class IterableFibonacci
如果要是class Fibonacci实现Iterable，可以重写Fibonacci生成器，另一种做法是创建一个适配器（adapter）来实现所需接口
class IterableFibonacci演示了通过继承来创建适配器类

## class GenericMethods
泛型方法，类中可以包含参数化方法，无论该类是否是泛型类
泛型方法可以取代将整个类泛型化  
static方法无法访问泛型类的类型参数， 如果static方法需要使用泛型能力，必须使其成为泛型方法  
定义泛型方法，只需将泛型参数列表置于返回值之前 

使用泛型类时，必须在创建对象的时候指定类型参数的值，通过类型参数推断(type argument inference)在使用泛型方法时不必指定参数类型

## class New
使用泛型实现的容器工具类，类型参数推断避免了重复的泛型参数列表 


## class SimplerPets
类型推断的进一步演示

