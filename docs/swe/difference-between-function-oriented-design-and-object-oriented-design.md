# 面向功能设计和面向对象设计的区别

> 原文:[https://www . geesforgeks . org/面向功能的设计和面向对象的设计的区别/](https://www.geeksforgeeks.org/difference-between-function-oriented-design-and-object-oriented-design/)

**1。功能导向设计:**
功能导向设计是关注程序功能的结果。这是基于逐步细化。逐步细化基于迭代过程分解。逐步细化是一种自上而下的策略，在这种策略中，一个程序被细化为一个增加细节层次的层次结构。

我们从程序的高级描述开始。然后，在每一步中，我们从我们的高级描述中提取一部分，并对其进行细化。细化实际上是一个细化的过程。这个过程应该从高度概念性的模型发展到较低层次的细节。每个模块的细化都是在我们达到编程语言的语句级别之前完成的。

**2。面向对象设计:**
面向对象设计是将注意力不集中在程序执行的功能上，而是集中在程序要处理的数据上的结果。因此，它与面向功能的设计是正交的。面向对象的设计始于对现实世界“事物”的检查。就其属性和行为而言，这些东西是单独的特征。

对象是独立的实体，可以很容易地改变，因为所有的状态和表示信息都保存在对象本身中。对象可以是分布式的，可以顺序或并行执行。面向对象技术包含以下三个关键词–

1.  **对象–**
    软件包的设计和开发是为了与包含所有数据和服务的现实世界实体相对应，以充当它们的关联实体消息。

2.  **通信–**
    建立了通信机制，提供了对象协同工作的手段。

3.  **方法–**
    方法是对象为满足问题域的功能需求而执行的服务。对象通过消息请求其他对象的服务。

**面向功能设计和面向对象设计的区别:**

<figure class="table">

| 比较因素 | 面向功能的设计 | 面向对象设计 |
| --- | --- | --- |
| **抽象** | 给用户的基本抽象是真实世界的函数。 | 基本抽象不是真实世界的函数，而是真实世界实体所代表的数据抽象。 |
| **功能** | 函数被组合在一起，由此得到更高级的函数。 | 由于类与其方法相关联，因此函数根据其操作的数据分组在一起。 |
| **状态信息** | 在这种方法中，状态信息通常在集中的共享内存中表示。 | 在这种方法中，状态信息不被表示，也不在集中的存储器中表示，而是在系统的对象中实现或分布。 |
| **接近** | 这是一种自上而下的方法。 | 这是一种自下而上的方法。 |
| **开始基础** | 首先考虑用例图和场景。 | 从识别对象和类开始。 |
| **分解** | 在面向功能的设计中，我们在功能/过程级别进行分解。 | 我们在类级别分解。 |
| **使用** | 这种方法主要用于计算敏感的应用。 | 这种方法主要用于模拟业务或业务案例的演进系统。 |

</figure>