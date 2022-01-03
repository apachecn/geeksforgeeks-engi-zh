# 区分软件工程中的 LOC 和功能点

> 原文:[https://www . geesforgeks . org/区分锁定和功能点软件工程/](https://www.geeksforgeeks.org/differentiate-between-loc-and-function-point-in-software-engineering/)

**1。代码行(LOC):**
**代码行** (LOC)度量是代码中任何不是注释或空行的文本行，在任何情况下都是该行中语句或语句片段的数量。LOC 显然由包含程序头文件、任何变量的声明以及可执行和不可执行语句的所有行组成。由于代码行(LOC)只计算代码的比例，您只能利用它来比较或评估使用相同语言和使用相同编码标准编程的项目。

**代码行示例:**

## C++

```
void selSort(int x[], int n) {
  //Below function sorts an array in ascending order 
   int i, j, min, temp;
   for (i = 0; i < n - 1; i++) {
      min = i;
      for (j = i + 1; j < n; j++)
      if (x[j] < x[min])
      min = j;
      temp = x[i];
      x[i] = x[min];
      x[min] = temp;
   }
}
```

所以，现在，如果 LOC 只是行数，那么上面显示的函数包含 13 行代码(LOC)。但是当忽略注释和空行时，上面显示的函数包含 12 行代码(LOC)。

**2。功能点(FP) :**
在**功能点**度量中，软件支持的功能数量和类型用于查找 FPC(功能点计数)。

**功能点示例:**
查看本文获取详细示例: [**功能点(FP)的计算**](https://www.geeksforgeeks.org/software-engineering-calculation-of-function-point-fp/)
功能点和 LOC 都是软件大小的度量单位。依赖于开发的软件的规模是必要的，以便对项目的工作量、成本和持续时间做出准确的估计。大多数参数估计模型，如建设成本模型(COCOMO)接受以计划生育或劳动力成本为输入的规模。

**LOC 与功能点的区别:**

<figure class="table">

| **功能点(FP)** | **代码行** |
| 功能点度量是基于规范的。 | LOC 度量基于类比。 |
| 功能点度量与语言无关。 | LOC 度量取决于语言。 |
| 功能点指标是面向用户的。 | LOC 度量是面向设计的。 |
| 功能点度量可扩展到代码行。 | 它可以改变为 FP(即逆火) |
| 功能点用于数据处理系统 | LOC 用于计算计算机程序的大小 |
| 功能点可用于描述项目时间 | LOC 用于计算和比较程序员的生产力。 |

一般来说，人们更喜欢用功能点来表示软件的功能大小，这是因为一个非常重要的原因，即使用功能点度量来表示的大小在任何情况下都保持不变，并且无论使用哪种语言。

</figure>