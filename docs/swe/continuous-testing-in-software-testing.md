# 软件测试中的持续测试

> 原文:[https://www . geesforgeks . org/continuous-testing-in-software-testing/](https://www.geeksforgeeks.org/continuous-testing-in-software-testing/)

**先决条件:** [软件测试](https://www.geeksforgeeks.org/software-testing-basics/)

在本文中，我们将讨论什么是连续测试，如何执行，为什么执行，以及最终我们通过实现这种测试获得的好处。所以，让我们深入文章了解更多。

**软件开发中的测试:**

软件测试是软件开发生命周期的一部分。SDLC 只不过是从收集需求到部署软件的软件开发的端到端过程(阶段)。

无论什么时候开发软件，都要经过测试阶段，以确保软件的质量，并确定要由开发人员修复的缺陷。

传统上，测试是在软件开发完成后进行的。软件的开发分为许多部分。一旦一个团队完成了软件的一个部分的开发，那么这个部分就被交给另一个团队，一旦他们完成了他们的部分，这个团队就把软件交给另一个团队。这种情况一直持续到软件完全开发出来。这种开发软件的方法被称为瀑布模型。

[瀑布模型](https://www.geeksforgeeks.org/software-engineering-classical-waterfall-model/)需要更多的时间来执行开发的各个部分，但是它保证了最好的结果，因为有时间进行开发，并且有几个团队专注于开发的特定部分。

随着对更快开发和向客户交付软件的需求增加，组织采用了敏捷软件开发模式。增量活动在该模型中持续执行。

如今，DevOps 被使用协作过程的软件开发组织所采用，责任由团队分担。DevOps 是软件开发的另一种方法论，就像瀑布和敏捷一样。比前几个好。

软件开发模型的这种演变导致组织使用自动化、[持续集成(CI)和持续交付(CD)](https://www.geeksforgeeks.org/ci-cd-continuous-integration-and-continuous-delivery/) ，它们需要持续测试(CT)。

**连续测试(CT) :**

持续测试是一个自动化测试的过程，一旦开发人员交付了一段代码，就持续对软件进行测试。这种测试在从开发的初始阶段直到软件部署的每个阶段都要进行。

**为什么组织要进行持续测试？**

*   Every time a new feature is added to the software, it takes a lot of time and manpower to test the software.
*   But organizations want more efficient and simpler solutions. This is why organizations adopt a new method of "continuous testing", which can provide faster and seamless software development and release high-quality software in a short time.
*   Through continuous testing, once the code is integrated into the previous set of code, it will be automatically tested.

**持续测试是如何工作的？**

*   Automated testing from the early stage of release.
*   Experience.
*   Tested everywhere again. That is, in different environments and devices.

**自动化在连续测试中的作用:**

是的。想象一下，一旦开发人员发布了一组要手动测试的代码，就要频繁地进行所有的测试。这几乎是不可能的，如果有可能的话，那么它的成本肯定会比花在自动化上的成本高得多。

持续测试之所以成为可能，只是因为测试自动化，这对于 CI 和 CD 来说是必不可少的。测试自动化是一种有助于测试代码性能和功能的工具。所以持续的测试和自动化无疑是一个高效和有效的组合。

**实施持续测试的好处:**

1.  Publish and deliver software more frequently.
2.  By testing in the early stage of development, the risk is potentially reduced.
3.  By identifying bugs at the initial stage, the cost can be reduced, which can save the time and cost of future changes.
4.  Due to frequent inspection, the product quality is higher.
5.  Easy to achieve.