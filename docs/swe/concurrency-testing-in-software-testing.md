# 软件测试中的并发测试

> 原文:[https://www . geesforgeks . org/concurrency-testing-in-software-testing/](https://www.geeksforgeeks.org/concurrency-testing-in-software-testing/)

**先决条件:** [软件测试](https://www.geeksforgeeks.org/software-testing-basics/)

目前一切都可以用软件来完成。在这个数字时代，每个人都有自己的数字设备，他们可以根据自己的需求随时随地访问软件。所以开发团队也要开发出一款能够为客户提供更好服务的优质软件。众所周知，软件开发遵循一个[软件开发生命周期(SDLC)](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/) 来开发任何软件应用程序。其中软件测试是开发周期的重要部分。由于一个软件应用程序被许多人同时用于多个设备，因此需要检查其兼容性和稳定性。不仅如此，还需要检查它是否同时工作。但是开发一个好的并发软件总是一个具有挑战性的活动。考虑到并发软件测试的重要性，在这一领域已经进行了许多研究，特别是涉及应用于串行程序的技术和标准的调整。在本文中，我们将讨论更多关于并发测试的内容。

**并发测试:**

并发测试主要用于在您的网站上有多个用户活动时检查网站的性能。这就是为什么它也被称为多用户测试。同步测试就像是准备网站流量的一个步骤，这样当有多个用户时就不会卡住。换句话说，我们可以说在多个用户同时采取相同行动的情况下监控效果。

**例如:–**现在几乎每个人都用 Flipkart 来订购产品。因此，请考虑这样一种情况:许多用户同时登录了他们的 Flipkart 帐户，同时多个用户订购同一产品，因此测试软件在这种情况下的行为是并发测试的一个例子。

正如我们所知[兼容性测试](https://www.geeksforgeeks.org/compatibility-testing-in-software-engineering/#:~:text=Compatibility%20testing%20is%20software%20testing,when%20the%20application%20becomes%20stable.)有助于提高并发程序的可靠性和持久性。同步程序同时运行多个程序并共享信息。其中同步测试确保了同步程序的可靠性。

**并发测试流程:**

*   Create a concurrent test plan.
*   Analysis and scope definition.
*   Create high-level and low-level scenarios for concurrent testing.
*   Prepare different platforms for testing.
*   Create a test environment.
*   Now, two or more testers can start testing by performing the same tasks at the same time.

**并发测试技术:**

1.  **Code review:** In this process, the embedded code and its structure are verified. This is a time-consuming process.
2.  **Static analysis:** Static analysis is to check and evaluate the coding system before the code is executed. It is very useful for finding errors and errors in the system.
3.  **fuzz test:** In this test, the user feeds incorrect random data and then waits to see how the program responds. There is no logic behind fuzzy test, it is not just a guess, because the bad data provided will cause the program to crash.
4.  **contest:** Contest eliminates synchronization errors in multithreaded Java applets. The competition also pointed out the shortcomings in unit testing.
5.  **Accessibility test:** Generally, accessibility test is impossible for many applications because it requires a large number of sub-tests.
6.  **Random test:** Increase the coverage area through random test input. Multi-strand simultaneous test. For better results, test 5-10 strands at a time.
7.  **Concurrent test extension:** This can be used to test multi-threaded or concurrent software. Using permutation algorithm, this type of test is easy to expand and consume. Without extension, combinatorial testing is effective for serial program testing.

**并发测试中的一些挑战:**

*   Create test cases for concurrent tests.
*   Get new bugs in concurrent tests.
*   It needs to be tested on different platforms.
*   Correct concurrent program errors.
*   Time-related defects are difficult to detect.

**优势:**

1.  Problems such as data corruption and deadlock are easy to identify.
2.  So that it is easy to encapsulate the behavior of a certain part of the inspection program.
3.  The reliability and durability of the software are increased.

**缺点:**

1.  Multi-platform testing is required.
2.  Require more extensive testing.
3.  Reproducing defects is an arduous task.
4.  The failure rate of synchronous program is higher than that of sequential program.
5.  Correct concurrent software.