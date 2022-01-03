# 软件工程|调试方法

> 原文:[https://www . geesforgeks . org/software-engineering-debug-approws/](https://www.geeksforgeeks.org/software-engineering-debugging-approaches/)

**调试** **:**
调试是发现并解决计算机程序中妨碍计算机软件或系统正确运行的缺陷或问题的过程。

**调试需要:**
一旦在程序代码中知道了错误，就需要首先建立对错误负责的精确的程序语句，从而修复它们。

**调试挑战:**

在代理调试的同时也有很多问题。这些是:

*   调试是通过开发软件程序的个人来完成的，这个人很难承认出错了。
*   调试通常在巨大的压力下进行，以尽快修复支持的错误。
*   很难准确再现输入条件。
*   与替代性软件程序改进活动相比，在调试过程中，研究、文献和正式准备相对较少。

**调试方法:**
下面是程序员普遍采用的一些调试方法。

*   **Brute Force Method:** 
    This is the foremost common technique of debugging however is that the least economical method. during this approach, the program is loaded with print statements to print the intermediate values with the hope that a number of the written values can facilitate to spot the statement in error. This approach becomes a lot of systematic with the utilisation of a symbolic program (also known as a source code debugger), as a result of values of various variables will be simply checked and breakpoints and watch-points can be easily set to check the values of variables effortlessly. 
*   **Backtracking:** 
    This is additionally a reasonably common approach. during this approach, starting from the statement at which an error symptom has been discovered, the source code is derived backward till the error is discovered. sadly, because the variety of supply lines to be derived back will increase, the quantity of potential backward methods will increase and should become unimaginably large so limiting the utilisation of this approach. 
*   **Cause Elimination Method:** 
    In this approach, a listing of causes that may presumably have contributed to the error symptom is developed and tests are conducted to eliminate every error. A connected technique of identification of the error from the error symptom is that the package fault tree analysis. 
*   **Program Slicing:** 
    This technique is analogous to backtracking. Here the search house is reduced by process slices. A slice of a program for a specific variable at a particular statement is that the set of supply lines preceding this statement which will influence the worth of that variable 

**调试指南:**
调试通常由支持其独创性的程序员管理。以下是一些有效调试的一般技巧:

*   很多时候调试需要对程序风格有深入的了解。试图纠正对系统风格和实现的部分理解可能需要过多的精力来调试甚至是简单的问题。

*   调试通常甚至需要系统的完整计划。在这种情况下，新手程序员通常会犯的一个典型错误是试图不修复错误，不管它的症状如何。

*   人们应该注意滑动修正引入新误差的可能性。因此，当每个球的误差修正，回归测试应该被管理。