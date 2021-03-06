# SAST 和 DAST 的区别

> 原文:[https://www . geesforgeks . org/sast 和-dast 之间的区别/](https://www.geeksforgeeks.org/difference-between-sast-and-dast/)

**1。静态应用安全测试(SAST) :**
这是一种白盒测试方法，意味着它们需要访问源代码才能运行。它通过在部署前检查代码来发现所有安全漏洞，包括软件缺陷和弱点，如 SQL 注入和其他漏洞。SAST 不需要运行系统来执行评估。

静态应用安全测试(SAST)是一种高度可扩展的安全测试方法。它也可以自动化，这将有助于节省时间和金钱。SAST 测试是在[软件开发生命周期(SDLC)](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/) 早期进行的，所以很容易更早发现潜在的安全漏洞。

**2。动态应用程序安全测试(DAST) :**
这是一种黑盒测试方法，这意味着测试是从运行中的应用程序外部执行的，而不是查看内部源代码或应用程序架构。它正在运行，通过检查应用程序来发现广泛的漏洞。DAST 需要一个运行系统来进行评估。

通过动态应用程序安全测试(DAST)，可以确定与软件应用程序的操作部署相关的不同安全漏洞。在 DAST，测试人员执行类似于攻击者的操作，以便帮助发现其他测试技术可能遗漏的不同安全漏洞。

**静态应用安全测试(SAST)和动态应用安全测试(DAST)的区别:**

<figure class="table">

| 序列号
 | 静态应用安全测试
 | 动态应用安全测试
 |
| 1. | SAST 是白盒安全测试的一种。 | DAST 是黑盒安全测试的类型。 |
| 2. | 在 SAST，应用程序是由内向外测试的。 | 在 DAST，应用程序是从外部测试的。 |
| 3. | 这种类型测试是开发人员的测试方法。 | 这种类型的测试是黑客的测试方法。 |
| 4. | 静态应用程序安全测试不需要部署应用程序。 | 动态应用程序安全性测试需要一个正在运行的应用程序。 |
| 5. | 在 SAST，发现漏洞、识别和修复漏洞更容易。 | 在软件开发生命周期接近尾声时发现漏洞。 |
| 6. | 只需要很少的成本援助就可以修复漏洞。 | 它在软件开发生命周期接近尾声时发现漏洞，因此这样做成本很高。 |
| 7. | SAST 无法发现与运行时和环境相关的问题。 | DAST 可以发现与运行时和环境相关的问题。 |
| 8. | 通常它支持所有类型的软件，如 web 应用程序、web 服务、胖客户端。 | 通常它只扫描网络应用程序、网络服务等应用程序，而不扫描其他类型的软件。 |
| 9. | 在这个测试中，开发人员拥有关于设计、应用程序框架和实现的知识。 | 在这个测试中，测试人员不了解应用程序、设计、框架和应用程序的实现。 |
| 10. | SAST 测试需要源代码来执行测试操作。 | DAST 测试不需要源代码来执行测试操作。 |
| 11. | 当它扫描静态代码并执行测试操作时，这就是为什么它被称为静态应用程序安全测试(SAST)。 | 当它扫描动态代码并执行测试操作时，这就是为什么它被称为动态应用程序安全测试(DAST)。 |
| 12. | 该测试在软件开发生命周期的早期阶段进行。 | 该测试在软件开发生命周期结束时进行。 |
| 13. | 在 SAST，依赖于测试人员的经验，存在昂贵的长持续时间。 | 在 DAST，测试人员无法进行全面的应用分析，因为这是由我们的外部人员进行的。 |
| 14. | 在 SAST，测试人员能够进行全面的应用分析。 | 由于范围有限，与其他类型的测试相比，DAST 可以做得更快。 |

</figure>