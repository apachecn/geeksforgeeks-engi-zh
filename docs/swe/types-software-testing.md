# 软件测试类型

> 原文:[https://www.geeksforgeeks.org/types-software-testing/](https://www.geeksforgeeks.org/types-software-testing/)

### 导言:-

测试是以发现错误为目的执行程序的过程。为了使我们的软件运行良好，它应该是没有错误的。如果测试成功，它将消除软件中的所有错误。

### 测试原则:-

(I)所有测试应满足客户要求
(ii)要使我们的软件测试应由第三方
执行(iii)不可能进行详尽的测试。因为我们需要基于应用程序风险评估的最佳测试量。
(四)所有要进行的测试都应在实施前进行规划
(五)它遵循帕累托法则(80/20 法则)，即 80%的错误来自 20%的程序组件。
(六)从小零件开始测试，并扩展到大零件。

### 测试类型:-

#### 1.单元测试

它专注于软件设计的最小单元。在这种情况下，我们测试单个单元或一组相互关联的单元。它通常由程序员通过使用样本输入并观察其相应的输出来完成。
示例:

```
a) In a program we are checking if loop, method or 
   function is working fine
b) Misunderstood or incorrect, arithmetic precedence.
c) Incorrect initialization
```

#### 2.集成测试

目标是获取经过单元测试的组件，并构建一个由设计决定的程序结构。集成测试是一组组件组合在一起产生输出的测试。

集成测试有四种类型:(一)自上而下(二)自下而上(三)三明治(四)大爆炸
示例

```
(a) Black Box testing:- It is used for validation. 
In this we ignore internal working mechanism and 
focuse on what is the output?.

(b) White Box testing:- It is used for verification. 
In this we focus on internal mechanism i.e.
how the output is achieved?
```

#### 3.回归测试

每次添加新模块都会导致程序发生变化。这种类型的测试确保整个组件即使在向整个程序添加组件后也能正常工作。
例

```
In school record suppose we have module staff, students 
and finance combining these modules and checking if on 
integration these module works fine is regression testing
```

#### 4.烟雾测试

进行该测试是为了确保测试中的软件准备好或稳定用于进一步测试
它被称为烟雾测试，因为测试最初通过是为了检查它在最初打开时是否没有着火或冒烟。
示例:

```
If project has 2 modules so before going to module 
make sure that module 1 works properly
```

#### 5.阿尔法测试

这是一种验证测试。这是一种*验收测试*，在产品发布给客户之前进行。这通常是由质量保证人员完成的。
示例:

```
When software testing is performed internally within
the organization
```

#### 6.Beta 测试

测试版测试由软件的最终用户在一个或多个客户站点进行。此版本针对有限数量的用户发布，用于在实时环境中进行测试
示例:

```
When software testing is performed for the limited
number of people
```

#### 7.系统试验

这个软件经过测试，可以很好地适用于不同的操作系统。它包含在黑盒测试技术中。在这种情况下，我们只关注所需的输入和输出，而不关注内部工作。
在这里，我们有安全测试、恢复测试、压力测试和性能测试
示例:

```
This include functional as well as non functional 
testing
```

#### 8.压力测试

在本文中，我们给出了系统的不利条件，并检查了它们在这些条件下的表现。
示例:

```
(a) Test cases that require maximum memory or other
    resources are executed
(b) Test cases that may cause thrashing in a virtual 
    operating system
(c) Test cases that may cause excessive disk requirement
```

#### 9.性能试验

它旨在测试集成系统环境中软件的运行时性能。它用于测试程序的速度和有效性。它也被称为负载测试。在其中，我们检查系统在给定负载下的性能。
示例:

```
Checking number of processor cycles.
```

#### 10.面向对象测试

这种测试是各种测试技术的结合，有助于验证和确认面向对象软件。该测试以下列方式进行:

*   需求测试，
*   测试的设计和分析，
*   代码测试，
*   集成测试，
*   系统测试，
*   用户测试。

我们使用这个面向对象的方法来讨论测试计划和执行项目。

本文由**克里特卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。