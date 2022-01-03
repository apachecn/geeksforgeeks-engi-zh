# 组合测试中的测试配置生成–示例| Set-2

> 原文:[https://www . geesforgeks . org/test-configuration-generation-in-composite-testing-example-set-2/](https://www.geeksforgeeks.org/test-configuration-generation-in-combinatorial-testing-example-set-2/)

我们已经在文章【组合测试中的测试配置生成】中讨论了用于测试配置生成的算法。让我们通过下面给出的一个已解决的例子来深入理解该算法。

### 例子

考虑一个可以在三种浏览器中任意一种上运行的应用程序:Safari、Internet Explorer 和 Firefox。该应用程序运行在三个操作系统上，包括 Windows、macOS 和 Linux。该应用程序能够使用三种连接协议(包括局域网、点对点协议和综合业务数字网)连接到设备。此外，输出被发送到本地或网络打印机，或者由应用程序发送到屏幕。对于给定的应用程序，请执行以下操作:

1.  确定给定问题中的因素和级别
2.  使用满足以下约束的 MOLS 为应用程序生成测试配置:
    *   Safari 只支持 macOS
    *   互联网资源管理器仅适用于 Windows
    *   火狐适用于所有三种操作系统，即苹果操作系统、视窗操作系统和 Linux

**解决方案:**

**1。确定因素和水平**

对于给定的问题，因素和级别为:

<figure class="table">

| 工厂 | 级别 |
| --- | --- |
| F1′:浏览器 | Safari，互联网浏览器，火狐 |
| F2′:操作系统 | Windows、macOS、Linux |
| F3’:协议 | 局域网、购买力平价、综合业务数字网 |
| F4 的:打印机 | 网络、本地、至屏幕 |

所以总共有 **4 个因子，每个因子有 3 个等级**。

**2。生成测试配置**

**(a)重新标记因素**

必须重新标记以下因素:

```
Since, |F1| = |F2| = |F3| = |F4| = 3

So, the relation |F1| >= |F2| >= |F3| >= .........|Fn-1| >= |Fn| is satisfied.
Therefore, factors are labeled as: 
F1 = F1'
F2 = F2'
F3 = F3'
F4 = F4'

Also, as b = |F1| and k = |F2|, 
Therefore, b = 3 and k = 3

```

**注:** |Fi|为因子 Fi 中的级数。此外，b 表示块的数量，k 表示每个块中的行数。

**(b)准备表格并填写 F1 和 F2 栏**

现在让我们准备一个包含 4 列的表格，因为有四个因素。另外，我们需要(b x k)行数，即(3 x 3 ) = 9 行，分成 3 个块。现在，我们用块 1 中的 1、块 2 中的 2 填充 F1 列，以此类推。此外，我们使用第 1 行到第 k 行中的序列 1，2，3…k 填充列 F2。

<figure class="table">

| 街区 | 排 | 子一代 | 第二子代 | 第三子代 | 法乐四联症 |
| --- | --- | --- | --- | --- | --- |
| one | one | one | one |   |   |
| one | Two | one | Two |   |   |
| one | three | one | three |   |   |
| Two | one | Two | one |   |   |
| Two | Two | Two | Two |   |   |
| Two | three | Two | three |   |   |
| three | one | three | one |   |   |
| three | Two | three | Two |   |   |
| three | three | three | three |   |   |

</figure>

**(c)找到 k 阶的 MOLS 并填充其余的列**

```
Since k = 3,

So, MOLS of order 3 are required. 
We know that if k is a prime or power of prime then number of MOLS = k - 1
As k = 3 is prime, therefore 2 MOLS exists that are: 

    1  2  3            1  2  3
M1 =    2  3  1        M2 =    3  1  2
    3  1  2            2  3  1

```

我们使用 F3 的 M1 列和 F4 的 M2 列来填充剩下的两列:

<figure class="table">

| 街区 | 排 | 子一代 | 第二子代 | 第三子代 | 法乐四联症 |
| --- | --- | --- | --- | --- | --- |
| one | one | one | one | one | one |
| one | Two | one | Two | Two | three |
| one | three | one | three | three | Two |
| Two | one | Two | one | Two | Two |
| Two | Two | Two | Two | three | one |
| Two | three | Two | three | one | three |
| three | one | three | one | three | three |
| three | Two | three | Two | one | Two |
| three | three | three | three | Two | one |

**(d)检查是否满足约束**

在给定的问题中，因素 **F1(浏览器)和 F2(操作系统)相互依赖**如下:

*   Safari 只支持 macOS
*   互联网资源管理器仅适用于 Windows
*   火狐适用于所有三种操作系统，即苹果操作系统、视窗操作系统和 Linux

因此，如果该行中的某个条目不满足上述约束条件，则该条目会以黄色突出显示:

<figure class="table">

| 街区 | 排 | 子一代 | 第二子代 | 第三子代 | 法乐四联症 |
| --- | --- | --- | --- | --- | --- |
| one | one | 1 | 1 | one | one |
| one | Two | one | Two | Two | three |
| one | three | 1 | 3 | three | Two |
| Two | one | Two | one | Two | Two |
| Two | Two | 2 | 2 | three | one |
| Two | three | 2 | 3 | one | three |
| three | one | three | one | three | three |
| three | Two | three | Two | one | Two |
| three | three | three | three | Two | one |

在上表中，有四行不满足给定的约束。比如 Block 1 的第 1 行，F1 = 1，F2 = 1，即 F1 是 Safari，F2 是 Windows，但是第一个约束中明确提到 Safari 只支持 macOS，不支持其他操作系统。因此，该行不满足约束，因此被突出显示。

**(e)删除不满足给定约束的配置**

上表中以黄色突出显示的配置必须删除，为此，我们将使用两步程序:

1.  修改高亮显示的行，以保持约束
2.  添加新的配置，覆盖在替换突出显示的行时未覆盖的对

因此，在第一步中，我们修改上面突出显示的行，使这些行满足给定的约束。修改后的表格如下:

<figure class="table">

| 街区 | 排 | 子一代 | 第二子代 | 第三子代 | 法乐四联症 |
| --- | --- | --- | --- | --- | --- |
| one | one | one | Two | one | one |
| one | Two | one | Two | Two | three |
| one | three | one | Two | three | Two |
| Two | one | Two | one | Two | Two |
| Two | Two | Two | one | three | one |
| Two | three | Two | one | one | three |
| three | one | three | one | three | three |
| three | Two | three | Two | one | Two |
| three | three | three | three | Two | one |

```
For the second step, The new configurations are as follows: 

F1    F2    F3    F4    
-    1    1    1    ....(A)
-    3    3    2    ....(B)
-    2    3    1    ....(C)
-    3    1    3    ....(D)

Here, '-' denotes that F1 could take any value out of 1,2,3.

```

**(A)和(C)在上表中已经满足**，因为:

*   F2 = 1 和 F3 = 1 出现在块 2 的第 3 行。此外，块 1 的行 1 中出现 F3 = 1 和 F4 = 1。因此，(甲)是满意的
*   类似地，F2 = 2 和 F3 = 3 出现在块 1 的第 3 行，并且 F3 = 3 和 F4 = 1 出现在块 2 的第 2 行。因此，满足(C)

但是，上表中不满足(B)和(D)，所以我们将它们添加到唯一配置表中。更新后的表格如下所示:

<figure class="table">

| 街区 | 排 | 子一代 | 第二子代 | 第三子代 | 法乐四联症 |
| --- | --- | --- | --- | --- | --- |
| one | one | one | Two | one | one |
| one | Two | one | Two | Two | three |
| one | three | one | Two | three | Two |
| Two | one | Two | one | Two | Two |
| Two | Two | Two | one | three | one |
| Two | three | Two | one | one | three |
| three | one | three | one | three | three |
| three | Two | three | Two | one | Two |
| three | three | three | three | Two | one |
| four | one | – | three | three | Two |
| four | Two | – | three | one | three |

**(f)用给定的因子值**替换列中的数字

现在，我们用实际值(即级别)替换 F1、F2、F3 和 F4 列的值。**最终设计配置**如下所示:

<figure class="table">

| 没有。 | 子一代 | 第二子代 | 第三子代 | 法乐四联症 |
| --- | --- | --- | --- | --- |
| one | 1 [Safari] | 2 [macOS] | 1[局域网] | 1[网络] |
| Two | 1 [Safari] | 2 [macOS] | 2[购买力平价] | 3[至 _ 屏幕] |
| three | 1 [Safari] | 2 [macOS] | 3[综合业务数字网] | 2[本地] |
| four | 2[互联网浏览器] | 1[视窗] | 2[购买力平价] | 2[本地] |
| five | 2[互联网浏览器] | 1[视窗] | 3[综合业务数字网] | 1[网络] |
| six | 2[互联网浏览器] | 1[视窗] | 1[局域网] | 3[至 _ 屏幕] |
| seven | 3[火狐] | 1[视窗] | 3[综合业务数字网] | 3[至 _ 屏幕] |
| eight | 3[火狐] | 2 [macOS] | 1[局域网] | 2[本地] |
| nine | 3[火狐] | 3 [Linux] | 2[购买力平价] | 1[网络] |
| Ten | – | 3 [Linux] | 3[综合业务数字网] | 2[本地] |
| Eleven | – | 3 [Linux] | 1[局域网] | 3[至 _ 屏幕] |

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>