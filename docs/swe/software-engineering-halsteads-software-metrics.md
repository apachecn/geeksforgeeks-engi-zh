# 软件工程|霍尔斯特德的软件度量

> 原文:[https://www . geesforgeks . org/software-engineering-halsteads-software-metrics/](https://www.geeksforgeeks.org/software-engineering-halsteads-software-metrics/)

计算机程序是一种算法的实现，该算法被认为是可以被分类为运算符或操作数的标记的集合。**霍尔斯特德的度量标准**包含在当前许多计算软件代码行数的商业工具中。通过对标记进行计数并确定哪些是运算符，哪些是操作数，可以收集以下基本度量:

n1 =不同运算符的数量。
n2 =不同操作数的数量。
N1 =运算符出现的总数。
N2 =操作数出现的总次数。

除上述内容外，霍尔斯特德还定义了以下内容:

n1* =潜在操作员的数量。
n2* =潜在操作数的数量。

Halstead 将 n1*和 n2*分别视为模块和程序的最小可能运算符和操作数。这个最小数量将体现在编程语言本身中，其中所需的操作将已经存在(例如，在 C 语言中，任何程序必须至少包含函数 main()的定义)，可能作为函数或过程:n1* = 2，因为任何函数或过程必须出现至少 2 个运算符:1 表示函数的名称，1 表示赋值或分组符号，n2*表示需要传递给函数或过程的参数数量，没有重复。

### 霍尔斯特德指标–

霍尔斯特德的衡量标准是:

*   **Halstead Program Length –** The total number of operator occurrences and the total number of operand occurrences. 
    N = N1 + N2 

    估计程序长度为，n<sup>^</sup>= n1 log<sub>2</sub>n1+N2 log<sub>2</sub>N2

    已发布以下替代表达式来估计程序长度:

    *   N <sub>J</sub> = log <sub>2</sub> (n1！)+ log <sub>2</sub> (n2！)
    *   n<sub>B</sub>= n1 * log<sub>2</sub>N2+N2 * log<sub>2</sub>n1
    *   n<sub>c</sub>= n1 * sqrt(n1)+N2 * sqrt(N2)
    *   N <sub>S</sub> = (n * log <sub>2</sub> n) / 2
*   **霍尔斯特德词汇表–**唯一运算符和唯一操作数出现的总数。
    n = n1 + n2
*   **Program Volume –** Proportional to program size, represents the size, in bits, of space necessary for storing the program. This parameter is dependent on specific algorithm implementation. The properties V, N, and the number of lines in the code are shown to be linearly connected and equally valid for measuring relative program size. 

    V =大小* (log <sub>2</sub> 词汇)= N * log <sub>2</sub> (n)

    体积的计量单位是尺寸“位”的通用单位。如果对词汇表使用统一的二进制编码，它就是程序的实际大小。并且误差=体积/ 3000

*   **Potential Minimum Volume –** The potential minimum volume V* is defined as the volume of the most succinct program in which a problem can be coded. 

    V* = (2 + n2*) * log <sub>2</sub> (2 + n2*)

    这里，n2*是唯一输入和输出参数的计数

*   **Program Level –** To rank the programming languages, the level of abstraction provided by the programming language, Program Level (L) is considered. The higher the level of a language, the less effort it takes to develop a program using that language. 

    L = V* / V

    L 的值在 0 和 1 之间，L=1 表示以最高可能的级别(即最小大小)编写的程序。
    估计节目级别为 L <sup>^</sup> =2 * (n2) / (n1)(N2)

*   **程序难度–**此参数显示程序的处理难度。
    D =(n1/2)*(N2/N2)
    D = 1/L
    随着一个程序执行量的增加，程序层级降低，难度增加。因此，编程实践，如操作数的冗余使用，或未能使用更高级别的控制结构，将会增加容量和难度。
*   **编程努力–**衡量将现有算法转化为指定程序语言实现所需的脑力活动量。
    E = V / L = D * V =难度*体积

*   **Language Level –** Shows the algorithm implementation program language level. The same algorithm demands additional effort if it is written in a low-level program language. For example, it is easier to program in Pascal than in Assembler. 
    L’ = V / D / D 
    lambda = L * V* = L<sup>2</sup> * V 
*   **智能内容–**确定程序中呈现(陈述)的智能量此参数提供了程序复杂性的度量，与实现它的程序语言无关。
    进出口
*   **Programming Time –** Shows time (in minutes) needed to translate the existing algorithm into implementation in the specified program language. 
    T = E / (f * S) 

    心理学家约翰·斯特劳德(John Stroud)提出的人脑处理速度的概念也被使用。斯托德把一个时刻定义为人脑完成最基本的决定所需的时间。因此，斯塔德数 S 是斯塔德每秒的力矩:5 < = S < = 20。霍尔斯特德使用 18。S 的值是从心理推理经验发展而来的，它对编程应用的推荐值是 18。

    斯特劳德数 S = 18 矩/秒

    秒到分钟因子 f = 60

### C 语言的计数规则–

1.  不考虑评论。
2.  不考虑标识符和函数声明
3.  所有的变量和常量都被认为是操作数。
4.  在同一程序的不同模块中使用的全局变量被视为同一变量的多次出现。
5.  不同函数中同名的局部变量被视为唯一操作数。
6.  函数调用被视为运算符。
7.  所有循环语句，例如 do {…} while()，while ( ) {…}，for ( ) {…}，所有控制语句，例如 if ( ) {…}，if ( ) {…} else {…}，等等。被视为运算符。
8.  在 control construct switch(){ case:…}中，switch 和所有 case 语句都被视为运算符。
9.  保留字如 return、default、continue、break、sizeof 等。，被认为是运算符。
10.  所有括号、逗号和终止符都被视为运算符。
11.  GOTO 被计为运算符，标签被计为操作数。
12.  一元和二元出现的“+”和“-”是分开处理的。类似地，“*”(乘法运算符)单独处理。
13.  在数组中，“数组名[索引]”“数组名”和“索引”等变量被视为操作数，而[ ]被视为运算符。
14.  在“结构名、成员名”或“结构名->成员名”等结构变量中，结构名、成员名作为操作数和“.”、“->”作为运算符。不同结构变量中成员元素的某些名称被视为唯一操作数。
15.  所有散列指令都被忽略。

**示例–**列出运算符和操作数，并计算软件科学度量的值，如

```
int sort (int x[ ], int n)

{
    int i, j, save, im1;
    /*This function sorts array x in ascending order */
    If (n< 2) return 1;
    for (i=2; i< =n; i++)
    {
        im1=i-1;
        for (j=1; j< =im1; j++)
            if (x[i] < x[j])
            {
                Save = x[i];
                x[i] = x[j];
                x[j] = save;
            }
    }
    return 0;
}

```

**解释–**

<figure class="table">

| 经营者 | 发生的事 | 操作数 | 发生的事 |
| （同 Internationalorganizations）国际组织 | four | 分类 | one |
| () | five | x | seven |
| , | four | n | three |
| [] | seven | 我 | eight |
| 如果 | Two | j | seven |
| < | Two | 救援 | three |
| ； | Eleven | im1 | three |
| 为 | Two | Two | Two |
| = | six | one | three |
| – | one | Zero | one |
| <= | Two | – | – |
| ++ | Two | – | – |
| 返回 | Two | – | – |
| {} | three | – | – |
| n1=14 | N1=53 | n2=10 | N2=38 |

```
Therefore,
N = 91
n = 24
V = 417.23 bits
N^ = 86.51
n2* = 3 (x:array holding integer 
to be sorted. This is used both
as input and output)
V* = 11.6
L = 0.027
D = 37.03
L^ = 0.038
T = 610 seconds

```

### **霍尔斯特德指标的优势:**

*   计算起来很简单。
*   它衡量节目的整体质量。
*   它预测误差率。
*   它预测维护工作量。
*   它不需要对编程结构进行全面分析。
*   它在计划和报告项目时非常有用。
*   它可以用于任何编程语言。

### 霍尔斯特德指标的缺点:

*   这取决于完整的代码。
*   它作为一个预测估计模型没有用。

**参考–**
[霍尔斯特德复杂度测量–](https://en.wikipedia.org/wiki/Halstead_complexity_measures)
维基百科[ristanase](https://www.ristancase.com/html/dac/manual/2.12.01-Software-Metrics-Classification.html)

本文由 [**希瓦尼·维马尼**](https://auth.geeksforgeeks.org/profile.php?user=Shivani Virmani) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。

</figure>