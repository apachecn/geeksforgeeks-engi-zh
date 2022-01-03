# 软件测试中的配对测试

> 原文:[https://www . geesforgeks . org/pair-testing-in-software-testing/](https://www.geeksforgeeks.org/pair-testing-in-software-testing/)

前提条件:[软件测试](https://www.geeksforgeeks.org/software-testing-basics/)

**配对测试:**

结对测试是由在机器后面操作的两个团队成员在软件中进行的验证。第一个成员控制鼠标和键盘，第二个成员做笔记，讨论测试场景和准备/提问。其中一个必须是测试人员，下一个必须是开发人员或业务分析师。

[结对编程](https://www.geeksforgeeks.org/pair-programming/#:~:text=Pair%20programming%20is%20a%20development,may%20switch%20their%20role%20frequently.)是极限编程中常见的做法。因此，结对编程被认为是一种很好的软件编程方法。像明智对测试是一个类似的软件测试过程。

**使用结对测试的优势:**

1.  Developers look at software from different or positive perspectives. They discuss and find out what will happen if I execute it, or what will happen if the business analyst doesn't execute it.
2.  When paired tests are performed with business analysts, they exchange ideas and knowledge between them like analysts and testers.
3.  When a new project is started by a new team member, there are often obstacles between testers and developers.
4.  If we find any problems and want to register them in the bug registration system, these problems will be automatically corrected, so walking in groups of two will help to sharpen each other.

**使用配对测试的缺点:**

当你不知道配对测试设置的准确条件时，你应该或不应该使用它。

1.  All mandatory tests should be automatic, and PT's solution is discovery rather than test cases. We can't use the results of PT session immediately after test automation.
2.  When there are team members, two team members may end each other's classification. That's why we shouldn't use PT when team members don't communicate or cooperate well.
3.  If you plan to implement a structured test case, it cannot add more values or zero values to execute the test case together. This task should be completed by a team member alone.

**结对测试设置:**

1.  Team members should reserve together. When we try to force cooperation, it doesn't work, so we need to create a workable atmosphere.
2.  There should be a separate room or table where team members can perform without interruption. In order to work better, they should also turn off their cell phones and notifications.
3.  The workplace consists of two people who sit behind a table. You can't force people without space.

**准备结对测试会话:**

1.  We should create an ET charter.
2.  We should make clear the concentration and outline of the exam.
3.  We should specify the purpose or goal of the exam.
4.  We should set a time limit for testing. Usually a class is 90 minutes.
5.  We should plan the meeting in a proper way.

**配对测试会话的执行:**

*   During the conversation, team members should discuss the part of the test and the depth of the test. The test should have objectives, emphases and test parts, as described in ET charter.
*   The first group members (drivers) control the keyboard and mouse, while the second group members analyze, ask questions and prepare notes.

**结对测试(PT)整理:**

PT 会话完成后，发现的问题将提交给错误注册系统。如果需要而没有完成。将升级 ET 章程，在发现问题的地方测试 aim 测试，并检查其他备注。东帝汶过渡当局宪章的范围是对过渡时期的短暂和计算，什么进展顺利，什么需要改进。

**最后**，它是团队工作和测试的融合，但是它有很多优点，比如分享关于测试和 SUT 的知识，培训新成员，在成员之间制造障碍等等，这很有趣。我们应该明智地使用配对测试。