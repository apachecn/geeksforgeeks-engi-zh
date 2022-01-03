# 软件工程中的阴性测试

> 原文:[https://www . geesforgeks . org/阴性-软件工程测试/](https://www.geeksforgeeks.org/negative-testing-in-software-engineering/)

每个软件开发过程都遵循[软件开发生命周期(SDLC)](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/) 最终开发出高质量的软件产品。其中[软件测试](https://www.geeksforgeeks.org/software-testing-basics/)是重要阶段之一，因为它只保证产品的质量。因此，[执行不同类型的软件测试](https://www.geeksforgeeks.org/types-software-testing/)来检查不同的参数或测试用例。

在这篇文章中，我们将讨论阴性测试，并了解它，比如这个测试实际上是什么，它是如何执行的，为什么执行它，以及最后执行这个测试的优缺点。所以，让我们开始探索这个话题。

**阴性测试:**
进行阴性测试是为了确保每当用户向软件应用程序提供任何无意或意外的输入时，软件应用程序或产品不会出现故障或行为异常。意思是做阴性测试的主要格言是检查当一些意想不到的输入被给予软件时软件的行为。当执行此测试以中断系统并验证应用程序在不需要的输入期间的响应时。

**阴性测试用例:**
阴性测试的某些组成部分称为阴性测试用例。团队创建它来测试应用程序。该团队使用以下测试方法:

*   **数据绑定测试–**
    这里团队测试所有数据字段的上下限。
*   **字段大小测试–**
    它防止用户在获得超过限制的错误消息之前面对更多的字符。
*   **必要数据测试–**
    该测试确保在输入关键数据之前，屏幕上的每个数据都经过验证。
*   **数值界限测试–**
    该测试确保阴性测试的测试用例在团队同时分析下限和上限的情况下是准确的。
*   **植入报价–**
    当最终用户使用单引号存储信息时，软件系统会面临一些问题。所以对于所有的屏幕，团队应该提供不止一个单引号。
*   **性能方面的修改–**
    该测试包含测试用例，这些测试用例比较了以前和当前版本的性能统计数据，有助于识别潜在的性能问题。
*   **Web 会话测试–**
    这里的测试构建测试用例，只在应用程序中发布网页，不涉及用户登录。

**如何进行阴性检测？**

*   最初，考虑可能对应用程序产生负面影响的可能情况是很重要的。
*   在探索场景时，我们需要优先考虑一些测试参数，以确保不会浪费时间或金钱。
*   现在我们构建一个测试用例，其中包括测试应用程序可能崩溃的数据输入。这正是我们不希望在客户使用产品时发生的事情。
*   在形成测试用例的优先级时，应该消除安全隐患。
*   想想可能进入我们程序的不需要的和意想不到的数据是很有帮助的，这些数据包括一些简单的错误，让用户感到沮丧。

**阴性检测的好处:**
阴性检测的一些显著好处是:

1.  它在上线前给客户带来更多的好处。
2.  它涵盖了所有的基础，并通过涵盖每种类型的错误来提高可能性。
3.  阴性测试的实施确保了产品质量良好，没有漏洞或漏洞可以忽略。
4.  为了确保覆盖所有的测试用例，在阳性测试之前要进行一轮阴性测试。

**阴性测试的真实示例:**
我们假设应用程序的登录屏幕中有两个框，一个是“用户名”，另一个是“密码”，要求如下才有效:

*   用户名不能为空，只能有个字符。
*   用户名最多可以包含 10 个字符。
*   密码只能包含字母数字值的组合，并且不允许使用其他类型的字符。
*   密码最多必须包含 10 个字符。
*   一些积极的测试场景包括:
*   Username: Satyabrata 密码:qwerty123
*   验证用户是否使用有效凭据登录
*   一些阴性测试场景可能包括:
*   用户名:9876=)密码:/*-+
*   然后验证用户名和密码。输入此类内容的目的是检查应用程序如何响应意外输入，从而确保质量保证。

**阴性测试的缺点:**
对于应用的增强，阴性测试是有帮助的，但是有一定的缺点:

1.  执行它需要投入时间、金钱和精力。
2.  客户不得不极度拖延，因为他们必须等到产品发布。
3.  在某些情况下，不需要进行过多的阴性测试。
4.  必须有一名训练有素的专业工程师来实施阴性测试。

**最后**，阴性测试确保交付给客户的产品或应用没有 bug。为了构建有效的阴性测试场景，我们需要富有创造力和智慧的测试工程师。每个软件公司的目标是能够进行阴性测试。因此，通过实现负测试，我们可以提高软件的质量。