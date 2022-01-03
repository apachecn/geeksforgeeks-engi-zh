# 数据分析建模

> 原文:[https://www . geesforgeks . org/model-building-for-data-analytics/](https://www.geeksforgeeks.org/model-building-for-data-analytics/)

**先决条件–**[数据分析的生命周期阶段](https://www.geeksforgeeks.org/life-cycle-phases-of-data-analytics/)

**模型构建:**
在此阶段，数据科学团队需要开发用于培训、测试和生产目的的数据集。这些数据集使数据科学家能够开发分析方法并对其进行训练，同时保留一些数据用于测试模型。

团队为测试、培训和生产目的开发数据集。此外，在这个阶段，团队基于模型规划阶段所做的工作来构建和执行模型。该团队还考虑其现有工具是否足以运行模型，或者是否需要更健壮的环境来执行模型和工作流(例如，快速硬件和并行处理)。

**免费或开源工具:**

```
Rand PL/R, Octave, WEKA, Python 
```

**商业工具–**

```
Matlab, STASTICA 
```

**建模阶段常用工具:**

**R 和 PL/R :**
它们在前面的模型规划阶段就有描述，PL/R 是 PostgreSQL 用 R 的过程语言，使用这种方法意味着 R 命令可以在数据库中执行。

**[【Octave】T2:](https://www.geeksforgeeks.org/basic-operations-in-octave/)**
它是用于计算建模的自由软件编程语言，具有 Matlab 的一些功能。因为是免费提供的，所以 Octave 在各大高校教授机器学习的时候都会用到。

**WEKA :**
它是一个带有分析工作台的免费数据挖掘软件包。WAKA 中创建的函数可以在 java 代码中执行。

**[Python](https://www.geeksforgeeks.org/python-programming-language/) :**
是为机器学习和分析提供工具包的编程语言，如 scikit-learn、 [NumPy](https://www.geeksforgeeks.org/python-numpy/) 、 [scipy](https://www.geeksforgeeks.org/data-analysis-with-scipy/) 、 [Pandas](https://www.geeksforgeeks.org/pandas-tutorial/) ，以及使用 matplotlib 的相关数据可视化。

**[SQL](https://www.geeksforgeeks.org/sql-tutorial/) :**
数据库实现中的 SQL，比如 MADlib，提供了一个替代内存桌面的分析工具。

**MADlib :**
它为 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 或 Greenplum 提供了一个可以在数据库中执行的开源机器学习算法库。

**模型构建的生命周期–**

*   选择变量
*   余额数据
*   构建模型
*   使生效
*   部署
*   维持
*   定义成功
*   浏览数据
*   条件数据

数据探索用于找出数据的要点，并对其质量、数量和特征进行初步评估。可视化技术也可以应用。然而，在具有许多输入变量的高维空间中，这可能是一项困难的任务。在数据调节中，我们对功能数据进行分组，然后在重新缩放后应用于建模技术，在某些情况下，如果变量耦合，重新缩放是一个问题。可变截面对开发质量模型非常重要。

这个过程是隐含的模型相关的，因为它被用来配置在正在进行的模型开发中应该使用哪个变量组合。数据平衡是将数据划分为适当的子集，用于训练、测试和验证。模型构建是关注期望的算法。最著名的技术是符号回归，其他技术也可以优先考虑。

模型验证对于在使用前培养信任感很重要。好模型的定义包括稳健性和定义明确的准确性。因此，可信精确模型也有潜在的财务和物理危险，但可信度量对于符号回归和堆叠分析网络非常重要。