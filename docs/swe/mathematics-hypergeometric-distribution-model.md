# 数学|超几何分布模型

> 原文:[https://www . geesforgeks . org/数学-超几何-分布-模型/](https://www.geeksforgeeks.org/mathematics-hypergeometric-distribution-model/)

超几何分布模型用于根据超几何分布估计在测试或调试过程开始时程序中最初存在的故障数量。假设![$C_i-1$](img/e2ff038a2056af73e265500fd9acc0bf.png "Rendered by QuickLaTeX.com")是到目前为止![$t_1, t_2, ...., t_i-1$](img/d1cd7601c85bb7b28f21e2a3a3760707.png "Rendered by QuickLaTeX.com")已经检测到的累计错误数，假设![$N_i](img/b7c80da4df6422e6ad793d6e8f75dc3a.png "Rendered by QuickLaTeX.com")是到时间![$t_i$](img/7643aa4ef38c1b99e98cd082c1d7cfc1.png "Rendered by QuickLaTeX.com")新检测到的错误数。

**假设:**

1.  当测试阶段开始时，一个程序最初包含 m 个错误。
2.  测试被定义为由输入数据和输出数据组成的多个测试实例。换句话说，一天或一周内执行的测试操作的集合称为测试实例。对于 i = 1，2，.，测试实例由![$t_i$](img/7643aa4ef38c1b99e98cd082c1d7cfc1.png "Rendered by QuickLaTeX.com")表示。。。，n。
3.  检测到的故障不会在测试实例之间移除。

因此，根据后一种假设，在几个测试实例中可能会遇到相同的故障。设![$W_i$](img/c6d459aaf5f042c03f05c77f8788352a.png "Rendered by QuickLaTeX.com")为测试实例![$t_i$](img/7643aa4ef38c1b99e98cd082c1d7cfc1.png "Rendered by QuickLaTeX.com")经历的故障数。需要注意的是，一些![$W_i$](img/c6d459aaf5f042c03f05c77f8788352a.png "Rendered by QuickLaTeX.com")故障可能是那些已经在![$C_i-1$](img/e2ff038a2056af73e265500fd9acc0bf.png "Rendered by QuickLaTeX.com")中计数的故障，剩余的 Wi 故障是新检测到的故障。
如果![$n_i$](img/e3321c4402dd22bc70cf7885c127a639.png "Rendered by QuickLaTeX.com")是![$N_i$](img/d250dc6ff5c7bb8a4afc7a89ce1a9249.png "Rendered by QuickLaTeX.com")的观察实例，那么我们可以看到![$n_i \leq W_i$](img/f405736168380f42e9a334037e22a6ad.png "Rendered by QuickLaTeX.com")。每个故障可以分为两类:

1.  新发现的断层
2.  重新发现的错误

如果我们假设新检测到的故障数量![$N_i$](img/d250dc6ff5c7bb8a4afc7a89ce1a9249.png "Rendered by QuickLaTeX.com")遵循超几何分布，那么在![$W_i$](img/c6d459aaf5f042c03f05c77f8788352a.png "Rendered by QuickLaTeX.com")故障中准确获得新检测到的故障的概率为:

![$P(N_i=n_i)=\frac{\binom{m-C_{i-1}}{n_i}\binom{C_{i-1}}{W_i-n_i}}{\binom{m}{W_i}}$](img/44f123c66cd0995f9c51472e98ccbea4.png "Rendered by QuickLaTeX.com")

在哪里

![$C_{i-1}= \Sigma_{k=1}^{i-1}n_k, \; C_0=0\; n_0=0 $](img/b5eb0b9a0b0035b5abd34d8ff5bfdc8d.png "Rendered by QuickLaTeX.com")

和

![$max\{0, W_i-C_{}i-1\}\leq n_i\leq max\{W_i, m-C_{i-1}\}$](img/9cd0370437268410ec342571c0dab28b.png "Rendered by QuickLaTeX.com")

因为假设![$N_i$](img/d250dc6ff5c7bb8a4afc7a89ce1a9249.png "Rendered by QuickLaTeX.com")是超几何分布的，所以在间隔![$[t_{i-1}, t_i]$](img/d2856af15da08543af3eca6bcecc8883.png "Rendered by QuickLaTeX.com")期间新检测到的故障的预期数量是，

![$E(N_i)=\frac{(m-C_i)W_i}{m}$](img/e194cd72c56ea6c18dfacd6ecd975cee.png "Rendered by QuickLaTeX.com")

![$C_i$](img/749baff5973cd96e7c9e5f8b026fcb61.png "Rendered by QuickLaTeX.com")的期望值由下式给出:

![$E(C_i)=m\left [1- \prod_{j=1}^i (1-p_i)  \right ]$](img/3956a759717b631c55f5af4a017c8b69.png "Rendered by QuickLaTeX.com")

在哪里

![$p_i=\frac{W_i}{m}\; i=1, 2, ...$](img/0841a18aaf949928e60f2d811d2a347d.png "Rendered by QuickLaTeX.com")