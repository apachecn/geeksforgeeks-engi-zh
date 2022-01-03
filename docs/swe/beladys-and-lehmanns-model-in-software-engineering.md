# 软件工程中的贝拉蒂和莱曼模型

> 原文:[https://www . geesforgeks . org/Bela dys-and-lehmanns-model-in-software-engineering/](https://www.geeksforgeeks.org/beladys-and-lehmanns-model-in-software-engineering/)

Belay 和 Lehmann (1972)是最早尝试在预测模型中捕捉维护工作的研究人员之一。该模型明确了这样一个概念，即如果使用糟糕的软件开发方法，那么工作量和成本会成倍增加，并且开发该软件的人不再能够执行软件的维护。Belady 和 Lehmann 在一个等式中捕捉到了这些效应:

**M = P+Ke<sup>(c-d)</sup>**

*   M = total maintenance workload of a system extension.
*   P = It represents all productive work, such as analysis, evaluation, design, coding and testing.
*   C = Complexity caused by lack of structured design and documentation.
*   D = is the familiarity of the maintenance team with the software.
*   K = the constant determined by comparing the relationship between this model and the actual project effort; It is called empirical constant because its value depends on the environment.

这个等式在决定维护工作量的因素中起着非常重要的关系。在给定的关系中，如果软件不是用软件工程过程开发的，那么 c 的值就会增加。当然，对于系统结构高度化的大型软件产品来说，c 会比同等程度的小型软件产品更高。如果维护软件时不了解软件的结构、功能和用途，那么“d”的值就会很低。这样，结果发现随着维护成本呈指数级增长。因此，为了节约维护成本，最好的方法是使用好的软件工程实践来构建系统，并让维护人员熟悉软件。

**<u>例:</u>** 一个软件项目的开发工作量是 300 人-月。经验确定的常数(K)为 0.3。代码的复杂度等于 8(相当高的值)。在以下情况下，计算总工作量(M)

1.  维护团队对项目有很好的理解水平(d = 0.9)。
2.  维护团队对项目的理解较差)d = 0.1)

**<u>解决方案:</u>** 开发工作量(P) =下午 300

```
K = 0.3
C = 8
```

1.维护团队有良好的理解水平(d = 0.9)

```
M = P + ke(c-d)
  = 300 + 0.3e(8-0.9)
  = 300 + 363.59
  = 663.59 PM
```

2.维护团队理解水平差(d = 0.1)

```
M = P + Ke(c-d)
  = 300 + 0.3e(8-0.1)
  = 300 + 809.18
  = 1109.18 PM
```

因此，从上面的例子中可以清楚地看出，如果使用了糟糕的软件工程方法，那么工作量会成倍地增加，并且项目的可理解性也很差。