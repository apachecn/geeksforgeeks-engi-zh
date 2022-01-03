# 逆向工程中的抽象层次

> 原文:[https://www . geeksforgeeks . org/逆向工程中的抽象层次/](https://www.geeksforgeeks.org/abstraction-levels-in-reverse-engineering/)

[逆向工程](https://www.geeksforgeeks.org/software-engineering-reverse-engineering/)拥有广泛的任务，可以帮助理解和修改软件系统。其主要目的是从系统中识别和恢复程序需求和设计需求信息。

抽象是忽略某些细节的过程，以便简化问题，并促进系统的规范、设计和实现以逐步的方式进行。在软件维护中，定义了以下三个层次的逆向工程抽象:实现抽象、设计抽象、规范抽象。

1.  **Implementation abstraction –**
    Implementation abstraction is a lowest level of abstraction and at this level the abstraction of the knowledge of the language in which the system is written, the syntax and semantics of language and the hierarchy of system components rather than data structures and algorithms is abstracted.

2.  **Design abstraction –**
    Design abstraction is the intermediary level of abstraction. This level abstracts how the components are related and control to each other.
3.  **Specification abstraction –**
    Specification abstraction abstracts the functions by replacing its algorithmic nature with concepts and specific to the application requirements.

    逆向工程需要检测低级别的实现，并用它们的高级别对应物替换它们。结果，该过程最终转变为程序整体架构的增量形成。

然而，逆向工程中的高级对应并不一定意味着具有更高抽象层次的产品。如果最终产品的抽象级别与原始系统处于同一级别，该操作通常被称为“重新文档化”。
另一方面，如果生成的产品处于更高的抽象层次，则该操作被称为“设计恢复”或“特定恢复”。

1.  **Redocumentation –**
    Re-documentation is the recreation of a sound mathematical or logical structure precise to its requirements using a specification language(set of notations defining the behavior of the system) within the same relative abstraction level that is equivalent to the representation of the original system.

    该流程有 3 个目的/任务–

    *   **(一)。**通过使用来自源代码的数据流或控制流图创建系统的交替视图，加强对产品的理解。
    *   **(二)。**随着变更的进行，并排更新系统文档。
    *   **(三)。**完成新修改系统的文档，以便将来对系统进行维护。
2.  **设计恢复–**
    设计恢复包括对系统的领域知识、外部数据和演绎，以识别和提取除了通过检查系统本身直接获得的抽象之外的有意义的更高级抽象。它将系统从低层次的抽象带到更高层次的抽象。
    设计恢复从代码、现有设计文档(如果存在)、个人经验以及关于问题和应用领域的知识的组合中重新创建抽象。作为恢复设计的新设计可以通过形成未来系统修改的基线来用于系统的重新开发。

    不同的方法，不同的侧重点，可以用来恢复这些设计。
    例如，在恢复单词搜索应用程序的设计后，它可以用于新单词编辑应用程序中单词搜索模块的设计。