# 责任链设计模式

> 原文:[https://www . geesforgeks . org/chain-response-design-pattern/](https://www.geeksforgeeks.org/chain-responsibility-design-pattern/)

责任链模式用于在软件设计中实现松散耦合，其中来自客户端的请求被传递给对象链来处理它们。稍后，链中的对象将自行决定谁将处理该请求，以及是否需要将该请求发送到链中的下一个对象。
**责任链模式适用的地点和时间:**

*   当您想要分离请求的发送者和接收者时
*   运行时确定的多个对象是处理请求的候选对象
*   当您不想在代码中显式指定处理程序时
*   当您想要向几个对象中的一个发出请求而不显式指定接收者时。

当多个对象可以处理一个请求，并且处理程序不必是特定的对象时，建议使用这种模式。另外，处理程序是在运行时确定的。请注意，任何处理程序根本不处理的请求都是有效的用例。

![](img/e584eba8d0440616bd1549f2eb8ccde9.png)

*   **处理程序:**这可以是一个主要接收请求并将请求分派给处理程序链的接口。它只引用了链中的第一个处理程序，对其余的处理程序一无所知。
*   **具体处理程序:**这些是以某种顺序链接的请求的实际处理程序。
*   **客户端:**请求的发起者，这将访问处理程序来处理它。

**如何使用责任链**在应用程序中发送请求

需要处理请求的客户机将其发送到处理程序链，处理程序链是扩展处理程序类的类。
链中的每个处理程序轮流尝试处理它从客户端接收的请求。
如果 ConcreteHandler1 可以处理它，那么请求就被处理，如果不能，它就被发送到链中的下一个处理程序 ConcreteHandler2。
**我们来看一个责任链设计模式的例子:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Chain
{
Processor chain;

public Chain(){
    buildChain();
}

private void buildChain(){
    chain = new NegativeProcessor(new ZeroProcessor(new PositiveProcessor(null)));
}

public void process(Number request) {
    chain.process(request);
}

}

abstract class Processor 
{ 
    private Processor processor;

    public Processor(Processor processor){
        this.processor = processor;
    };

    public void process(Number request){
        if(processor != null)
            processor.process(request);
    }; 
} 

class Number 
{ 
    private int number; 

    public Number(int number) 
    { 
        this.number = number; 
    } 

    public int getNumber() 
    { 
        return number; 
    } 

} 

class NegativeProcessor extends Processor 
{ 
    public NegativeProcessor(Processor processor){
        super(processor);

    }

    public void process(Number request) 
    { 
        if (request.getNumber() < 0) 
        { 
            System.out.println("NegativeProcessor : " + request.getNumber()); 
        } 
        else
        { 
            super.process(request); 
        } 
    } 
} 

class ZeroProcessor extends Processor 
{ 
    public ZeroProcessor(Processor processor){
        super(processor);
    }

    public void process(Number request) 
    { 
        if (request.getNumber() == 0) 
        { 
            System.out.println("ZeroProcessor : " + request.getNumber()); 
        } 
        else
        { 
            super.process(request); 
        } 
    } 
} 

class PositiveProcessor extends Processor 
{ 

    public PositiveProcessor(Processor processor){
        super(processor);
    }

    public void process(Number request) 
    { 
        if (request.getNumber() > 0) 
        { 
            System.out.println("PositiveProcessor : " + request.getNumber()); 
        } 
        else
        { 
            super.process(request); 
        } 
    } 
} 

class TestChain 
{ 
    public static void main(String[] args) { 
        Chain chain = new Chain();

        //Calling chain of responsibility 
        chain.process(new Number(90)); 
        chain.process(new Number(-50)); 
        chain.process(new Number(0)); 
        chain.process(new Number(91)); 
    } 
} 
```

**Output:** 

```
PositiveProcessor : 90
NegativeProcessor : -50
ZeroProcessor : 0
PositiveProcessor : 91
```

**责任链设计模式的优势**

*   降低耦合度。它将要求发送方和接收方解耦。
*   简化对象。对象不需要知道链结构。
*   提高任务分配的灵活性。通过更改链中的成员或更改其顺序，允许动态添加或删除责任。
*   增加请求处理新类的非常方便。

**责任链设计模式的劣势**

*   请求必须被接收，不能保证。
*   系统的性能会受到影响，而且在代码调试不容易的时候可能会造成循环调用。
*   由于调试，观察操作特性可能不容易。

**进一步阅读:**[Python 中的责任链设计模式](https://www.geeksforgeeks.org/chain-of-responsibility-python-design-patterns/)

本文由 [**Saket Kumar**](https://github.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。