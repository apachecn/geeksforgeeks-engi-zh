# 扩展功能点(EFP)指标

> 原文:[https://www . geesforgeks . org/extended-function-point-EFP-metrics/](https://www.geeksforgeeks.org/extended-function-point-efp-metrics/)

[功能点(FP)](https://www.geeksforgeeks.org/software-engineering-functional-point-fp-analysis/) 测量对于许多工程和嵌入式系统来说是不够的。为了克服这一点，已经提出了对基本功能点度量的许多扩展。这些措施如下:

**Feature Points:**

*   通过计算信息域值来计算特征点。*   它可以用在那些复杂程度比较高的领域。*   功能点度量是特征点的子集。*   But both the Function point and feature point represents the functionality of the systems

    **特征点计算表:**

    <center>

    | -你好。不，不。 | 测量参数 | 数数 | ** | 权重因数 |
    | --- | --- | --- | --- | --- |
    | one | 外部输入数量 | – | * | four |
    | Two | 外部产出数量 | – | * | five |
    | three | 外部查询数量 | – | * | four |
    | four | 内部文件数量(ILF) | – | * | seven |
    | five | 外部接口数量(EIF) | – | * | seven |
    | six | 使用的算法总数 | – | * | three |

    **3D 功能点:**

    *   数据、功能和控制是由 3D 功能点表示的三个维度。
        1.  **数据:**用户界面和数据与原方法相同。
        2.  **控制:**实时行为
        3.  **功能:**内部处理
    *   数据维度计算与 FPs 相同。特征转换是在功能维度中完成的。在控制尺寸中，添加了特征-过渡。
    *   三维功能点法是波音公司提出的。
    *   它旨在用阿尔布雷特方法解决两个问题。

    **示例:**
    计算具有以下特征的嵌入式系统的 FP、特征点和 3D 功能点值:

    ```
    1\. Internal data structures = 8
    2\. No. of user inputs = 32
    3\. No. of user outputs = 60
    4\. No. of user inquiries = 24
    5\. No. of external interfaces = 2
    6\. No. of transformation = 23
    7\. No. of transition = 32 
    ```

    假设上述计数的复杂性是平均情况= 3。

    **说明:**

    **第一步:**我们先画出计算 FPs 的表格。

    <center>

    | -你好。不，不。 | 测量参数 | 数数 | ** | 简单加权因子 | 平均加权因子 | 复数加权因子 | 计算值 |
    | --- | --- | --- | --- | --- | --- | --- | --- |
    | one | 外部输入数量 | Thirty-two | * | three | four | six | One hundred and twenty-eight |
    | Two | 外部产出数量 | Sixty | * | four | five | seven | Three hundred |
    | three | 外部查询数量 | Twenty-four | * | three | four | six | Ninety-six |
    | four | 内部文件数量(ILF) | eight | * | seven | Ten | Fifteen | Eighty |
    | five | 外部接口数量(EIF) | Two | * | five | seven | Ten | Fourteen |
    | six | 转换次数 | Twenty-three | * |  |  |  | Twenty-three |
    | seven | 过渡次数 | Thirty-two | * |  |  |  | Thirty-two |
    |  | 计数-总计 |  |  | —–> |  |  | Six hundred and seventy-three |

    </center>

    **步骤-2:** 求所有 fi 的和(1 到 14)

    ```
    Σ(&fi) = 14 * 3 = 42 
    ```

    **第三步:**计算功能点:

    ```
    FP = Count-total * [0.65 + 0.01 *Σ(&fi) ]
    = 618 * [0.65 + 0.01 * 42]
    = 618 * [0.65 + 0.42]
    = 618 * 1.07 
    = 661.26 
    ```

    **第 4 步:**计算特征点:

    ```
    = (32 *4 + 60 * 5 + 24 * 4 + 80 +14) * 1.07 + {12 * 15 *1.07} 
    = 853.86 
    ```

    **步骤-5:** 计算 3D 功能点，通过计算总的计算值来计算。所以，对于 3D 功能点，需要的索引是 673。

    </center>