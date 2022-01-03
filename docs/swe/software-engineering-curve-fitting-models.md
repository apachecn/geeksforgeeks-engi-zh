# 软件工程|曲线拟合模型

> 原文:[https://www . geesforgeks . org/software-engineering-curve-fitting-models/](https://www.geeksforgeeks.org/software-engineering-curve-fitting-models/)

曲线拟合群组模型使用统计回归分析来研究软件复杂性与程序中的故障数量、变更数量或故障率之间的关系。这组模型通过使用线性回归、非线性回归或时间序列分析的方法找到输入和输出变量之间的关系。例如，因变量是程序中的错误数量。自变量是维护阶段改变的模块数量、故障间隔时间、程序员技能、程序大小等。这组模型包括:误差估计、复杂性估计、故障率估计。这些解释如下。

下图是实际值与估计值的关系。

![](img/bfc8b10478e4345eea8ca8a9404f47aa.png)

**1。误差估计模型:**
程序中的误差数量可以通过使用线性或非线性回归模型来估计。估算程序中初始误差总数 N 的简单非线性回归模型可表示如下:

![$ N = \Sigma a_{i} X_{i} + \Sigma b_{i} X^{2}_{i} + \Sigma c_{i} X^{3}_{i} + \varepsilon $ ](img/ed0120ce5613019df516a98740cb38dd.png "Rendered by QuickLaTeX.com")

其中 Xi 是第一误差因子；ai、bi、ci 为模型的系数，![\varepsilon ](img/bc701e16aa1ea1c85dfe4309ce5cc964.png "Rendered by QuickLaTeX.com")为误差项。典型的错误因素是软件复杂性度量和环境因素。大多数曲线拟合模型只涉及一个误差因素。

**2。复杂性估计模型:**
该模型用于使用时间序列方法估计软件复杂性 CR。软件复杂性模型总结如下:

![$ CR = a_{0} + a_{1} R + a_{2} E_{R} + a_{3} MR + a_{4} IR + a_{5} D + \varepsilon $ ](img/1a7c9214c6786adafa097430a012b385.png "Rendered by QuickLaTeX.com")

其中
R =发布序列号
ER =发布时的环境因素 R
MR =发布时的模块数量 R
IR =发布间隔 R
D =首次出现错误的天数
![\varepsilon ](img/bc701e16aa1ea1c85dfe4309ce5cc964.png "Rendered by QuickLaTeX.com") =错误

这种特殊的模型在软件评估时使用，因为时间意味着模型的更多版本被发布。

**3。故障率估算模型:**
该模型用于估算软件的故障率。给定故障时间 t1、t2，..tn，对第 I 个故障间隔的故障率的粗略估计是

![$ \widehat{\lambda}_{i} = \frac{1}{t_{i-1} - t_{i}} $ ](img/fbef79e15da7150a116691b910dfe9b8.png "Rendered by QuickLaTeX.com")

假设故障率是单调非递增的，则可以用最小二乘法得到这个函数的估计值![\lambda ](img/e0ceb1b60d218e033f25263665100b9a.png "Rendered by QuickLaTeX.com")，i = 1，2，…，n。