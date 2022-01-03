# 设计图案|第一套(简介)

> 原文:[https://www . geesforgeks . org/design-patterns-set-1-introduction/](https://www.geeksforgeeks.org/design-patterns-set-1-introduction/)

设计模式为软件设计中出现的常见问题提供了通用的可重用解决方案。该模式通常显示类或对象之间的关系和交互。这个想法是通过提供经过良好测试的、经过验证的开发/设计范例来加快开发过程。设计模式是独立于编程语言的解决常见问题的策略。这意味着设计模式代表一个想法，而不是一个特定的实现。通过使用设计模式，您可以使代码更加灵活、可重用和可维护。

在项目中总是实现设计模式并不是强制性的。设计模式并不意味着项目开发。设计模式是用来解决常见问题的。每当有需要时，您必须实现一个合适的模式来避免将来出现这样的问题。要找出使用哪种模式，你只需要试着理解设计模式及其目的。只有这样做，你才能选择正确的。

**目标:**
了解每个设计模式的目的和用法，以便根据需要挑选和实施正确的模式。

**示例:**
在许多现实世界中，我们只想创建一个类的一个实例。例如，在任何给定时间，一个国家只能有一位现任总统。这种模式被称为单例模式。其他软件示例可能是由多个对象共享的单个数据库连接，因为为每个对象创建单独的数据库连接成本很高。同样，应用程序中可以有一个配置管理器或错误管理器来处理所有问题，而不是创建多个管理器。

**设计模式类型**
设计模式主要有三种类型:

1.  **Creational** 
    These design patterns are all about class instantiation or object creation. These patterns can be further categorized into Class-creational patterns and object-creational patterns. While class-creation patterns use inheritance effectively in the instantiation process, object-creation patterns use delegation effectively to get the job done. 

    创造性设计模式是*工厂方法、抽象工厂、构建器、单例、对象池和原型。*

    创建设计模式的用例-
    1)假设一个开发人员想要创建一个简单的 DBConnection 类来连接到一个数据库，并且想要从代码中访问多个位置的数据库，通常开发人员要做的是创建一个 DBConnection 类的实例，并在任何需要的地方使用它来进行数据库操作。这将导致从数据库创建多个连接，因为每个数据库连接类实例都有一个到数据库的独立连接。为了处理这个问题，我们创建了一个单独的 DBConnection 类，这样就只创建了一个 DBConnection 的实例，并建立了一个连接。因为我们可以通过一个实例管理数据库连接，所以我们可以控制负载平衡、不必要的连接等。

    2)假设您想要创建多个相似类型的实例，并且想要实现松散的[耦合](https://www.geeksforgeeks.org/coupling-in-java/)，那么您可以选择工厂模式。实现工厂设计模式的类充当多个类之间的桥梁。考虑一个使用多个数据库服务器的例子，如 SQL Server 和 Oracle。如果您正在使用 SQL Server 数据库作为后端开发应用程序，但将来需要将数据库更改为 oracle，您将需要修改所有代码，因此，由于工厂设计模式保持松耦合和易于实现，我们应该选择工厂设计模式，以实现松耦合和创建类似类型的对象。

2.  **Structural** 
    These design patterns are about organizing different classes and objects to form larger structures and provide new functionality. 

    结构设计模式有*适配器、桥、复合、装饰、外观、Flyweight、私有类数据和代理。*

    结构设计模式的用例-

    1)当两个接口彼此不兼容，并希望通过适配器在它们之间建立关系时，这被称为适配器设计模式。适配器模式将一个类的接口转换成客户端期望的另一个接口或类，即适配器让类一起工作，否则由于不兼容而无法工作。因此，在这些类型的不兼容场景中，我们可以选择适配器模式。

3.  **Behavioral** 
    Behavioral patterns are about identifying common communication patterns between objects and realizing these patterns. 

    行为模式是*责任链、命令、解释器、迭代器、中介器、纪念品、空对象、观察者、状态、策略、模板方法、访问者*

    行为设计模式的用例-

    1)模板模式定义了操作中算法的框架，将一些步骤推迟到子类。模板方法允许子类在不改变算法结构的情况下重新定义算法的某些步骤。例如，在您的项目中，您希望模块的行为能够扩展，这样我们就可以随着应用程序需求的变化，或者为了满足新应用程序的需求，使模块以新的和不同的方式运行。然而，任何人都不允许对其进行源代码更改，也就是说，在开发人员可以接近模板设计模式的情况下，您可以添加但不能修改结构。

**参考文献:**T2[https://sourcemaking.com/design_patterns](https://sourcemaking.com/design_patterns)T5[https://sourcemaking.com/design_patterns/singleton](https://sourcemaking.com/design_patterns/singleton)

本文由**阿比吉特·萨哈****塔努嘉·普拉哈拉伊**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。