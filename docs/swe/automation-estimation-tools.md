# 自动化估算工具

> 原文:[https://www.geeksforgeeks.org/automation-estimation-tools/](https://www.geeksforgeeks.org/automation-estimation-tools/)

分解技术和经验估计模型可作为一系列软件工具的一部分。这种自动化的评估工具有助于评估成本和工作量，并对重要的项目变量进行“假设”分析，如交付数据或人员配置。

所有自动评估工具都显示相同的一般特征，并且都执行以下一般功能-

1.  **Sizing of Project Deliverable :**
    Estimated the size of one or more work products i.e., external representation of software, software itself, distributed functionality, descriptive information, all are approximate first.

2.  **Selecting Project Activities :**
    The required process framework is selected and the software engineering project is specified.
3.  **Predicting Staffing Levels :**
    The number of people available is specified. This is an important task, because the relationship between the people available and work is highly inauspicious.
4.  **Predicting Software Effort :**
    The estimation tool related to the use of some models from the size of project deliverable to the effort required (from producing them).
5.  **Predicting Software Cost :**
    Software costs can be calculated by assigning labor rates to project activities.
6.  **预测软件进度:**
    了解工作量、人员配备水平和项目活动后，可以根据建议的工作量分配模型，通过在软件工程活动中分配 lober 来生成进度草案。

对相同的项目数据应用不同的估计工具会导致预测结果发生相对较大的变化。此外，更重要的是，估计值明显不同于实际值。这加强了估计设备的输出应该被用作进行估计的数据点的概念。

根据这些数据进行的自动评估估计了模型项目、成本、工具实现的人员交易，以及在某些情况下，满足相关风险所需的开发进度和工作。王研究所开发的 WICOMO(王研究所成本模型)和数字设备公司开发的 DECplan 是基于 [COCOMO](https://www.geeksforgeeks.org/software-engineering-cocomo-model/) 的自动化估算工具。

每个设备都需要向用户提供初步估计的 20°c。这些近似按编程语言和类型(即定制代码、重用代码、新代码)分类。用户还可以指定成本动因属性的值。

每种工具都会产生一个估计的项目持续时间(以月为单位)、员工月工作量、每月平均人员配备、平均生产能力(以 LOC/pm 为单位)和每月成本。SLIM 是一个基于 Rayleigh Putnam 模型的自动成本计算系统 SLIM 应用了 Putnam 软件模型、线性规划、统计模拟和程序评估和审查技术，或 [PERT 技术](https://www.geeksforgeeks.org/project-evaluation-and-review-technique-pert/)来推导软件项目估算。

一旦确定了软件规模，SLIM 将计算规模偏差、指示成本和工作量可能偏差的敏感度曲线，以及与为类似规模的软件系统收集的检查数据的一致性。计划者可以实施线性规划分析，考虑成本和工作量的开发成本以及工作量的逐月分布，并对为类似规模的软件系统收集的数据进行一致性检查。