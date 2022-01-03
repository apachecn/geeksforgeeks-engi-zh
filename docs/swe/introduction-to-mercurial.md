# 水星

简介

> 原文:[https://www.geeksforgeeks.org/introduction-to-mercurial/](https://www.geeksforgeeks.org/introduction-to-mercurial/)

**Mercurial** 是一个流行的分布式版本控制系统，它提供了归档和保存旧版本源代码的方法。Mercurial 于 2005 年作为开源版本控制系统出现，作为闭源 BitKeeper 的替代品，由 Matt Mackall 开发。

与集中式版本控制系统的 SVN 不同，Mercurial 是分布式版本控制系统。也就是说，当您将更改推送到存储库时，它将转到本地机器。正因为如此，这个过程变得非常快，因为您不会一直推送到远程服务器(尽管可以这样设置)。

Mercurial 主要构建在 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中，这使得它可以跨平台兼容。这也是 Mercurial 主要用作命令行工具的原因之一，尽管也有可用的 GUI 工具。Mercurial 一直是 Adium、Mozilla、Netbeans、Vim、blow 等大品牌使用的版本控制系统。除此之外，许多个人开发人员使用 Mercurial 来管理他们的代码。

**水银的特性:**

*   **Distributed architecture :**
    Most of the traditional version control systems like SVN are based on client-server architecture, where a central server holds the updates done to a project. Mercurial is completely distributed, where each developer has a local copy of the complete project. This way, the developer is not dependent on network or server access. Committing the code, branching and merging can be done faster.
*   **Fast :**
    The implementation and data structure of Mercurial are designed in a way that the tool is fast enough to handle multiple commits. Diffs can be generated between revisions or rolled back in much lesser time, usually in seconds. That’s why it has been used in larger and complex projects like OpenJDK or NetBeans.
*   **Platform independent :**
    Mercurial is intended to be platform independent. Hence, a major portion of it is written in [Python](https://www.geeksforgeeks.org/python-programming-language/), and a small chunk in portable [C](https://www.geeksforgeeks.org/c-programming-language/) for performance related reasons. Because of this reason, binary releases for Mercurial are available on all major platforms.
*   **Extensible :**
    Mercurial can be functionally extended using the official plugins that are shipped along with Mercurial or downloading from external sources or writing our own. Extensions are written in [Python](https://www.geeksforgeeks.org/python-programming-language/) and can change the workings of the basic commands, add new commands and access all the core functions of Mercurial.
*   **Easy to use :**
    The command set of Mercurial is so simple that most of the SVN users will find it very easy. The basic interface of Mercurial is easy to learn and use.
*   **开源:**
    Mercurial 是免费提供的，并根据 GNU 通用公共许可证第 2 版或任何更高版本的条款获得许可。