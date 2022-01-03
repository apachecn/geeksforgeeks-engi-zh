# 软件工程| Goel-Okumoto 模型

> 原文:[https://www . geesforgeks . org/software-engineering-goel-oku moto-model/](https://www.geeksforgeeks.org/software-engineering-goel-okumoto-model/)

Goel-Okumoto 模型(也称为指数 NHPP 模型)基于以下假设:

1.  程序中的所有故障都与故障检测观点相互独立。
2.  任何时候检测到的故障数量都与程序中当前的故障数量成正比。这意味着故障实际发生(即检测到)的概率是恒定的。
3.  在未来的测试场合之前，隔离的故障被移除。
4.  每次发生软件故障时，导致故障的软件错误会立即被删除，并且不会引入新的错误。

这显示在下面的微分方程中:

![$\frac{\partial m(t)}{\partial t} = b[a-m(t)]$  \null\hfill    Eqn(1)](img/a31dffa6557b338c53782f01b8ee158a.png "Rendered by QuickLaTeX.com")

其中 a 是测试前软件中存在的预期故障总数，b 是故障检测率或故障的故障强度。

微分方程 1 的平均值函数解由下式给出

![$m(t) = a(1-e^{-bt})$](img/11bc19776e4efb494feb3be3756b565c.png "Rendered by QuickLaTeX.com")

这个模型被称为 **Goel-Okumoto 模型**

对于第一类数据，使用最大似然估计方法的 Goel-Okumoto 模型的参数 a 和 b 的估计可以通过同时求解以下方程获得:

![$a= \frac{y_n}{(1-e^{-bt_n})}\\$ $\frac{y_nt_ne^{-bt_n}}{1-e^{-bt_n}} = \sum_{k=1}^n  \frac{(y_k-y_{k-1})(t_ke^{-bt_k}-t_{k-1}e^{-bt_{k-1}})}{(e^{-bt_{k-1}}-e^{-bt_k})}  \\ $](img/cf18853254f0847bbe12a3bc4b8e4bfa.png "Rendered by QuickLaTeX.com")

类似地，对于第二类数据，使用最大似然估计
方法对参数 a 和 b 的估计可以通过求解以下方程获得:

![$a= \frac{n}{(1-e^{-bS_n})}\\$ $\frac{n}{b} = \sum_{k=1}^n S_i + \frac{nS_ne^{(-bS_n)}}{1-e^{-bS_n})}  \\ $](img/35c7ccb50bd3abbbe55a19419fb0dbfa.png "Rendered by QuickLaTeX.com")

设![ $\hat{a}$ ](img/1dce08fa8c2d4ed3261216803c58f030.png "Rendered by QuickLaTeX.com")和![$ \hat{b} $ ](img/1ddff0866fb595b786ff79ff94246443.png "Rendered by QuickLaTeX.com")分别为参数 a 和 b 的 MLE。然后，我们可以获得平均值函数和可靠性函数的最大似然估计，如下所示:

![$\hat{m} (t)=\hat{a} [1-e^{-\hat{b}t}]$ $ \hat{R} (x|t)=e^{-\hat{a}[e^{-\hat{b}t}-e^{-\hat{b}(t+x)}]}$ ](img/6418b17dde98cc2a0b9ec2d70f399f86.png "Rendered by QuickLaTeX.com")

在时间 t，N(t)确定故障数量的可变性是有意义的。人们可以根据泊松分布近似地获得 N(t)的置信区间

![$\hat{m}-z_{\alpha} \sqrt{\hat{m}(t)}\leq N(t)\leq \hat{m}(t) + z_{\alpha}  \sqrt{\hat{m}(t)}  $ ](img/6459c6d6e67f72eb296dbb91518dffb1.png "Rendered by QuickLaTeX.com")

其中![$z_a$](img/beb480dc61facd71f9233aae3d730b88.png "Rendered by QuickLaTeX.com")为标准正态分布的![$100(1+\alpha)/2$](img/3669ea0ecdd6d795e344331d86f2f32a.png "Rendered by QuickLaTeX.com")百分位，即 N(0，1)。