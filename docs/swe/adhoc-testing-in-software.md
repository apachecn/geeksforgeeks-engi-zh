# 软件中的临时测试

> 原文:[https://www.geeksforgeeks.org/adhoc-testing-in-software/](https://www.geeksforgeeks.org/adhoc-testing-in-software/)

先决条件–[软件测试](https://www.geeksforgeeks.org/software-testing-basics/)

**即席测试:**
即席测试是一种软件测试，在正式测试完成后进行非正式的随机测试，找出系统中的任何漏洞。因此，它也被称为随机测试或猴子测试。即席测试不是以结构化的方式进行的，因此它不基于任何方法。这就是为什么即席测试是一种非结构化软件测试。

**特殊测试有–**

*   没有文档。

*   没有测试用例。

*   无测试设计。

因为它不基于任何测试用例，也不需要文档或测试设计，所以解决最终确定的问题对开发人员来说变得非常困难。有时会发现非常有趣和意想不到的错误或不常见的错误，这些错误在存在的书面测试案例中是永远不会发现的。实际上这种特殊测试用于[验收测试](https://www.geeksforgeeks.org/acceptance-testing-software-testing/)。

即席测试节省了大量时间，即席测试的一个很好的例子是，客户在今天下午 6 点前需要产品，但产品开发将在当天下午 4 点完成。所以手头只有有限的时间，也就是说只有 2 小时，所以在这 2 小时内，开发人员和测试人员团队可以通过随机输入测试整个系统，并且可以检查任何错误。

**专项测试的类型:**
专项测试分为以下三种类型。

1.  **Buddy Testing –** 
    Buddy testing is a type of Adhoc testing where two bodies will be involved one is from Developer team and one from tester team. So that after completing one module and after completing [Unit testing](https://www.geeksforgeeks.org/unit-testing-software-testing/) the tester can test by giving random inputs and the developer can fix the issues too early based on the currently designed test cases. 
2.  **Pair Testing –** 
    Pair testing is a type of Adhoc testing where two bodies from the testing team can be involved to test the same module. When one tester can perform the random test and another tester can maintain the record of findings. So when two testers get paired they exchange their ideas, opinions and knowledge so good testing is performed on the module. 
3.  **Monkey Testing–**
    Monkey Testing 是一种即席测试，在这种测试中，系统基于随机输入进行测试，没有任何测试用例，系统的行为被跟踪，系统的所有功能是否工作都受到监控。由于遵循随机性方法，对输入没有约束，因此称为猴子测试。

**专项测试特点:**

*   随机进行即席测试。

*   基于没有文档，没有测试用例和测试设计。

*   正式测试后完成。

*   它遵循一种非结构化的测试方式。

*   与其他测试技术相比，它花费的时间相对较少。

*   它有利于发现测试用例中提到的错误和不一致。

**何时进行专项测试:**

*   当测试系统的时间有限时。

*   当没有明确的测试用例来测试产品时。

*   正式测试完成后。

*   当开发大部分完成时。

**何时不进行专项检测:**

*   当测试用例中存在错误时。

*   进行测试时。

**即席测试的优势:**

*   不能用书面测试用例识别的错误可以通过即席测试来识别。

*   它可以在非常有限的时间内完成。

*   有助于创建独特的测试用例。

*   这个测试有助于构建一个不太容易出现未来问题的强大产品。

*   该测试可以在[软件开发生命周期过程(SDLC)](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/) 的任何时间进行

**临时检测的缺点:**

*   有时，基于识别的问题解决错误是困难的，因为没有书面的测试用例和文档。

*   需要良好的产品知识以及测试概念，以完美地识别任何模型中的问题。

*   它不能保证错误一定会被识别出来。

*   发现一个错误可能需要一些不确定的时间。

**进行专项测试需要遵循的五个惯例:**

1.  良好的软件知识。

2.  找出容易出错的地方。

3.  确定测试区域的优先级。

4.  粗略规划测试计划。

5.  使用正确的工具。