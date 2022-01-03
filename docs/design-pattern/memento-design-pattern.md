# 纪念品设计图案

> 原文:[https://www.geeksforgeeks.org/memento-design-pattern/](https://www.geeksforgeeks.org/memento-design-pattern/)

纪念品模式是一种行为设计模式。纪念品模式用于将对象的状态恢复到以前的状态。随着应用程序的进展，您可能希望在应用程序中保存检查点，并在以后恢复到这些检查点。

**UML 图纪念品设计模式**

![Memento-Diagram](img/b4f4fbc5bb4af1daca7a84d3d413a905.png)

**设计组件**

*   **发起方:**要保存状态的对象。它会创建纪念品，并在将来使用它来撤销。
*   **纪念物:**将要维持始发者状态的物体。这只是一个 POJO。
*   **看守人:**记录多个纪念品的物体。比如维护保存点。

一个**管理员**想要在**发起者**上执行操作，同时有回滚的可能。管理员在创建者身上调用**creatememoto()**方法，要求创建者将纪念品对象传递给它。此时，创建者创建一个保存其内部状态的纪念品对象，并将该纪念品传递给管理员。看管人保管纪念品并进行操作。在需要撤销操作的情况下，管理员对传递维护的纪念品对象的发起者调用**setmemotion()**方法。发起者会接受纪念品，用它来恢复它以前的状态。

**我们来看一个 Memento 设计模式的例子。**

```
import java.util.List;
import java.util.ArrayList;

class Life
{
    private String time;

    public void set(String time) 
    {
        System.out.println("Setting time to " + time);
        this.time = time;
    }

    public Memento saveToMemento() 
    {
        System.out.println("Saving time to Memento");
        return new Memento(time);
    }

    public void restoreFromMemento(Memento memento) 
    {
        time = memento.getSavedTime();
        System.out.println("Time restored from Memento: " + time);
    }

    public static class Memento 
    {
        private final String time;

        public Memento(String timeToSave) 
        {
            time = timeToSave;
        }

        public String getSavedTime() 
        {
            return time;
        }
    }
}

class Design 
{

    public static void main(String[] args) 
    {

        List<Life.Memento> savedTimes = new ArrayList<Life.Memento>();

        Life life = new Life();

        //time travel and record the eras
        life.set("1000 B.C.");
        savedTimes.add(life.saveToMemento());
        life.set("1000 A.D.");
        savedTimes.add(life.saveToMemento());
        life.set("2000 A.D.");
        savedTimes.add(life.saveToMemento());
        life.set("4000 A.D.");

        life.restoreFromMemento(savedTimes.get(0));   

    }
}
```

输出:

```
Setting time to 1000 B.C.
Saving time to Memento
Setting time to 1000 A.D.
Saving time to Memento
Setting time to 2000 A.D.
Saving time to Memento
Setting time to 4000 A.D.
Time restored from Memento: 1000 B.C.

```

**优势**

*   我们可以使用序列化来实现更通用的 memoto 模式实现，而不是每个对象都需要有自己的 memoto 类实现的 memoto 模式。

**劣势**

*   如果发起人对象非常大，那么纪念品对象的大小也将很大，并使用大量的内存。

**进一步阅读–**[蟒蛇纪念品法](https://www.geeksforgeeks.org/memento-method-python-design-patterns/)

本文由 **[Saket Kumar](https://github.com/saketkumar95)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。