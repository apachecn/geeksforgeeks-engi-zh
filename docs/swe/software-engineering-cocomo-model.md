# 软件工程| COCOMO 模型

> 原文:[https://www . geesforgeks . org/software-engineering-cocomo-model/](https://www.geeksforgeeks.org/software-engineering-cocomo-model/)

Cocomo(建设性成本模型)是基于 LOC 的回归模型，即**代码行数**。它是软件项目的程序性成本估算模型，经常被用作可靠地预测与制定项目相关的各种参数(如规模、工作量、成本、时间和质量)的过程。它是由巴里·博姆在 1970 年提出的，基于对 63 个项目的研究，这使它成为记录最完整的模型之一。

定义任何软件产品质量的关键参数也是 Cocomo 的结果，主要是工作和进度:

*   **努力程度:**完成一项任务所需的劳动量。它以人月为单位。
*   **时间表:**简单来说就是完成工作所需的时间，当然，这与付出的努力成正比。它是以时间单位来衡量的，如周、月。

已经提出了不同的 Cocomo 模型来根据所需的准确性和正确性预测不同级别的成本估算。所有这些模型都可以应用于各种项目，这些项目的特性决定了后续计算中使用的常量值。这些属于不同系统类型的特征将在下面提到。

Boehm 对有机、半独立和嵌入式系统的定义:

1.  **Organic–**如果所需的团队规模足够小，问题被很好地理解并在过去得到解决，并且团队成员对问题有名义上的经验，那么软件项目就被称为有机类型。
2.  **半分离–**如果一个软件项目的重要特征(如团队规模、经验、对各种编程环境的了解)介于有机和嵌入式之间，则称其为半分离类型。与有机项目相比，被归类为半分离的项目相对不那么熟悉，也更难开发，需要更多的经验、更好的指导和创造力。编译器或不同的嵌入式系统可以被认为是半分离型的。
3.  **Embedded –** A software project with requiring the highest level of complexity, creativity, and experience requirement fall under this category. Such software requires a larger team size than the other two models and also the developers need to be sufficiently experienced and creative to develop such complex models.

    所有上述系统类型都利用了工作计算中使用的不同常量值。

    **模型的类型:** COCOMO 由三种越来越详细和精确的形式组成的层次结构组成。根据我们的要求，可以采用三种形式中的任何一种。这些是 COCOMO 模型的类型:

    1.  基本 COCOMO 模型
    2.  中级 COCOMO 模型
    3.  详细的 COCOMO 模型

    第一级，**基础 COCOMO** 可用于软件成本的快速和稍微粗略的计算。由于缺乏足够的因素考虑，其准确性受到一定限制。

    **中级 COCOMO** 将这些成本动因考虑在内，**详细 COCOMO** 还考虑了单个项目阶段的影响，即在详细的情况下，它同时考虑了这些成本动因，并且计算也是分阶段进行的，从而产生更准确的结果。下面将进一步讨论这两个模型。

    **工作量估算:计算–**

    1.  **Basic Model –**

        上述公式用于基本 COCOMO 模型的成本估算，也用于后续模型。不同系统类别的基本模型的常数值 a、b、c 和 d:

        | 软件项目 | a | b | c | d |
        | --- | --- | --- | --- | --- |
        | 有机的 | Two point four | One point zero five | Two point five | Zero point three eight |
        | 半分离的 | Three | One point one two | Two point five | Zero point three five |
        | 植入的 | Three point six | One point two | Two point five | Zero point three two |

        工作量是以人-月来衡量的，从公式中可以明显看出，它依赖于千行代码。
        发育时间以月为单位。

        这些公式同样用于基本模型计算中，因为不太考虑不同的因素，如可靠性、专业知识，因此估算是粗略的。

        下面是基本 COCOMO 的 C++程序

        ```
        // C++ program to implement basic COCOMO
        #include<bits/stdc++.h>
        using namespace std;

        // Function for rounding off float to int
        int fround(float x)
        {
            int a;
            x=x+0.5;
            a=x;
            return(a);
        }

        // Function to calculate parameters of Basic COCOMO
        void calculate(float table[][4], int n,char mode[][15], int size)
        {
            float effort,time,staff;

            int model;

            // Check the mode according to size

            if(size>=2 && size<=50)
                model=0;        //organic

            else if(size>50 && size<=300)
                model=1;        //semi-detached

            else if(size>300)
                model=2;        //embedded

            cout<<"The mode is "<<mode[model];

            // Calculate Effort
            effort = table[model][0]*pow(size,table[model][1]);

            // Calculate Time
            time = table[model][2]*pow(effort,table[model][3]);

            //Calculate Persons Required
            staff = effort/time;

            // Output the values calculated
            cout<<"\nEffort = "<<effort<<" Person-Month";

            cout<<"\nDevelopment Time = "<<time<<" Months";

            cout<<"\nAverage Staff Required = "<<fround(staff)<<" Persons";

        }

        int main()
        {
            float table[3][4]={2.4,1.05,2.5,0.38,3.0,1.12,2.5,0.35,3.6,1.20,2.5,0.32};

            char mode[][15]={"Organic","Semi-Detached","Embedded"};

            int size = 4;

            calculate(table,3,mode,size);

            return 0;
        }
        ```

        **Output:**

        ```
        The mode is Organic
        Effort = 10.289 Person-Month
        Development Time = 6.06237 Months
        Average Staff Required = 2 Persons

        ```

    2.  **Intermediate Model –**

        基本的 Cocomo 模型假设工作量只是代码行数和根据不同软件系统评估的一些常数的函数。然而，在现实中，没有一个系统的努力和进度可以仅仅基于代码行来计算。为此，各种其他因素，如可靠性、经验、能力。这些因素被称为成本动因，中间模型利用 15 个这样的动因进行成本估算。

        成本动因的分类及其属性:

        **(一)产品属性–**

        *   所需的软件可靠性范围
        *   应用程序数据库的大小
        *   产品的复杂性

        **(二)硬件属性–**

        *   运行时性能限制
        *   内存限制
        *   虚拟机环境的不稳定性
        *   所需周转时间

        **(三)人员属性–**

        *   分析师能力
        *   软件工程能力
        *   应用体验
        *   虚拟机体验
        *   编程语言经验

        **(iv)项目属性–**

        *   软件工具的使用
        *   软件工程方法的应用
        *   所需的开发时间表

        | 成本动因 | 极低 | 低的 | Nominal

        ；

         | 高的 | 非常高 |
        | --- | --- | --- | --- | --- | --- |
        | **产品属性** |  |  |  |  |  |
        | 所需的软件可靠性 | Zero point seven five | Zero point eight eight | One | One point one five | One point four |
        | 应用程序数据库的大小 |  | Zero point nine four | One | One point zero eight | One point one six |
        | 产品的复杂性 | Zero point seven | Zero point eight five | One | One point one five | One point three |
        | **硬件属性** |  |  |  |  |  |
        | 运行时性能约束 |  |  | One | One point one one | One point three |
        | 内存限制 |  |  | One | One point zero six | One point two one |
        | 虚拟机环境的不稳定性 |  | Zero point eight seven | One | One point one five | One point three |
        | 所需周转时间 |  | Zero point nine four | One | One point zero seven | One point one five |
        | **人员属性** |  |  |  |  |  |
        | 分析师能力 | One point four six | One point one nine | One | Zero point eight six | Zero point seven one |
        | 应用体验 | One point two nine | One point one three | One | Zero point nine one | Zero point eight two |
        | 软件工程师能力 | One point four two | One point one seven | One | Zero point eight six | Zero point seven |
        | 虚拟机体验 | One point two one | One point one | One | Zero point nine |  |
        | 编程语言经验 | One point one four | One point zero seven | One | Zero point nine five |  |
        | **项目属性** |  |  |  |  |  |
        | 软件工程方法的应用 | One point two four | One point one | One | Zero point nine one | Zero point eight two |
        | 软件工具的使用 | One point two four | One point one | One | Zero point nine one | Zero point eight three |
        | 所需的开发时间表 | One point two three | One point zero eight | One | One point zero four | One point one |

        项目经理要对一个特定项目的这 15 个不同参数进行 1 到 3 级的评分。然后，根据这些评级，从上表中获取适当的成本动因值。然后将这 15 个值相乘来计算 EAF(努力调整系数)。中间 COCOMO 公式现在采用以下形式:

        对于中间模型，a 和 b 的值如下:

        | 软件项目 | a | b |
        | --- | --- | --- |
        | 有机的 | Three point two | One point zero five |
        | 半分离的 | Three | One point one two |
        | 植入的 | Two point eight | One point two |

    3.  **Detailed Model –**
        Detailed COCOMO incorporates all characteristics of the intermediate version with an assessment of the cost driver’s impact on each step of the software engineering process. The detailed model uses different effort multipliers for each cost driver attribute. In detailed cocomo, the whole software is divided into different modules and then we apply COCOMO in different modules to estimate effort and then sum the effort.

        详细 COCOMO 的六个阶段是:

        1.  规划和要求
        2.  系统设计
        3.  详细设计
        4.  模块代码和测试
        5.  集成和测试
        6.  成本构成模型

        工作量是作为程序规模的函数来计算的，并且根据软件生命周期的每个阶段给出了一组成本驱动因素。

另阅读:[经典瀑布模型](https://www.geeksforgeeks.org/software-engineering-classical-waterfall-model/)[迭代瀑布模型](https://www.geeksforgeeks.org/software-engineering-iterative-waterfall-model/)[原型模型](https://www.geeksforgeeks.org/software-engineering-prototyping-model/)[螺旋模型](https://www.geeksforgeeks.org/software-engineering-spiral-model/)