# 软件工程|功能点(FP)计算

> 原文:[https://www . geesforgeks . org/software-engineering-计算功能点-fp/](https://www.geeksforgeeks.org/software-engineering-calculation-of-function-point-fp/)

[功能点(FP)](https://www.geeksforgeeks.org/software-engineering-functional-point-fp-analysis/) 是软件开发的一个要素，有助于在开发过程的早期估算开发成本。它可以从用户的角度来衡量功能。

**计数功能点(FP):**

*   **Step-1:**

    ```
    F = 14 * scale
    ```

    根据复杂度调整因子的特性，标度从 0 到 5 不等。下表显示了比例:

    ```
    0 - No Influence
    1 - Incidental
    2 - Moderate
    3 - Average
    4 - Significant
    5 - Essential 
    ```

*   **步骤 2:** 计算复杂度调整因子。

    ```
    CAF = 0.65 + ( 0.01 * F )
    ```

*   **Step-3:** Calculate Unadjusted Function Point (UFP).

    表格(必填)

    | 功能单元 | 低的 | 平均值 | 高的 |
    | --- | --- | --- | --- |
    | 不，不 | three | four | six |
    | 东正教(Easter Orthodox) | four | five | seven |
    | 情商 | three | four | six |
    | 感应损耗因数(inductive loss factor) | seven | Ten | Fifteen |
    | EIF | five | seven | Ten |

    将每个函数点乘以表中相应的值。

*   **第 4 步:**计算功能点。

    ```
    FP = UFP * CAF
    ```

**示例:**
给定以下值，计算所有复杂度调整因子(CAF)和加权因子取平均值时的功能点。

```
User Input = 50
User Output = 40
User Inquiries = 35
User Files = 6
External Interface = 4 
```

**说明:**

*   **步骤-1:** 由于复杂度调整因子是平均的(在问题中给出)，因此，

    ```
    scale = 3.
    F = 14 * 3 = 42 
    ```

*   **第二步:**

    ```
    CAF = 0.65 + ( 0.01 * 42 ) = 1.07 
    ```

*   **步骤 3:** 由于加权因子也是平均的(在问题中给出)，因此我们将把每个单独的功能点乘以表中相应的值。

    ```
    UFP = (50*4) + (40*5) + (35*4) + (6*10) + (4*7) = 628 
    ```

*   **Step-4:**

    ```
    Function Point = 628 * 1.07 = 671.96 
    ```

    这是必需的答案。

计算功能点的程序如下

```
#include <bits/stdc++.h>
using namespace std;

// Function to calculate Function Point
void calfp(int frates[][3], int fac_rate)
{

    // Function Units
    string funUnits[5] = {
        "External Inputs",
        "External Outputs",
        "External Inquiries",
        "Internal Logical Files",
        "External Interface Files"
    };

    // Weight Rates
    string wtRates[3] = { "Low", "Average", "High" };

    // Weight Factors
    int wtFactors[5][3] = {
        { 3, 4, 6 },
        { 4, 5, 7 },
        { 3, 4, 6 },
        { 7, 10, 15 },
        { 5, 7, 10 },
    };

    int UFP = 0;

    // Calculating UFP (Unadjusted Function Point)
    for (int i = 0; i < 5; i++) {

        for (int j = 0; j < 3; j++) {

            int freq = frates[i][j];

            UFP += freq * wtFactors[i][j];
        }
    }

    // 14 factors
    string aspects[14] = {
        "reliable backup and recovery required ?",
        "data communication required ?",
        "are there distributed processing functions ?",
        "is performance critical ?",
        "will the system run in an existing heavily utilized operational environment ?",
        "on line data entry required ?",
        "does the on line data entry require the input transaction to be built over multiple screens or operations ?",
        "are the master files updated on line ?",
        "is the inputs, outputs, files or inquiries complex ?",
        "is the internal processing complex ?",
        "is the code designed to be reusable ?",
        "are the conversion and installation included in the design ?",
        "is the system designed for multiple installations in different organizations ?",
        "is the application designed to facilitate change and ease of use by the user ?"
    };

    /*
    Rate Scale of Factors
    Rate the following aspects on a scale of 0-5 :-
    0 - No influence 
    1 - Incidental 
    2 - Moderate 
    3 - Average 
    4 - Significant 
    5 - Essential 
    */

    int sumF = 0;

    // Taking Input of factors rate
    for (int i = 0; i < 14; i++) {

        int rate = fac_rate;

        sumF += rate;
    }

    // Calculate CFP
    double CAF = 0.65 + 0.01 * sumF;

    // Calculate Function Point (FP)
    double FP = UFP * CAF;

    // Output Values
    cout << "Function Point Analysis :-" << endl;

    cout << "Unadjusted Function Points (UFP) : " << UFP << endl;

    cout << "Complexity Adjustment Factor (CAF) : " << CAF << endl;

    cout << "Function Points (FP) : " << FP << endl;
}

// driver function
int main()
{
    int frates[5][3] = {
        { 0, 50, 0 },
        { 0, 40, 0 },
        { 0, 35, 0 },
        { 0, 6, 0 },
        { 0, 4, 0 }
    };

    int fac_rate = 3;

    calfp(frates, fac_rate);

    return 0;
}
```

**Output:**

```
Function Point Analysis :-
Unadjusted Function Points (UFP) : 628
Complexity Adjustment Factor (CAF) : 1.07
Function Points (FP) : 671.96

```