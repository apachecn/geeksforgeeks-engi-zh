# 侦察及其工具

> 原文:[https://www.geeksforgeeks.org/reconnaissance-and-its-tools/](https://www.geeksforgeeks.org/reconnaissance-and-its-tools/)

**侦察**(或简称**侦察**)是**笔测**过程的初始阶段。侦察的目标是尽可能多地收集目标的信息。信息越多，对笔测试的后续阶段越有利。大多数新学员低估了这个阶段，并忽略了它，但侦察是笔测试最重要的阶段。如果你完全理解这个过程，你对数字世界的观点就会改变。学会成功地进行侦察过程对任何人来说都是一项宝贵的技能。侦察有两种策略，即主动侦察和被动侦察。

*   **主动侦察:**
    意思是直接与目标互动收集信息。不建议这样做，因为这违反了笔测试中“隐藏痕迹”的规则。
*   **被动侦察:**
    是指利用互联网上存在的大量信息收集目标信息。在这种情况下，我们不直接与目标互动，因此不用担心目标会记录或记录我们的活动。

**侦察工具:**

1.  **HTTrack–网站复印机:**
    它是一个免费的实用程序，可以下载任何网站的离线副本。离线副本包括所有图片，网页，链接和原始网站的代码。使用这个工具，你不必花太多时间在目标网站上。在任何网站上花费太多时间都可能导致监控工具记录您的活动。
2.  **谷歌指令:**
    谷歌使用指令提供了一种增强的搜索方法。首先写出要使用的指令的名称，然后是冒号(:)，然后是要在指令中使用的术语。您也可以组合两个或多个指令。

    ```
    for e.g- site:geeksforgeeks.org  dhcp snooping  
    filetype:pdf “some text”  
    site:geeksforgeeks.org filetype:png “your text”
    ```

3.  **The Harvester :**
    It is a python script written by Christian Martorella. This tool is used to make systematic list of e-mail and sub-domains related to target.

    请注意，这些工具已经存在于 Kali-Linux 操作系统中。为了方便和容易地实践这些工具，建议使用 Kali Linux。