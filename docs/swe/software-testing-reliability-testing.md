# 软件测试|可靠性测试

> 原文:[https://www . geesforgeks . org/software-testing-reliability-testing/](https://www.geeksforgeeks.org/software-testing-reliability-testing/)

**可靠性测试**是一种测试技术，涉及测试软件的功能和给定环境条件的能力，有助于发现软件设计和功能中的问题。它被定义为一种软件测试类型，用于确定软件是否可以在特定环境中执行特定时间段的无故障操作。它确保产品无故障，并且对于预期目的是可靠的。

**可靠性测试的目标:**
可靠性测试的目标是:

*   寻找重复失败的永久结构。
*   找出发生故障的次数是特定的时间段。
*   发现失败的主要原因。
*   修复缺陷后，对软件产品的各个模块进行性能测试。

**可靠性测试的类型:**
可靠性测试有三种类型:-

1.  **特征测试:**
    本次测试涉及以下三个步骤:

*   软件中的每个功能至少应该执行一次。
*   应该减少两个或更多功能之间的交互。
*   每个功能都应该正确执行。

*   **回归测试:**
    回归测试基本上是在应用程序中添加任何新功能、删除旧功能或修复错误时执行的，以确保引入新功能或修复以前的错误后，应用程序中不会引入新错误。*   **Load Testing:**
    Load testing is carried out to determine whether the application is supporting the required load without getting breakdown. It is performed to check the performance of the software under maximum work load.

    可靠性测试的研究可以分为三类

    1.  系统模型化
    2.  尺寸
    3.  改进

    **可靠性测试的测量:**

    *   **平均故障间隔时间(MTBF):**
        可靠性测试的测量是根据平均故障间隔时间(MTBF)进行的。
    *   **平均故障时间(MTTF):**
        两次连续故障之间的时间称为平均故障时间(MTTF)。
    *   **平均修复时间(MTTR):**
        修复故障所需的时间称为平均修复时间(MTTR)。

        ```
        MTBF = MTTF + MTTR 
        ```