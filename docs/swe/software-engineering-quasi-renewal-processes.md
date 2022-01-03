# 软件工程|准更新流程

> 原文:[https://www . geesforgeks . org/软件-工程-准续约-流程/](https://www.geeksforgeeks.org/software-engineering-quasi-renewal-processes/)

设{N(t)，t > 0}为计数过程，设![$X_n$](img/3745f1424b52a016adc9acb77118f0e3.png "Rendered by QuickLaTeX.com")为该过程的![$(n-1)_{th}$](img/95f1ac815d67da1ad64b46937a98be9d.png "Rendered by QuickLaTeX.com")和![$n_{th}$](img/4081d6789607aa4e2ad207c1bbeca141.png "Rendered by QuickLaTeX.com")事件之间的时间，![ n\geq 1](img/06b08f8fbd95627688bfddf75e8af5be.png "Rendered by QuickLaTeX.com")。

**定义:**
非负随机变量序列{X1，X2，…。}是独立的

![$X_i=aX_{i-1}$](img/55f34197fc1588e64ec628052c15d5e2.png "Rendered by QuickLaTeX.com")

对于![$i\geq 2$](img/da6342eed83bbb520cc8def0a1f4d9be.png "Rendered by QuickLaTeX.com")中![$\alpha > 0$](img/440748e8e4cb14510b88729b48b48f3a.png "Rendered by QuickLaTeX.com")为常数，则计数过程{N(t)，t ![$\geq $](img/55f80f397b4907ad00693492d9512a3c.png "Rendered by QuickLaTeX.com") 0}称为带参数和第一个到达间隔时间![$X_1$](img/8484b808ad8c282fa591d46a4c85d919.png "Rendered by QuickLaTeX.com")的准更新过程。

当![$\alpha $](img/3818947e95c84b048cc6ef1855a9d0dd.png "Rendered by QuickLaTeX.com") = 1 时，这个过程成为普通的更新过程。这种准更新过程可用于![$\alpha $](img/3818947e95c84b048cc6ef1855a9d0dd.png "Rendered by QuickLaTeX.com") > 1 的软件测试阶段和硬件老化阶段的可靠性增长过程建模，以及![$\alpha \geq $](img/6a2553e62f583027276be0527670835f.png "Rendered by QuickLaTeX.com") 1 时的硬件维护过程建模。

**与准更新过程相关的重要公式:**
分别假设随机变量![$ X_1\: are\: f_1(x), F_1(x), s_1(x), and\: r_1(x)$](img/e9d3148dfd95d860a6ddbc5b00e558dd.png "Rendered by QuickLaTeX.com")的概率密度函数、累积分布函数、生存函数和失效率。然后，

1.  The pdf(probability density function) of Xn for n = 1, 2, 3, … is

    ![$f_n(x)= \frac{1}{\alpha^{n-1}}f_1\left (\frac{1}{\alpha^{n-1}}x\right ) $](img/cc3310e4264197e3dd45d0ae1204b6fd.png "Rendered by QuickLaTeX.com")

2.  The cdf(cumulative density function) of Xn for n = 1, 2, 3, … is

    ![$F_n(x)= F_1\left (\frac{1}{\alpha^{n-1}}x\right ) $](img/66175a3dc93f9c94af23b348276080ae.png "Rendered by QuickLaTeX.com")

3.  The survival function of Xn for n = 1, 2, 3, … is

    ![$S_n(x)= S_1\left (\frac{1}{\alpha^{n-1}}x\right ) $](img/525ca0c59a987aac18dbe94bdf0e9883.png "Rendered by QuickLaTeX.com")

4.  The failure rate of Xn for n = 1, 2, 3, … is

    ![$ f_n(x)= \frac{1}{\alpha^{n-1}}r_1\left (\frac{1}{\alpha^{n-1}}x\right )$](img/50b98c39983872b89f7317350a6e34cd.png "Rendered by QuickLaTeX.com")

类似地，Xn 的均值和方差如下所示

![$E(X_n)=\alpha^{n-1}E(X_1)$ $ Var(X_n)=\alpha^{2n-2}Var(X_1)$ ](img/ee73d9f17c7cdb38a599fe07562c386c.png "Rendered by QuickLaTeX.com")

由于![$X_1$](img/8484b808ad8c282fa591d46a4c85d919.png "Rendered by QuickLaTeX.com")的非负性和![$X_1$](img/8484b808ad8c282fa591d46a4c85d919.png "Rendered by QuickLaTeX.com")不是同 0 的事实，我们得到

![$ E(X_1)=\mu \neq 0 $](img/8c3c36c0270c200dc0266a7fa871e354.png "Rendered by QuickLaTeX.com")

**命题-1:**
如果![$X_1$](img/8484b808ad8c282fa591d46a4c85d919.png "Rendered by QuickLaTeX.com")遵循伽玛、威布尔或对数正态分布，那么对于准更新过程来说![$X_n$](img/3745f1424b52a016adc9acb77118f0e3.png "Rendered by QuickLaTeX.com")的形状参数对于 n = 1、2、3、…是相同的。这意味着“更新”后，到达间隔时间的形状参数不会改变。在软件可靠性中，软件调试过程不改变无错分布类型的假设似乎是合理的。

因此，在由准更新过程建模的调试阶段期间，软件的无错误时间将具有相同的形状参数。从这个意义上说，准更新过程适合于对软件可靠性增长建模。值得注意的是，

![ $ \lim_{n \rightarrow  \infty } \frac{E(X_1+X_2+ ... +X_n)}{n}&= \lim_{n \rightarrow  \infty }\frac{\mu_{1}(1-\alpha^n)}{(1-\alpha)n} $ $=\; 0 if\; \alpha\:  \: 1 $ ](img/761cedc7d90e1804810f21049fb17f1e.png "Rendered by QuickLaTeX.com")

因此，如果到达间隔时间代表软件系统的无错误时间，那么当其调试过程长时间发生时，平均无错误时间接近无穷大。

**命题-2:**
拟更新过程的首次到达间隔分布唯一地决定了其更新函数。如果到达间隔时间代表无错误时间(首次故障时间)，则可以使用准更新过程来模拟软件和硬件的可靠性增长。

假设软件的所有故障都有相同的被检测到的机会。如果准更新过程的到达间隔时间代表软件系统的无错误时间，那么时间间隔[0，t]内软件故障的预期数量可以由更新函数 m(t)定义，参数为![\alpha > 1](img/4a7f5c081567c3092656b76ba8aaa296.png "Rendered by QuickLaTeX.com")。由![$m_r(t)$](img/14a4176d6444f67f911020e50e4f60e1.png "Rendered by QuickLaTeX.com")表示，在时间 t 剩余的软件故障的数量，如下:

![$m_r(t)=m(T_c)-m(t)$](img/25366f791cac8cd5ad83c56e31bbaf70.png "Rendered by QuickLaTeX.com")

其中![$m(T_c)$](img/532077560ccdef13f45b23516cbdeeae.png "Rendered by QuickLaTeX.com")是最终将通过软件生命周期 Tc 检测到的故障数量。