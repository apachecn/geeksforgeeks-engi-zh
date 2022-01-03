# 软件工程|需求验证技术

> 原文:[https://www . geesforgeks . org/software-engineering-requirements-validation-technologies/](https://www.geeksforgeeks.org/software-engineering-requirements-validation-techniques/)

**需求验证**是检查为开发定义的需求，定义客户真正想要的系统的过程。为了检查与需求相关的问题，我们执行需求验证。我们通常在开发的初始阶段使用需求验证来检查错误，因为在开发过程的后期检测到错误时，错误可能会增加过多的返工。

在需求验证过程中，我们执行不同类型的测试来检查[软件需求规范(SRS)](https://www.geeksforgeeks.org/software-engineering-quality-characteristics-of-a-good-srs/) 中提到的需求，这些检查包括:

*   完整性检查
*   一致性检查
*   有效性检查
*   真实性检查
*   双重有罪支票
*   可验证性

需求验证的输出是问题列表和对检测到的问题的一致行动。问题列表表明在需求验证过程中检测到的问题。商定措施的列表说明了应采取的纠正措施，以解决检测到的问题。

有几种技术可单独使用或与其他技术结合使用，以检查整个或部分系统:

1.  **测试用例生成:**
    SRS 文档中提到的需求应该是可测试的，所进行的测试揭示了需求中存在的错误。一般认为，如果测试很难或不可能设计，这通常意味着要求将很难实现，应该重新考虑。
2.  **原型制作:**
    在这种验证技术中，系统的原型呈现在最终用户或客户面前，他们用呈现的模型进行实验，并检查它是否满足他们的需求。这种类型的模型通常用于收集关于用户需求的反馈。
3.  **需求评审:**
    在这种方法中，SRS 由一组人员仔细评审，包括来自承包商组织和客户方的人员，评审者系统地分析文档以检查错误和模糊性。
4.  **Automated Consistency Analysis:**
    This approach is used for automatic detection of an error, such as nondeterminism, missing cases, a type error, and circular definitions, in requirements specifications.

    首先，用正式的符号来构造需求，然后使用 CASE 工具来检查系统的一致性，识别所有不一致的报告并采取纠正措施。

5.  **演练:**
    演练没有正式定义的过程，也不需要区分角色分配。
    *   尽早检查这个想法是否可行。
    *   获取他人的意见和建议。
    *   检查他人的认可并达成一致。