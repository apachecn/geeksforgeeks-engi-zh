# 软件公差

> 原文:[https://www.geeksforgeeks.org/software-tolerance/](https://www.geeksforgeeks.org/software-tolerance/)

在本文中，我们将从一般的容错开始，讨论软件容错的优缺点。所以，让我们深入了解一下这篇文章，以便更好地理解这个概念。

**容错:**
容错是一个术语，解释了软件即使在其组件出现故障后也能继续执行其系统操作。软件容错是指软件检测和恢复运行软件的系统中的软件或硬件中正在发生或已经发生的故障的能力，以便根据参数提供帮助。软件容错是构建从嵌入式系统到数据仓库系统的下一代高可用、高可靠计算系统的必要设备。软件容错不仅仅是一个解决方案，然而，它已经成为未来一代系统开发过程中需要包含的一个重要组件。

软件故障大多发生在软件开发过程中。软件制造，软件的复制，被认为是精确的。基于容错特性设计的系统在满足需求方面问题较少。

[软件容错技术](https://www.geeksforgeeks.org/fault-tolerance-techniques-in-computer-system/):

*   硬件容错技术
*   软件容错技术

**软件故障:**
设计故障发生在设计人员，要么曲解了客户给出的要求，要么只是犯了一个错误。软件故障之所以频繁，通常是因为现代系统中的复杂性经常被还原为系统的软件部分。据观察，目前 70-85%的计算机故障来自软件错误。软件故障也可能来自硬件；这些故障本质上通常是短暂的，可以通过结合现有的软件和硬件[容错技术来包含。](https://www.geeksforgeeks.org/basic-fault-tolerant-software-techniques/)

**如何应用容错:**
容错系统由许多组件组成，当系统发生故障时，这些组件用作备份。其中包括:

1.  **物理系统–**
    它由相同或等效的系统支持。例如，服务器可以通过使用并行运行的相同配置服务器来利用容错属性，所有操作都模仿备份服务器。
2.  **虚拟系统–**
    被其他软件实例保留。例如，包含客户信息的数据库可以连续存储在另一台机器上。如果当前数据库出现故障，则操作可以自动重定向到存储的数据库。

**什么是容错架构？**
有一种不同的方法可以创建容错服务器平台，从而防止数据丢失并避免计划外停机。计算机体系结构中的容错简单地描述了管理员和工程师做出什么决定，以便系统即使在故障的情况下也能保持运行。

可以考虑开发不同的容错工具。在驱动器控制器级别，廉价磁盘冗余阵列(RAID)是一种常见的容错策略，可以在开发时实施。有各种设施级容错形式，包括冷、热、暖和复制站点。容错计算在灾难恢复和中断期间发挥着巨大的作用。为此，容错策略还包括一些不间断电源(UPS)，如发电机，即使在电网发生故障后，它也能独立运行。拜占庭容错(BFT)是未来容错架构的另一个问题。BFT 系统对于区块链、核电和航天工业是必要的，因为即使系统中的某些节点出现故障或受到恶意行为者的驱动，这些系统也能防止停机。

**容错优势:**

*   这是一种系统，旨在提供同一系统的多个副本，并在系统出现故障时切换到另一个可用副本。
*   如果其中一个系统出现故障，同一系统的存储副本可用于在新环境中测试系统的其他功能，而不会干扰核心系统。
*   使用这种策略，即使系统的单个部分出现故障，整个系统也会继续工作。
*   不同级别的容错应用程序可以保护系统免受恶意攻击和黑客攻击。
*   冗余当主系统出现故障时，可以自动将同一系统的同一副本复制到不同的位置。

**容错的缺点:**

*   在某些情况下，如果在开发过程中出现故障，那么在备份系统中工作会导致不同的错误。
*   为了防止数据在故障期间丢失，我们不得不单独购买组件以备不时之需，这导致购买不同组件的成本增加。
*   容错设计使用不同的不太安全的组件，这可能会导致不同的安全问题。