# COCOMO 车型

的优势&劣势

> 原文:[https://www . geeksforgeeks . org/优势-劣势-cocomo-model/](https://www.geeksforgeeks.org/advantages-disadvantages-of-cocomo-model/)

**概述:**
Cocomo 代表建设性成本模型，是基于 LOC 即代码行数的回归模型。COCOMO 模型是 Boehm 在 1981 年提出的，它是一个软件项目的程序性成本估算模型，经常被用作可靠地预测与制定项目相关的各种参数(如规模、工作量、成本、时间和质量)的过程。COCOMO 模型是世界上最常用的模型之一

**COCOMO 的类别:**
任何一个软件模型根据开发复杂度分为有机、半分离和嵌入三类，如下所示。

1.  **Organic–**
    如果一个开发项目的规模相同，团队经验丰富，项目处理的是开发一个很好理解的应用程序，那么这个项目就被认为是有机的。例如数据处理系统和简单的业务系统。
2.  **半分离–**
    如果一个开发项目包含经验丰富或缺乏经验的团队成员，则该项目被认为是半分离的。例如数据库管理系统。
3.  **Embedded–**
    如果正在开发的软件与复杂的硬件强耦合，或者如果对操作方法有严格的规定，则开发项目被认为是嵌入式的。它是在一组严格约束的示例 ATM 中开发的。

**COCOMO 车型类型:**
COCOMO 车型三种类型如下。

**基本模型:**
COCOMO 模型提供了项目参数的准确大小。这有利于快速估算成本。估计的努力和计划的时间由下面的关系给出。

```
Effort (E) = a*(KLOC)b  MM
Scheduled Time (D) = c*(E)d  Months(M)
Where,

E            = Total effort required for the project in Man-Months (MM).
a, b, c, d   = The constant parameters for a software project.
D            = Total time required for project development in Months (M).
KLOC         = The size of the code for the project in Kilo lines of code.
```

**中间模型** :
中间 COCOMO 将软件开发工作量计算为程序规模和一组“成本驱动因素”的函数，这些因素包括对产品、硬件、人员和项目属性的主观评估。估计的努力和计划的时间由下面的关系给出。

```
Effort (E) = a*(KLOC)b *EAF  MM
Scheduled Time (D) = c*(E)d  Months(M)

E           = Total effort required for the project in Man-Months (MM).
a, b, c, d  = The constant parameters for a software project.
D           = Total time required for project development in Months (M).
KLOC        = the size of the code for the project in Kilo lines of code.
EAF         = Efforts adjustment factors 
```

**详细模型:**
详细 COCOMO 结合了标准版本的所有质量，并评估了成本动因对软件工程过程中每种方法的影响。

**优势:**

*   它处理历史数据，并提供更准确的细节。
*   各种因素下易于实施。人们很容易理解它是如何工作的。
*   易于估算项目的总成本。
*   驱动因素非常有助于理解影响项目危机的不同因素的影响。

**缺点:**

*   它忽略了硬件问题以及个人营业额水平。
*   它忽略了所有的文档和需求。
*   这主要取决于时间因素。
*   它限制了软件成本的准确性。
*   它过分简化了安全或安保方面的影响。
*   它还忽略了客户技能、合作和知识。