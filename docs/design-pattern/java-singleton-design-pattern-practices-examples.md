# Java 单体设计模式实践示例

> 原文:[https://www . geesforgeks . org/Java-singleton-design-pattern-practices-examples/](https://www.geeksforgeeks.org/java-singleton-design-pattern-practices-examples/)

在[之前的](https://www.geeksforgeeks.org/singleton-design-pattern-introduction/)文章中，我们详细讨论了单体设计模式和单体类[实现](https://www.geeksforgeeks.org/singleton-design-pattern/)。
在本文中，我们将看到如何创建单例类。阅读本文后，您将能够根据您的用途、简单性和消除的瓶颈来创建您的单例类。
在 Java 中有很多方法可以做到这一点。所有这些方式在模式的实现上都有所不同，但最终，它们都实现了单个实例的相同最终结果。

1.  **急切初始化:**这是创建单例类最简单的方法。在这种情况下，类的对象是在被 JVM 加载到内存中时创建的。这是通过直接为引用分配一个实例来完成的。
    当程序总是使用这个类的实例时，或者创建实例的成本在资源和时间方面不是太大时，可以使用它。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java code to create singleton class by
// Eager Initialization
public class GFG
{
  // public instance initialized when loading the class
  private static final GFG instance = new GFG();

  private GFG()
  {
    // private constructor
  }
  public static GFG getInstance(){
        return instance;
    }
}
```

1.  **优点:**
    1.  实现起来非常简单。
    2.  可能导致资源浪费。因为不管是否需要，类的实例总是被创建的。
    3.  如果不需要，在创建实例时也会浪费 CPU 时间。
    4.  异常处理是不可能的。
2.  **使用静态块:**这也是热切初始化的子部分。唯一的区别是对象是在静态块中创建的，这样我们就可以访问它的创建，比如异常处理。同样以这种方式，在类加载时创建对象。
    当在创建具有急切初始化的对象时有可能出现异常时，可以使用它。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java code to create singleton class
// Using Static block
public class GFG
{
  // public instance
  public static GFG instance;

  private GFG()
  {
    // private constructor
  }
static
  {
    // static block to initialize instance
    instance = new GFG();
  }
}
```

1.  **优点:**
    1.  实现起来非常简单。
    2.  不需要实现 getInstance()方法。实例可以直接访问。
    3.  异常可以在静态块中处理。
    4.  可能导致资源浪费。因为不管是否需要，类的实例总是被创建的。
    5.  如果不需要，在创建实例时也会浪费 CPU 时间。
2.  **惰性初始化:**在这个方法中，只有在需要的时候才会创建对象。这可以防止资源浪费。需要 getInstance()方法的实现来返回实例。有一个空检查，如果没有创建对象，那么创建，否则返回先前创建的。为了确保该类不能以任何其他方式实例化，构造函数被设为 final。由于对象是在方法中用创建的，它确保除非需要，否则不会创建对象。实例是私有的，因此没有人可以直接访问它。
    它可以在单线程环境中使用，因为多线程可以破坏 singleton 属性，因为它们可以同时访问 get instance 方法并创建多个对象。

## Java 语言（一种计算机语言，尤用于创建网站）

```
//Java Code to create singleton class
// With Lazy initialization
public class GFG
{
  // private instance, so that it can be
  // accessed by only by getInstance() method
  private static GFG instance;

  private GFG()
  {
    // private constructor
  }

  //method to return instance of class
  public static GFG getInstance()
  {
    if (instance == null)
    {
      // if instance is null, initialize
      instance = new GFG();
    }
    return instance;
  }
}
```

1.  **优点:**
    1.  只有在需要时才会创建对象。它可以克服资源的消耗和 CPU 时间的浪费。
    2.  方法中也可以进行异常处理。
    3.  每次必须检查 null 的条件时。
    4.  无法直接访问实例。
    5.  在多线程环境中，它可能会破坏 singleton 属性。
2.  **线程安全单例:**创建了一个线程安全的单例，这样即使在多线程环境中也能维护单例属性。为了使单例类线程安全，getInstance()方法被同步，这样多个线程就不能同时访问它。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to create Thread Safe
// Singleton class
public class GFG
{
  // private instance, so that it can be
  // accessed by only by getInstance() method
  private static GFG instance;

  private GFG()
  {
    // private constructor
  }

 //synchronized method to control simultaneous access
  synchronized public static GFG getInstance()
  {
    if (instance == null)
    {
      // if instance is null, initialize
      instance = new GFG();
    }
    return instance;
  }
}
```

1.  **优点:**
    1.  惰性初始化是可能的。
    2.  它也是线程安全的。
    3.  getInstance()方法是同步的，因此由于多个线程不能同时访问它，因此会导致性能下降。
2.  **带双重检查锁定的惰性初始化:**在这个机制中，我们克服了同步代码的开销问题。在这个方法中，getInstance 是不同步的，但是创建实例的块是同步的，因此最少数量的线程必须等待，这只是第一次。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java code to explain double check locking
public class GFG
{
  // private instance, so that it can be
  // accessed by only by getInstance() method
  private static GFG instance;

  private GFG()
  {
    // private constructor
  }

  public static GFG getInstance()
  {
    if (instance == null)
    {
      //synchronized block to remove overhead
      synchronized (GFG.class)
      {
        if(instance==null)
        {
          // if instance is null, initialize
          instance = new GFG();
        }

      }
    }
    return instance;
  }
}
```

1.  **优点:**
    1.  惰性初始化是可能的。
    2.  它也是线程安全的。
    3.  同步关键字降低了性能开销。
    4.  第一次，会影响性能。
2.  **Bill Pugh Singleton 实现:**在 Java5 之前，内存模型存在很多问题，上述方法在多线程环境中的某些场景下会导致失败。因此，比尔·普格提出了一个用于单例的内部静态类的概念。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java code for Bill Pugh Singleton Implementation
public class GFG
{

  private GFG()
  {
    // private constructor
  }

  // Inner class to provide instance of class
  private static class BillPughSingleton
  {
    private static final GFG INSTANCE = new GFG();
  }

  public static GFG getInstance()
  {
    return BillPughSingleton.INSTANCE;
  }
}
```

1.  当加载单例类时，内部类不会被加载，因此在加载类时不会创建对象。内部类仅在调用 getInstance()方法时创建。所以这看起来像是急切的初始化，但实际上是懒惰的初始化。
    这是最广泛使用的方法，因为它不使用同步。

**什么时候用什么**

1.  急切初始化很容易实现，但它可能会造成资源和 CPU 时间的浪费。只有当初始化一个类的成本在资源方面更低或者你的程序总是需要类的实例时，才使用它。
2.  通过在急切初始化中使用静态块，我们可以提供异常处理，还可以控制实例。
3.  使用 synchronized 我们可以在多线程环境中创建单例类，但是它会导致性能下降，所以我们可以使用 Double check 锁定机制。

4.  Bill Pugh 实现是单例类最广泛使用的方法。大多数开发人员更喜欢它，因为它简单且有优势。

本文由**维沙尔·加尔格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。