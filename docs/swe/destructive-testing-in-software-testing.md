# 软件测试中的破坏性测试

> 原文:[https://www . geesforgeks . org/破坏性软件测试测试/](https://www.geeksforgeeks.org/destructive-testing-in-software-testing/)

**破坏性测试:**
破坏性测试是[软件测试](https://www.geeksforgeeks.org/software-testing-basics/)的一种类型，与软件测试中的[测试非常相似。在修改过程中，我们会在软件中添加一些已知的错误，并监控错误的检测率。类似地，在破坏性测试中，软件程序中的不同故障点被检测到。在这个测试的帮助下，一个应用程序被故意执行以失败，以便检查应用程序的健壮性以及识别各种故障点。我们知道有不同类型的软件测试方法来验证软件的性能、软件的稳定性、软件的兼容性、软件的安全性等。像这样，通过破坏性测试，我们检查应用程序中不需要的和不可预测的异常用户行为。](https://www.geeksforgeeks.org/bebugging-in-software-testing/)

在破坏性测试(或破坏性物理分析，DPA)中，进行样品失效测试，以了解样品的性能或材料在各种载荷下的行为。与无损检测相比，这些检测通常更容易执行，也更容易解释。破坏性试验最适合大规模生产，也最经济，因为销毁几个样品的成本可以忽略不计。通常，这种测试程序是不经济的，因为只生产一个或很少的项目(例如，在建筑物的情况下)。破坏性故障模式通常使用连续高速摄像机记录(胶片循环)进行分析和记录，直到检测到故障。故障可以通过声音检测器或气压计来检测，它会产生信号来操作高速摄像机。

重要的是，即使你不知道软件产品的原始需求，也可以进行破坏性测试。然而，一些知识可以帮助开发一个好的测试策略。

**破坏性试验的重要性:**

*   帮助识别基于场景的问题。
*   有助于验证软件产品的持久性。
*   有助于轻松检测任何故障点。
*   有助于理解软件产品的健壮性。

**它在这次测试中取得了什么成绩？**

*   程序的适当行为
*   不适当的程序行为
*   使用不当
*   输入数据不正确
*   适当的输出数据

**这些测试是怎么做的？**
破坏性测试包括许多活动，例如设计一组测试脚本、执行测试脚本、引发错误、关闭错误，以及在迭代结束时向涉众提供成功或失败的度量标准。

对于破坏性测试，有许多方法可以测试它。让我们看一些例子–

*   **故障点分析方法–**
    这是系统的详细介绍，用于评估不同点可能出现的错误。对于这个策略，可以从 BA(业务分析师)那里获得帮助。
*   **同行测试人员评审–**
    该测试由同行测试人员执行，以分析测试用例并评审那些不太熟悉系统/功能的人。
*   **测试用例的业务评审–**
    最终用户或专家可能会想到许多有效的场景，测试人员可能不会考虑或错过，因为他们的重点将完全放在测试需求上。
*   **使用运行表进行探索性测试–**
    使用运行表进行探索性测试将有助于确定测试的内容，重复测试，并允许您控制测试覆盖率。

**破坏性试验方法:**
以下是各种破坏性试验方法

*   [α/β测试](https://www.geeksforgeeks.org/difference-between-alpha-and-beta-testing/#:~:text=Alpha%20Testing%20is%20a%20type,users%20or%20to%20the%20public.&text=Beta%20testing%20is%20performed%20by%20clients%20who%20are%20not%20part,end%2Duser%20of%20the%20product.)
*   [界面测试](https://www.geeksforgeeks.org/differences-between-interface-and-integration-testing/#:~:text=Integration%20Testing%20focuses%20on%20verifying%20data%20communication%20among%20these%20modules.&text=Interface%20testing%20is%20carried%20out,testing%20is%20tricky%20and%20boring.)
*   环形试验
*   [系统测试](https://www.geeksforgeeks.org/system-testing/)
*   平均分配
*   [回归测试](https://www.geeksforgeeks.org/software-engineering-regression-testing/)
*   [验收测试](https://www.geeksforgeeks.org/acceptance-testing-software-testing/)等。

**破坏性测试技术:**
以下是经过修改后可以使用的破坏性测试技术:

*   [白盒测试](https://www.geeksforgeeks.org/software-engineering-white-box-testing/)
*   [安全测试](https://www.geeksforgeeks.org/software-testing-security-testing/)
*   缺陷测试
*   [冒烟测试](https://www.geeksforgeeks.org/smoke-testing-software-testing/)等。

最后，在这种技术中，应用程序被有意地执行到程序故障，以验证应用程序的健壮性，即使对软件产品的原始需求一无所知。