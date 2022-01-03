# 如何开发易于维护的信息系统

> 原文:[https://www . geeksforgeeks . org/如何开发易于维护的信息系统/](https://www.geeksforgeeks.org/how-to-develop-information-systems-that-are-easy-to-maintain/)

**简介:**

维护是一项基本要求，需要大约 60%的时间，有时维护会占用不必要的时间，这完全是一种浪费，因为只需稍加规划或测试，就可以避免这种情况。路易斯·罗斯曾经说过:“我坚信一个系统的维护是它最初发展得有多好的直接函数”。

现在，我们将讨论在开发系统时应该牢记的某些因素，以便最大限度地减少维护时间。下面给出的因素如下。

1.  Looking to the future, the system should be well planned.
2.  The user's specifications should be correct.
3.  Modular system is required.
4.  Complete all documents.
5.  In the process of [developing](https://www.geeksforgeeks.org/what-is-full-stack-development/) , we should follow the standards.
6.  [Check](https://www.geeksforgeeks.org/software-testing-basics/) thoroughly.
7.  For the [development cycle](https://www.geeksforgeeks.org/software-engineering-program-development-life-cycle-pdlc/) , enough time should be set aside.
8.  Human factors should be considered, and attention should be paid to end users and ergonomics (health status).
9.  With the relationship between [system design](https://www.geeksforgeeks.org/5-common-system-design-concepts-for-interview-preparation/) and system maintenance, the development team should fully realize.

对于用户来说，维护对于文档来说很重要，到目前为止，我们已经看到了这一点，以及维护对于系统平稳运行的重要性。对于交流来说，文档对于开发团队和所有潜在用户来说都是非常重要和必要的。如果只有在开发团队成员缺席的情况下才需要紧急维护，那么文档证明是非常有用的，因为所有的事实都有一个记录，记录了所有的假设，未来的维护因此变得非常容易。为了方便，无错误的功能维护是必要的系统，也为了跟上不断变化的要求和不断变化的技术。因此，我们正在讨论的文档和其他要素维护是软件开发中不受欢迎但非常重要的方面。

**与** [**编程相关的点**](https://www.geeksforgeeks.org/c/) **方法论:**

*   For a good program, the meaningful name of the identifier should be used.
*   The expression should be simple and clear.
*   To enhance readability, comments and logos should be used.
*   To make the program readable, blank lines and spaces should be inserted.
*   Robustness should be made by programs. Robustness refers to the ability of a program to recover after an error and continue running in its environment.
*   Errors that violate grammar rules and regulations of programming languages are under compile-time errors (grammatical errors and semantic errors).
*   In the process of program execution, there will be run-time errors.
*   There is a logical error due to the wrong analysis of the problem.

**案例研究:**

**调查发现维修问题严重:**

到 1986 年发布[质量保证](https://www.geeksforgeeks.org/software-engineering-software-quality-assurance/)研究所在大型数据中心内的调查结果时，软件维护问题仍有待解决。本次调查的重点在这里，调查了 37 家财富 500 强公司。

*   From two months to 60 months-an average of 23 months-through the maintenance backlog, this is the case in the company under investigation.
*   Maintenance expenditure accounts for 10% to 90% of data processing budget, with an average of 51%.
*   Nearly 80% of the respondents have systems whose logic can only be understood by specific individuals. This makes it impossible for data processing personnel to take on maintenance responsibilities in turn.
*   The formal method of deciding when to rewrite the program exists in less than 15% of the companies surveyed. 16% of companies require that the old system and the newly developed system meet the same programming standards.
*   Except for 5% of the companies surveyed, all companies admit that programmers engaged in new system development are more prestigious than those assigned to the maintenance department.