# 边界值测试用例、健壮用例和最坏情况测试用例

> 原文:[https://www . geeksforgeeks . org/边界值-测试用例-健壮-用例-最坏情况-测试用例/](https://www.geeksforgeeks.org/boundary-value-test-cases-robust-cases-and-worst-case-test-cases/)

为程序生成边界值分析、稳健和最坏情况测试用例，以找到三个数字的中间值。它的输入是正整数的三倍(比如 x、y 和 z)，最小值可以是 100，最大值可以是 500。

**三个数的中位数**是三个数全部排序时的中间数。

**示例–**

```
10, 40, 20
```

在这种情况下，中位数是 20 (10，20，40)。

**1。边界值测试案例**有–

```
for x, y, z :
min value = 100
close to min = 101
nominal = 300
close to max = 499
max = 500 
```

测试用例是，

```
4*3 + 1 = 13 
```

<center>

| X | Y | Z | 中位数 |
| --- | --- | --- | --- |
| One hundred | Three hundred | Three hundred | Three hundred |
| One hundred and one | Three hundred | Three hundred | Three hundred |
| Three hundred | Three hundred | Three hundred | Three hundred |
| Four hundred and ninety-nine | Three hundred | Three hundred | Three hundred |
| Five hundred | Three hundred | Three hundred | Three hundred |
| Three hundred | One hundred | Three hundred | Three hundred |
| Three hundred | One hundred and one | Three hundred | Three hundred |
| Three hundred | Four hundred and ninety-nine | Three hundred | Three hundred |
| Three hundred | Five hundred | Three hundred | Three hundred |
| Three hundred | Three hundred | One hundred | Three hundred |
| Three hundred | Three hundred | One hundred and one | Three hundred |
| Three hundred | Three hundred | Four hundred and ninety-nine | Three hundred |
| Three hundred | Three hundred | Five hundred | Three hundred |

</center>

**2。健壮测试用例–**
这里，我们超越了合法边界，它是边界值分析的延伸。

```
for x, y, z :
min value : 100  
close to min : 101  
nominal : 300 
close to max : 499 
max : 500 
lesser than min value : 99 
larger than max value : 501  
```

测试用例总数，

```
= 6*n+1 = 6*3+1 = 19 
```

因此，除了上述 13 种情况之外，还会有另外 6 种情况–

<center>

| X | Y | Z |
| --- | --- | --- |
| Ninety-nine | Three hundred | Three hundred |
| Five hundred and one | Three hundred | Three hundred |
| Three hundred | Ninety-nine | Three hundred |
| Three hundred | Five hundred and one | Three hundred |
| Three hundred | Three hundred | Ninety-nine |
| Three hundred | Three hundred | Five hundred and one |

**3。最差测试用例–**
如果我们拒绝可靠性的“单一”故障假设理论，并且考虑一个以上变量具有极值的情况，那么它被称为最差情况分析。

测试用例总数，

```
5^n = 5^3 = 125 cases 
```

<center>

| X | Y | Z | 中位数 |
| --- | --- | --- | --- |
| One hundred | One hundred | One hundred | One hundred |
| One hundred and one | One hundred | One hundred | One hundred |
| Three hundred | One hundred | One hundred | One hundred |
| Four hundred and ninety-nine | One hundred | One hundred | One hundred |
| Five hundred | One hundred | One hundred | One hundred |
| One hundred | One hundred and one | One hundred | One hundred |
| One hundred and one | One hundred and one | One hundred | One hundred and one |
| Three hundred | One hundred and one | One hundred | One hundred and one |
| Four hundred and ninety-nine | One hundred and one | One hundred | One hundred and one |
| … | … | … | … |

</center>

从数学上讲，测试用例将是 3 组的叉积–

```
  {100, 101, 300, 499, 500} 
x {100, 101, 300, 499, 500} 
x {100, 101, 300, 499, 500}
```

让我们设置一个，

```
= {100, 101, 300, 499, 500}
```

最糟糕的情况是，

```
= A x A x A 
```

</center>