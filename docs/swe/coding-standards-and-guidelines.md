# 编码标准和指南

> 原文:[https://www . geesforgeks . org/coding-standards-and-guidelines/](https://www.geeksforgeeks.org/coding-standards-and-guidelines/)

设计文档中指定的不同模块在编码阶段根据模块规范进行编码。编码阶段的主要目标是通过高级语言从设计阶段后准备的设计文档中编码，然后对该代码进行单元测试。

好的软件开发组织希望他们的程序员保持某种定义明确的标准编码风格，称为编码标准。他们通常根据什么最适合他们的组织并基于他们开发的软件类型来制定自己的编码标准和指导方针。对于程序员来说，维护编码标准是非常重要的，否则代码将在代码审查过程中被拒绝。

**拥有编码标准的目的:**

*   编码标准为不同工程师编写的代码提供了统一的外观。
*   它提高了代码的可读性和可维护性，也降低了复杂性。
*   它有助于代码重用，并有助于轻松检测错误。
*   它促进了良好的编程实践，提高了程序员的效率。

下面给出了一些编码标准:

1.  **Limited use of globals:**
    These rules tell about which types of data that can be declared global and the data that can’t be.
2.  **Standard headers for different modules:**
    For better understanding and maintenance of the code, the header of different modules should follow some standard format and information. The header format must contain below things that is being used in various companies:
    *   模块的名称
    *   模块创建日期
    *   模块作者
    *   修改历史
    *   关于模块功能的模块简介
    *   模块中支持的不同功能及其输入输出参数
    *   模块访问或修改的全局变量
3.  **Naming conventions for local variables, global variables, constants and functions:**
    Some of the naming conventions are given below:
    *   有意义和可理解的变量名称有助于任何人理解使用它的原因。
    *   局部变量应使用以小写字母开头的驼色字母命名(例如 **localData** )，而全局变量名称应以大写字母开头(例如 **GlobalData** )。常量名称只能使用大写字母(例如 **CONSDATA** )。
    *   最好避免在变量名中使用数字。
    *   函数的名称应该用小字母开头的 camel 大小写。
    *   函数的名称必须清晰、简洁地描述使用函数的原因。
4.  **Indentation:**
    Proper indentation is very important to increase the readability of the code. For making the code readable, programmers should use White spaces properly. Some of the spacing conventions are given below:
    *   两个函数参数之间的逗号后面必须有一个空格。
    *   每个嵌套块应该适当缩进和隔开。
    *   程序中每个块的开头和结尾都应该有适当的缩进。
    *   所有大括号都应该从新的一行开始，大括号后面的代码也应该从新的一行开始。

5.  **Error return values and exception handling conventions:**
    All functions that encountering an error condition should either return a 0 or 1 for simplifying the debugging.

    另一方面，编码指南给出了一些关于编码风格的一般性建议，为了提高代码的可理解性和可读性，应该遵循这些建议。下面给出了一些编码指南:

6.  **Avoid using a coding style that is too difficult to understand:**
    Code should be easily understandable. The complex code makes maintenance and debugging difficult and expensive.
7.  **Avoid using an identifier for multiple purposes:**
    Each variable should be given a descriptive and meaningful name indicating the reason behind using it. This is not possible if an identifier is used for multiple purposes and thus it can lead to confusion to the reader. Moreover, it leads to more difficulty during future enhancements.
8.  **Code should be well documented:**
    The code should be properly commented for understanding easily. Comments regarding the statements increase the understandability of the code.
9.  **Length of functions should not be very large:**
    Lengthy functions are very difficult to understand. That’s why functions should be small enough to carry out small work and lengthy functions should be broken into small ones for completing small tasks.
10.  **尽量不要使用 GOTO 语句:**
    GOTO 语句使程序非结构化，从而降低了程序的可理解性，调试也变得困难。

**编码指南的优势:**

*   编码准则提高了软件的效率，减少了开发时间。
*   编码指南有助于在早期阶段检测错误，因此有助于减少软件项目产生的额外成本。
*   如果正确维护了编码准则，那么软件代码就增加了可读性和可理解性，从而降低了代码的复杂性。
*   降低了软件开发的隐性成本。