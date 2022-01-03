# 测试覆盖率与代码覆盖率

> 原文:[https://www . geesforgeks . org/test-coverage-vs-code-coverage/](https://www.geeksforgeeks.org/test-coverage-vs-code-coverage/)

**测试覆盖率和代码覆盖率**是评估代码可行性的最主流的哲学。尽管事实上这些术语有时是相互使用的，因为它们的基本标准是相同的。无论如何，它们并不像你可能怀疑的那样具有可比性。通常，我看到测试组和推进组对这两个短语的使用感到困惑。这就是为什么我想编造一篇文章来详细讨论代码覆盖率和测试覆盖率之间的对比。

**代码覆盖率与测试覆盖率:它们有什么不同？**

*   **代码覆盖率:**
    显示了通过使用 Selenium 或其他测试机械化结构的手动测试和计算机化测试，由测试用例保护的代码级别。例如，如果你的源代码有一个简单的 if… else 循环，那么如果你的测试代码覆盖了这两种情况，那么代码覆盖率将是 100%。
*   **Test coverage :**
    Incorporates testing the highlights actualized as piece of the Functional prerequisites detail, programming necessities particular, and other required archives. For instance, in the event that you are to perform cross program testing of your web application to guarantee whether your application is delivering admirably from various programs or not? Your test coverage would be around the quantity of programs + OS mixes over which you have approved program similarity of your web application.

    理解了代码覆盖率和测试覆盖率之间的本质对比之后，让我们跳到关于代码覆盖率和测试覆盖率的更细微之处。

**深入理解代码覆盖:**
代码覆盖是由设计人员在单元测试期间执行的，以此方式确认代码的使用，以至于几乎所有的代码公告都被执行。很大一部分代码覆盖设备利用静态工具，其中屏蔽执行的语句嵌入在代码的重要区域。尽管插装代码的扩展会导致应用程序大小和执行时间的增加，但是与通过插装代码的执行产生的数据相比，开销是微不足道的。这个产出包括一份报告，它揭示了测试套件的测试覆盖率。

**为什么要执行代码覆盖？**
因为单元测试是由设计者编写的，所以他/她对应该作为单元测试的一部分的测试有更好的感知能力。单元测试改善了产品的一般性质，但是对于包含单元测试的测试数量会有持续的询问。测试套件中有足够数量的测试场景吗？对我们来说，包括更多的测试是个好主意吗？代码覆盖率是对每一个查询的响应。

随着项目的进展，新的亮点，正如修复(测试过程中产生的错误)被添加到放电周期。这意味着测试代码可能同样需要更改，以便在升级过程中随着产品更改保持更新。重要的是，在风险开始时设定的测试原则要与最终的放电周期保持一致。代码覆盖率可以用来确保您的测试满足这些准则，并且最佳质量的代码进入创建阶段。

**仪器种类:**

有三种重要的仪器:

1.  **代码插装–**
    这里源代码是插装语句扩展后组装的。聚会应该利用普通的工具链来完成，富有成效的安排带来了仪表化聚会的时代。例如，为了检查在代码中执行特定函数所花费的时间，可以在函数的开始和结束中包含插装语句。
2.  **运行时检测–**
    与代码检测方法相反，这里的数据是从运行时条件收集的，例如在代码执行的时候。
3.  **Halfway code instrumentation –**
    In this sort of instrumentation, instrumented class is produced by expansion of byte codes to arranged class documents.

    根据您的测试需要，您应该选择正确的代码覆盖设备和由 te 设备支持的最佳测试方法。

**代码覆盖设备:**
有各种代码覆盖设备支持独特的编程方言，其中相当多的设备也作为质量保证设备而存在。大量设备可以与制造仪器和任务执行装置结合，这使得它们显著地更令人印象深刻和更有价值。在挑选开源代码覆盖设备时，您应该检查设备支持的亮点以及仪器是否有功能改进。鉴于这些变量，下面是部分众所周知的开源代码覆盖工具。

1.  **coverage . py–**
    是 Python 的代码覆盖器。顾名思义，它会分解您的源代码，并区分执行的代码级别。它是用 Python 创建的。
2.  **Serenity BDD –**
    Supporting Java and Groovy programming dialects, Serenity BDD is well known open-source library that is fundamentally utilized for composing superb quality acknowledgment tests quicker. You can utilize stories and sagas for tests and code coverage is processed for these accounts and legends. Because of this, test reports that are produced are more illustrative and account in nature. You can plan those mechanized tests back in your prerequisites.

    它倾向于与 JUnit、黄瓜和 Jbehavior 一起使用。宁静 BDD 可以与 Maven、Cradle、JIRA 和 Ant 进行有效的协调。如果您正在利用硒网络驱动程序或硒网格结构进行自动化测试，请选择宁静。

3.  **JaCoCo–**
    JaCoCo 是 Java 的代码覆盖工具。尽管有不同的选择，如 Cobertura 和 EMMA，但这些仪器受到了指责，因为很长一段时间没有更新。JaCoCo 设备是 Eclipse 基金会的一部分，它取代了 Eclipse 中的 EMMA 代码覆盖设备。除了 JaCoCo 的动态推进，另一个使用它的首选位置是与 CI/CD 和任务一致的加入。
4.  **JCov–**
    JCov 是测试系统理性主义的代码覆盖工具。它往往很容易与甲骨文的测试基础——JavaTest 和 JTReg 相协调。尽管事实上，这不是动态的事件，支持飞行。
5.  **PITest–**
    PITest 是一个非常著名的代码覆盖设备，用于 Java 和 JVM 的转换测试。它通过改变您的测试代码来执行变更测试的责任，并且单元测试目前在这个调整后的代码上执行。如果在 PITest 包含额外的代码后，发现使用该代码的错误，单元测试就是白痴证明；否则它需要改变，因为问题是不熟悉的。PITest 很难使用，速度很快，而且处于动态变化之中。