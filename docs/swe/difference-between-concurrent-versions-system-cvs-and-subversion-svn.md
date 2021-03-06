# 并发版本系统(CVS)和 Subversion (SVN)的区别

> 原文:[https://www . geeksforgeeks . org/concurrent-version-system-CVS-and-subversion-SVN/](https://www.geeksforgeeks.org/difference-between-concurrent-versions-system-cvs-and-subversion-svn/)

**1。并发版本系统(CVS) :**
并发版本系统是由 Dick Grune 作为一系列 shell 脚本开发的功能性版本控制系统。这有助于团队在开发软件时与存储库中的变更联系起来。这个工具长期以来被用作版本控制系统。这是一个可靠的软件工具，但由于新的挑战，其他替代方法使它的使用受到限制。

以下是 CVS 的一些特性:

*   它是可靠的版本控制系统之一
*   它不允许提交错误。
*   脚本是用 RCS 编写的。
*   用户只能将文件存储到存储库中。

**优势:**

*   CVS 是可靠的版本控制软件之一。
*   变更以完全变更的方式提交。

**缺点:**

*   CVS 更改非常耗时。
*   如果提交中有错误，CVS 不会提交。

**2。Subversion(SVN):**
Subversion 是一个开源的高功能版本控制系统，由 CollabNet Inc .开发，后来被 Apache 软件基金会拿走。该系统由服务器集中控制。该服务器负责存储存储库，通过该服务器，该存储库被分配到三个区域，称为分支、区域和卡车。这使得 SVN 与众不同。

以下是 SVN 的一些特色:

*   它与多种编程语言相结合。
*   当多人访问同一个文件时，该文件被锁定，称为文件锁定。
*   指令和编辑是版本化的。
*   二进制文件要小心处理。

**优势:**

*   SVN 是高度可配置的。
*   仅提交和观察最新更改。

**缺点:**

*   SVN 中央存储库使提交更改非常耗时。
*   第一次学 SVN 很难。

**CVS 和 SVN 的区别:**

<center>

| 参数 | CVS | SVN |
| --- | --- | --- |
| 开发人 | CVS 是由迪克·格鲁恩开发的。 | SVN 是由 CollabNet 公司开发的。 |
| 开放源码 | 它是开源的，并与 GNU 通用公共许可证一起发布。 | 它是开源的，并与 Apache 许可证一起发布。 |
| 存储库格式 | CVS 使用 RFC 格式存储存储库。 | SVN 使用二进制格式存储库 |
| 标签管理 | CVS 有一个维护标签和分支的系统机制。 | SVN 使用分支、区域和主干来管理存储库，并且没有标记功能。 |
| 速度 | 与 SVN 相比，CVS 比较慢。 | SVN 很快，因为所有的文件都备份到电脑上完成。 |
| 文件类型 | CVS 最初要求数据是文本，并要求用户输入数据类型。 | SVN 很聪明，很容易看到变化并发表出来。 |

</center>