# 尺寸导向指标的简短说明

> 原文:[https://www . geesforgeks . org/面向大小的简短说明-度量/](https://www.geeksforgeeks.org/short-note-on-size-oriented-metrics/)

**面向大小的度量**通过考虑已生产软件的大小来标准化质量和生产率点度量，从而得出。组织为软件项目建立一个简单的规模测量记录。它建立在组织过去的经验之上。这是对软件的直接衡量。

这种度量是最简单和最早的度量之一，用于计算机程序测量大小。面向规模的度量也用于衡量和比较程序员的生产力。它是软件的直接衡量标准。尺寸测量基于代码行计算。代码行被定义为源文件中的一行文本。

在计算代码行数时，最简单的标准是:

*   不要计算空行
*   不计算评论
*   数数其他的一切
*   以大小为导向的衡量标准并不是一种普遍接受的方法。

可以开发的一套简单的尺寸测量方法如下:

```
Size = Kilo Lines of Code (KLOC) 
Effort = Person / month
Productivity = KLOC / person-month
Quality = Number of faults / KLOC
Cost = $ / KLOC
Documentation = Pages of documentation / KLOC 
```

**优势:**

*   使用这些指标，测量大小非常简单。
*   容易计算的软件开发工件。
*   许多已经作为键输入存在的方法都使用 LOC。
*   基于 LOC 的大量文献和数据已经存在。

**缺点:**

*   这个度量依赖于编程语言。
*   这种方法是根据编程语言精心设计的。
*   它不包含非过程语言。
*   有时，在开发的早期阶段很难估计 LOC。
*   虽然测量起来很简单，但是用户很难理解。
*   它不能测量规范的大小，因为它是在代码中定义的。

**示例–**
对于面向规模的指标，软件组织以表格形式维护记录。典型的表格条目有:项目名称、锁定、工作、文档页数、错误、缺陷、工作人员总数。

<center>

| 项目名 | 通信线路（LinesofCommunication） | 努力 | 成本(美元) | 医生。(页数) | 错误 | 缺点 | 人 |
| 字母表 | 10, 000 | Twenty | One hundred and seventy | four hundred | One hundred | Twelve | four |
| PQR | 20, 000 | Sixty | Three hundred | One thousand | One hundred and twenty-nine | Thirty-two | six |
| XYZ | 35, 000 | Sixty-five | Five hundred and twenty-two | One thousand two hundred and ninety | Two hundred and eighty | Eighty-seven | seven |

</center>