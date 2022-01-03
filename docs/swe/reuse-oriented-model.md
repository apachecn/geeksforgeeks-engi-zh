# 面向重用的模型

> 原文:[https://www.geeksforgeeks.org/reuse-oriented-model/](https://www.geeksforgeeks.org/reuse-oriented-model/)

**面向重用的模型(ROM)** ，也称为面向重用的开发(ROD)，它可以是特定持续时间内软件开发的步骤，其中通过创建一系列被称为模型的原型来重新设计软件，每个系统都是从前一个系统派生而来的，具有一系列恒定的定义规则。

面向重用的模型在它的纯形式中并不总是明智的，因为一整套可重用的添加剂可能不可用。在这种情况下，需要设计几个新的系统组件。如果不这样做，只读存储器就不得不在感知需求上妥协，导致产品不能满足用户的确切需求。这种模式依赖于这样一种认识，即维护可能被视为一种消遣，涉及现有系统组件的重用。

复用模型有 4 个**基本步骤**，依次为:

1.  Identify the components in the old system that are most suitable for reuse.
2.  Understand all system components.
3.  Modify the old system components to meet the new requirements.
4.  Integrate all modified parts into the new system.

组件分类需要特定的框架，因此需要修改。完整的重用版本可以从存在周期的任何部分开始——需求、规划、编码、设计或分析数据——而不像其他模型。

**优势:**

*   The total cost of software development can be reduce.
*   The risk factor is very low.
*   Can save a lot of time and energy.
*   Essentially, it is very efficient.

**缺点:**

*   Reuse-oriented models do not always work as practices in their true forms.
*   Compromise of requirements may cause the system to fail to meet the needs of users.
*   Sometimes the old system components are used, that is, they are incompatible with the new version components, which may lead to the influence on the system evolution.