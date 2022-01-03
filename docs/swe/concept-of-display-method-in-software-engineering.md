# 软件工程中显示方法的概念

> 原文:[https://www . geesforgeks . org/软件工程中的显示方法概念/](https://www.geeksforgeeks.org/concept-of-display-method-in-software-engineering/)

显示方法基本上是软件检查过程中使用的主要的和重要的方法，仅仅是为了确保和确认代码的正确性以及验证形式模型。

在这种方法中，显示是精确的文档，即，精确和正确的文档，其中程序简单地以这样的方式呈现，即它的正确性可以被确定和识别，而不检查任何其他显示。显示器通常由以下三部分组成:

*   **P1 :**
    代表此显示中显示的程序规格。
*   **P2 :**
    代表节目本身。程序名称可能会出现在此文本中，因此我们可以说所有这些程序都在此显示中被调用。

*   **P3 :**
    Represents specification of all programs that are invoked in P2 but are now known. A known program is a program that does not even require any specification. Semantic of known programs are simply considered to be easily understood. Therefore, each and every project should contain a list of programs that are assumed to be known.

    **展示方式概念:**

    1.  **Lexicon–**
        Lexicon 基本上是一个字典，包含任何数学函数、类型、程序常数等的几种定义。需要并在多个显示器中使用。
    2.  **索引–**
        索引基本上是一个包含所有变量和程序的列表，指示所有这些项目在显示中的位置。如果有些名字有一个以上的含义，那么我们也解释每个名字的类别。
    3.  **完整性和正确性–**
        每个显示可能会在不参考其他显示的情况下进行审查。它的正确性也可以被验证，甚至不用看在那个显示中调用的程序的实现，或者程序调用它描述的程序。
    4.  **正确性–**
        如果 P2 的程序将完全满足 P1 给出的规范，只要在 P2 调用的程序完全满足 P3 给出的规范，则显示被认为是正确的。
    5.  **Completeness –**
        A set of displays is considered to be complete if, for each specification of a program that is present and found in P3 of a display, there exits another display in which this specification is found in P1\. A set of displays is correct only if set of displays is complete and all displays are correct.

        **数学符号和数学方法在显示方法中的作用:**
        显示方法一般基于程序的数学模型。它使用一些数学符号只是为了提供一个准确和正确的程序描述。在软件工程中，数学方法的使用更侧重于程序开发或程序验证。

        符号在文档中非常重要。文件通常由不同领域的专家阅读，必须以简单易懂的方式理解。因此，在设计符号时，我们应该运用“分治”的原则。

        **表格和表格符号的作用:**
        表格符号通常会降低表达的复杂性。它通过以下三种方式降低复杂性:

        *   表通常解析表达式，即分解表达式，使读者容易理解。
        *   表格还消除了可能出现在列标题中的子表达式的许多重复。
        *   表中的每个条目仅适用于函数域的一小部分，因此可以简化该条目中的表达式。

        **优势:**

        *   当程序非常长时，使程序文档更加有用
        *   将一个程序简单地表示为一组显示以及每个显示可以在不查看任何其他显示的情况下被检查和验证的属性。
        *   用于保证代码的正确性。