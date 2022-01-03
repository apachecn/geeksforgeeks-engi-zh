# 软件测试中的渐进式测试

> 原文:[https://www . geesforgeks . org/progressive-testing-in-software-testing/](https://www.geeksforgeeks.org/progressive-testing-in-software-testing/)

**渐进式测试**也称为增量测试。在[软件测试](https://www.geeksforgeeks.org/software-testing-basics/)中，增量测试指的是一个接一个的测试模块。当在应用程序中测试父子模块时，需要首先测试与其相关的模块。

让我们更深入地了解一下渐进式测试/增量测试。该增量测试被认为是属于[集成测试](https://www.geeksforgeeks.org/software-engineering-integration-testing/)的子测试技术。实际上，这个测试作为一种方法/策略来执行软件产品的集成测试，而不是直接的测试活动。

在对软件的每个独立组件完成[单元测试](https://www.geeksforgeeks.org/unit-testing-software-testing/)之后，执行[集成测试](https://www.geeksforgeeks.org/software-engineering-integration-testing/)以确保系统组件之间的正确接口和交互。增量测试或渐进式测试被视为集成测试的部分阶段。首先它对独立组件执行集成测试，然后它继续集成组件并相应地对它们执行集成测试。由于组件是以增量方式集成的，这也是它被称为增量测试的原因。

**增量测试工作:**

*   对系统的每个单元进行单元测试，通过单元测试后，将其隔离。
*   每个单元都用所需的参数进行独立测试，以补偿与其他组件的集成测试。
*   单元被组装，集成测试被逐步执行。

**增量测试方法:**

1.  [**自下而上的方法**](https://www.geeksforgeeks.org/steps-in-bottom-up-integration-testing/)**–**
    在自下而上的方法中，所有组件从底层到顶层逐个组合，直到所有组件集成。
2.  [**自上而下进场**](https://www.geeksforgeeks.org/software-engineering-integration-testing/) **–**
    在自上而下的方法中，所有组件从顶层到底层逐一组合，直到所有组件集成。存根被用来代替必要的组件。
3.  **功能方法–**
    在功能方法中，测试是横向进行的，这意味着集成是基于功能完成的。这就是为什么它也被命名为功能增量。
4.  **混合方法–**
    在混合方法中，同时遵循自上而下方法和自下而上方法。在本文中，我们利用了自顶向下方法和自底向上方法的优点。

**增量测试要点:**

*   增量测试包括对每个组件执行集成测试。
*   为了满足其他必要单元或组件的要求，使用驱动程序和存根作为替代。
*   但是存根可能会增加软件的复杂性。
*   与大型子系统相比，小型子系统中的缺陷/故障很容易检测出来。
*   这是一个耗时的过程，植入需要大量的时间。
*   增量方法比非增量方法在早期检测任何缺陷方面更有优势。