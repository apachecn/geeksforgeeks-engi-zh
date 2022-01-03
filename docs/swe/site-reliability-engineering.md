# 现场可靠性工程

> 原文:[https://www.geeksforgeeks.org/site-reliability-engineering/](https://www.geeksforgeeks.org/site-reliability-engineering/)

**Site Reliability Engineering，**这是科技巨头现在正在实践的一种做法，在这种做法中，一个组织的运营问题被视为软件工程问题，换句话说，就是一个开发人员被指派解决运营问题。基本上，sre 是软件工程师，他们构建各种软件来制造更好的可靠系统。出现的问题是，这不是 DevOps 吗？或者 SRE vs [DevOps](https://www.geeksforgeeks.org/lifecycle-of-devops/) 哪个更好？

**历史:**
这个术语最早是由**本·特雷诺**在 2003 年创造的，他是谷歌的一名软件工程师，这一实践比 DevOps 运动要早得多。在他们的场所实施 SRE 之后不久，treynor 的团队很快推出了 SRE 电子书，让业界了解这种做法。

**现场可靠性工程师的职责:**

*   sre 对生产中运行的系统负责并承担待命职责。
*   SREs 负责开发提高系统可靠性的软件。
*   他们负责对失败的系统进行事故后审查。

**SRE vs 德沃普斯:哪个更好？**
有一个很好的类比来更好地理解这两个术语。那么，接下来，让我们把 DevOps 看作是一个**接口**即类似于包含没有定义的方法的抽象类，把 SRE 看作是一个实现 DevOps 的**具体类**。

```
Interface DevOps{
Reduce Organizational silos();
Accepting failures();
Implement gradual changes();
Leverage Automation();
Measure Everything();
}

```

现在，SRE 作为一个具体的类将实现 DevOps，同时将所有方法定义为:

*   **通过使用同一套工具，在软件工程师、产品团队和 SREs 之间共享所有权，减少组织孤岛。**
*   **接受故障，**由于没有一个系统是 100%可靠的，所以会有故障，sre 对系统进行无可指责的事后分析，并为其生成元数据。
*   **实施小变更，**变更越小，识别问题越容易，修复变更或回滚越快。从而降低故障成本。
*   **利用自动化，**尽可能在生产系统上自动化手动任务，如用户创建、安装软件包、警报或日志记录等。
*   **Measuring Everything,** at the end monitoring the right things that has implemented, as on the end of the day you should have numbers or clear metrics that supports success.

    因此，SRE 和德沃普斯不是竞争标准，而是携手并进。所以，是 **SRE 跟 DevOps** 。