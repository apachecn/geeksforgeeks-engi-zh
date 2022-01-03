# 抽象工厂模式

> 原文:[https://www.geeksforgeeks.org/abstract-factory-pattern/](https://www.geeksforgeeks.org/abstract-factory-pattern/)

**简介**

抽象工厂设计模式是创新模式之一。抽象工厂模式几乎类似于[工厂模式](https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/)被认为是工厂模式之上的另一层抽象。抽象工厂模式围绕一个创建其他工厂的超级工厂工作。
抽象工厂模式实现为我们提供了一个框架，允许我们创建遵循通用模式的对象。因此，在运行时，抽象工厂与能够创建所需类型对象的任何所需的具体工厂相耦合。
**让我们看看抽象工厂模式的 GOFs 表示:**

![](img/d289bf5936be0d14dfbb03a76b29834b.png)

*抽象工厂设计模式的 UML 类图示例。*

*   **抽象工厂**:为创建抽象产品对象的操作声明一个接口。
*   **具体工厂**:实现抽象工厂中声明的操作，创建具体的产品对象。
*   **产品**:定义一个要由对应的具体工厂创建的产品对象，实现抽象产品接口。
*   **客户端**:只使用抽象工厂和抽象产品类声明的接口。

抽象工厂提供用于创建相关或从属对象族的接口，而无需指定它们的具体类。
客户端软件创建抽象工厂的具体实现，然后使用通用接口创建属于对象族的具体对象。
客户端不知道或不关心它从这些具体工厂中的每一个获得哪些具体对象，因为它只使用它们产品的通用接口。
因此，有了抽象工厂模式的想法，我们现在将尝试创建一个设计，这将有助于相关对象的创建。

**实施**

让我们举个例子，假设我们想建立一个全球汽车工厂。如果是[工厂设计模式](https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/)，那么适合单个位置。但是对于这种模式，我们需要多个位置和一些关键的设计更改。
我们每个地方都需要汽车工厂，比如印度汽车工厂、美国汽车工厂和德国汽车工厂。现在，我们的应用程序应该足够智能，能够识别使用它的位置，因此我们应该能够使用适当的汽车工厂，甚至不知道哪个汽车工厂实现将在内部使用。这也让我们避免了有人打电话给错误的工厂。
这里我们需要另一个抽象层，它将识别位置并在内部使用正确的汽车工厂实现，甚至不需要给用户任何提示。这正是一个抽象工厂模式用来解决的问题。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate the
// working of Abstract Factory Pattern

enum CarType
{
    MICRO, MINI, LUXURY
}

abstract class Car
{
    Car(CarType model, Location location)
    {
        this.model = model;
        this.location = location;
    }

    abstract void construct();

    CarType model = null;
    Location location = null;

    CarType getModel()
    {
        return model;
    }

    void setModel(CarType model)
    {
        this.model = model;
    }

    Location getLocation()
    {
        return location;
    }

    void setLocation(Location location)
    {
        this.location = location;
    }

    @Override
    public String toString()
    {
        return "CarModel - "+model + " located in "+location;
    }
}

class LuxuryCar extends Car
{
    LuxuryCar(Location location)
    {
        super(CarType.LUXURY, location);
        construct();
    }
    @Override
    protected void construct()
    {
        System.out.println("Connecting to luxury car");
    }
}

class MicroCar extends Car
{
    MicroCar(Location location)
    {
        super(CarType.MICRO, location);
        construct();
    }
    @Override
    protected void construct()
    {
        System.out.println("Connecting to Micro Car ");
    }
}

class MiniCar extends Car
{
    MiniCar(Location location)
    {
        super(CarType.MINI,location );
        construct();
    }

    @Override
    void construct()
    {
        System.out.println("Connecting to Mini car");
    }
}

enum Location
{
  DEFAULT, USA, INDIA
}

class INDIACarFactory
{
    static Car buildCar(CarType model)
    {
        Car car = null;
        switch (model)
        {
            case MICRO:
                car = new MicroCar(Location.INDIA);
                break;

            case MINI:
                car = new MiniCar(Location.INDIA);
                break;

            case LUXURY:
                car = new LuxuryCar(Location.INDIA);
                break;

                default:
                break;

        }
        return car;
    }
}

class DefaultCarFactory
{
    public static Car buildCar(CarType model)
    {
        Car car = null;
        switch (model)
        {
            case MICRO:
                car = new MicroCar(Location.DEFAULT);
                break;

            case MINI:
                car = new MiniCar(Location.DEFAULT);
                break;

            case LUXURY:
                car = new LuxuryCar(Location.DEFAULT);
                break;

                default:
                break;

        }
        return car;
    }
}

class USACarFactory
{
    public static Car buildCar(CarType model)
    {
        Car car = null;
        switch (model)
        {
            case MICRO:
                car = new MicroCar(Location.USA);
                break;

            case MINI:
                car = new MiniCar(Location.USA);
                break;

            case LUXURY:
                car = new LuxuryCar(Location.USA);
                break;

                default:
                break;

        }
        return car;
    }
}

class CarFactory
{
    private CarFactory()
    {

    }
    public static Car buildCar(CarType type)
    {
        Car car = null;
        // We can add any GPS Function here which
        // read location property somewhere from configuration
        // and use location specific car factory
        // Currently I'm just using INDIA as Location
        Location location = Location.INDIA;

        switch(location)
        {
            case USA:
                car = USACarFactory.buildCar(type);
                break;

            case INDIA:
                car = INDIACarFactory.buildCar(type);
                break;

            default:
                car = DefaultCarFactory.buildCar(type);

        }

        return car;

    }
}

class AbstractDesign
{
    public static void main(String[] args)
    {
        System.out.println(CarFactory.buildCar(CarType.MICRO));
        System.out.println(CarFactory.buildCar(CarType.MINI));
        System.out.println(CarFactory.buildCar(CarType.LUXURY));
    }
}
```

输出:

```
Connecting to Micro Car 
CarModel - MICRO located in INDIA
Connecting to Mini car
CarModel - MINI located in INDIA
Connecting to luxury car
CarModel - LUXURY located in INDIA
```

**差异**

*   “工厂方法”和“抽象工厂”的主要区别在于工厂方法是一个单一的方法，而抽象工厂是一个对象。
*   工厂方法只是一个方法，它可以在子类中被覆盖，而抽象工厂是一个有多个工厂方法的对象。
*   工厂方法模式使用继承，并依赖子类来处理所需的对象实例化。

**优势:**当客户端不知道具体要创建什么类型时，这种模式特别有用。

*   **具体类的隔离:**抽象工厂模式帮助您控制应用程序创建的对象的类。因为工厂封装了创建产品对象的责任和过程，所以它将客户端与实现类隔离开来。客户端通过其抽象接口操纵实例。产品类名在具体工厂的实现中是孤立的；它们不会出现在客户端代码中。
*   **轻松交换产品族:**具体工厂的类在应用程序中只出现一次，也就是它被实例化的地方。这使得更改应用程序使用的混凝土工厂变得很容易。只需更换混凝土工厂，就可以使用各种产品配置。因为一个抽象的工厂创建了一个完整的产品系列，所以整个产品系列会立刻发生变化。
*   **促进产品之间的一致性:**当一个系列中的产品对象被设计为一起工作时，应用程序一次只使用一个系列中的对象是很重要的。抽象工厂使这易于实施。

**缺点**

*   **难以支持新的产品种类:**扩展抽象工厂来生产新的产品种类并不容易。这是因为抽象工厂接口修复了可以创建的产品集。支持新类型的产品需要扩展工厂接口，这涉及到改变抽象工厂类及其所有子类。

上面的例子也是基于像优步和 ola 这样的出租车是如何大规模运行的。
**进一步阅读:**[Python 中的抽象工厂方法](https://www.geeksforgeeks.org/abstract-factory-method-python-design-patterns/)
本文由 [**Saket Kumar**](https://github.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。