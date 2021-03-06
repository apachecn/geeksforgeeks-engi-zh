# 渗透测试和逆向工程

> 原文:[https://www . geesforgeks . org/渗透测试和逆向工程/](https://www.geeksforgeeks.org/penetration-testing-and-reverse-engineering/)

什么是渗透测试？
**【渗透】[测试](https://www.geeksforgeeks.org/software-testing-basics/)** 一年来一直在进化，高度复杂的攻击大幅增加。每个组织现在都意识到网络攻击造成的损害。私营和政府组织现在每三个月或更短时间进行一次定期渗透测试。攻击每天都在增加，现在几乎每个设备都容易受到未修补的零日漏洞的攻击。像熔毁和幽灵这样的攻击已经深入到利用处理器级别的漏洞。像其他方式一样，固件也是重要的攻击媒介之一。本文讨论了路由器固件逆向工程的多种方法和逆向工程的过程。

什么是固件？
**固件**通过软件控制一个硬件。固件预装在路由器、智能手机、计算机和其他物联网设备中。固件是硬件专用的。它们不仅不同于其他制造商的设备，而且也不同于同一制造商的设备。固件通常在高度复杂的设备中充当操作环境。另一方面，在不太复杂的设备中，它们充当操作系统，负责完整的硬件控制。固件保存在只读存储器中；非易失性存储器。在大多数路由器中，固件文件系统基于 Linux 操作系统。固件可以替换，但用户不能删除

什么是逆向工程？
[逆向工程](https://www.geeksforgeeks.org/software-engineering-reverse-engineering/)是对一个产品进行反编译的过程，以暴露其内部架构，并学习它是如何构建的。路由器固件大多是二进制格式，因为它们是硬件专用的，无法读取。

因此，它们被逆向工程以解压缩其中存在的文件系统。解压缩文件系统后，文件系统中的文件可见。然后，安全研究人员分析该文件，以发现代码中的安全缺陷。或者可以操纵文件系统中的文件，并在文件系统中添加后门程序，使攻击者能够控制路由器以及网络和连接到网络的其他设备。逆向工程使研究人员能够理解文件系统、代码流和固件的功能。

有多种方法可用于反向工程路由器固件。最近，美国国家安全局发布了其逆向工程工具——Ghidra。Linux 有几个内置的实用程序，允许用户解压缩固件文件系统，而无需使用任何第三方工具。

**逆向工程工具:**

*   **Binwalk–**是一个内置的 Linux 实用程序，允许我们雕刻和分析二进制文件。
*   **Unsquashfs–**是一个解压缩或提取 squashfs 文件系统的工具。
*   **hex dump–**允许用户查看特定输入数据的十六进制视图，能够将文件内容提取为多种格式，如十进制、八进制和 ASCII。
*   **Objdump–**显示关于目标文件的信息，并用于反汇编可执行文件。
*   **字符串–**提取嵌入在二进制文件和其他可执行文件中的字符串
*   **GDB–**GNU 调试器帮助反编译用嵌入式 C、C++等编写的可执行文件和二进制文件。
*   **radar E2–**是为逆向工程和分析二进制文件而构建的框架。
*   **Ghidra–**由一套逆向工程工具和 NSA 许可的开源软件组成。
*   **IDA–**是商业软件，允许从可执行文件中调试和反编译源代码。
*   **固件 mod 套件–**允许对嵌入式设备中的各种固件进行解压缩。它支持各种文件系统和版本，如 SquashFS 2.0、3.0 和 4.0。