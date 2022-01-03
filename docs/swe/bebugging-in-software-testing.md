# 软件测试中的改进

> 原文:[https://www . geeksforgeeks . org/bebugging-in-software-testing/](https://www.geeksforgeeks.org/bebugging-in-software-testing/)

先决条件–[软件中的缺陷或 Bug](https://www.geeksforgeeks.org/software-engineering-differences-between-defect-bug-and-failure/)和 [Bug 生命周期](https://www.geeksforgeeks.org/bug-life-cycle-in-software-development/)

说到软件开发，那么[软件测试](https://www.geeksforgeeks.org/software-testing-basics/)会自动加入到这个过程中。因为每个软件开发都遵循[软件开发生命周期](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/)，其中软件测试是一个重要阶段。执行[不同类型的软件测试](https://www.geeksforgeeks.org/types-software-testing/)是为了开发高质量的软件产品并将其交付给客户。

通过不同类型的测试，软件测试团队验证不同类型的质量参数，如质量、有效性、可靠性、需求、安全性等。有不同类型的技术来执行不同类型的测试，其中 Bebugging 是软件测试团队为确保其性能和质量而实施的重要且有用的技术之一。

通常在测试阶段，测试团队识别软件产品中存在的缺陷/错误，然后开发团队通过遵循缺陷生命周期来修复识别出的错误。正如我们所知[调试](https://www.geeksforgeeks.org/software-engineering-debugging/)是软件开发中的一般过程，就像调试一样，我们识别、分析和消除错误。但是开始和调试是不同的过程。因此，在调试和调试之间不应该有任何混淆。所以，让我们从深入了解 Bebugging 开始。

**Bebugging :**
Bebugging 也写为 Bebugging，是指在软件应用程序中故意添加一些已知的 bug，以监控其检测和整改的速度的过程。它也被称为缺陷播种或错误猜测或错误注入或缺陷反馈，因为测试团队故意将缺陷/bug 添加到中，作为软件测试方法的一部分，只是为了提高被测软件的质量和功能，目的是开发出高质量的产品。

随机错误被注入到程序源代码中，然后由测试团队对其进行测试，并识别缺陷。那么未被识别的已知 bug 的百分比是软件应用程序中仍然存在的真正 bug，这些 bug 尚未被相关的测试人员检测到。本文介绍了未来可能出现的缺陷、缺陷及其对应用的影响，并介绍了需要解决的新缺陷。

所以让我们知道**Bebugging 的主要目的:**

*   它提高了产品的质量。
*   它用于确定测试集的可靠性。
*   它允许监控缺陷检测和去除的速率。
*   它有助于熟悉已知的 bug。
*   它有助于发现未被发现的错误。

**强化技术:**

1.  **运行时注入–**
    这是一种使用软件触发器将缺陷动态注入正在运行的软件系统的技术。基于时间的触发器、基于中断的触发器、网络级故障注入和系统调用插入技术等。是执行运行时注入的方式数。
2.  **编译注入–**
    它是一种注入技术，在系统的源代码中注入模拟故障，帮助团队确定系统中遗留的各种故障和系统中识别的新故障。

**一些升级工具:**

*   Xception
*   暴风雨
*   详尽无遗
*   超越安全
*   hola deck . hola deck . hola deck . hola deck
*   FIK
*   三维荧光光谱

**变身先决条件:**

*   以前缺陷的记录
*   应用程序的风险报告
*   测试活动经验丰富的团队
*   检查清单