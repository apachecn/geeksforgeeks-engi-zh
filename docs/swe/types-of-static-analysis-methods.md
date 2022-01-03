# 静态分析方法的类型

> 原文:[https://www . geesforgeks . org/type-of-static-analysis-methods/](https://www.geeksforgeeks.org/types-of-static-analysis-methods/)

**软件的静态分析:**
静态分析涉及一组用于分析软件源代码或目标代码的方法，以确定软件如何运行，并建立检查其正确性的标准。静态分析研究源代码而不执行它，并揭示各种各样的信息，如所用模型的结构、数据和控制流、语法准确性等。

静态分析方法有几种类型-

1.  **Control Analysis :-**
    This software focuses on examining the controls used in calling structure, control flow analysis and state transition analysis. The calling structure is related to the model by identifying the calling and call structure. The calling structure can be a process, subroutine, function, or method. Control flow analysis checks the sequence of control transfers. Furthermore, it inefficient constructions in the model. A graph of the model is created in which the conditional branches and model junctions are represented by nodes.

2.  **Data Analysis :-**
    Ensures proper operation is applied to data objects such as data structures and linked lists. In addition, this method also ensures that the defined data is used properly. Data analysis involves two methods, namely, data dependency and data-flow analysis. Data dependency is necessary to assess the accuracy of synchronization across multiple processors. Data flow analysis checks the definition and context of variables.
3.  **Fault/Failure Analysis :-**
    It analyzes faults (incorrectly component) and failure (incorrect behavior of model component) in the model. This method uses the input-output transformation description to identify the conditions that are cause for the failure. To determine the failures in certain conditions the model design specification is checked.
4.  **界面分析:-**
    该软件通过验证和验证交互和分发模拟来检查代码。界面分析有两种基本技术，用户界面分析检查子模型界面并确定界面结构的准确性。用户界面分析检查用户界面模型，以及在用户与模型交互期间为防止错误而采取的预防措施。该方法还关注界面如何准确地集成到整体模型和仿真中。