# 软件维护和各种软件维护表

> 原文:[https://www . geesforgeks . org/软件-维护-和-各种-软件-维护-表/](https://www.geeksforgeeks.org/software-maintenance-and-various-software-maintenance-tables/)

[软件维护](https://www.geeksforgeeks.org/software-engineering-software-maintenance/)有两种正式定义，如下-

1.  **IEEE，1993 :-**
    软件维护是在交付后对软件产品进行修改，以纠正故障、提高性能或其他属性，或者使产品适应修改后的环境。
2.  **国际标准化组织/国际电工委员会标准 12207 :-**
    一组软件维护活动，当软件由于问题或需要改进或适应而对代码和相关文档进行修改时发生。

第一个定义类似于硬件维护、汽车维修，在这种情况下，产品会被检查是否有错误，或者在售出后会被赋予额外的任务。

相比之下，第二个定义将软件维护作为软件产品整个生命周期的一个重要方面，从早期开发开始。

**软件维护**指定软件系统初始工作版本交付后的活动。必须从一开始就在系统中进行维护，即在整个开发过程中应考虑维护。虽然维护没有软件生产最复杂的方面。

**维护**包括软件过程所有其他阶段的部分。收到维护请求后，第一步是确定需要什么类型的维护。有时候，问题出在用户身上，而不是软件。

就软件产品而言，人们更感兴趣的是更新产品，使其适应环境或硬件的变化，而不是减少产品，用另一种新产品取代它。因此，软件产品也需要维护，以保持它们与周围环境同步，从而实现最佳应用。

<center>**Problem Identification Phase**</center>

**Input:**Modification request.
**Process:**Assign change number, Classify modification request, Accept or reject change, Prioritize.
**Control:**Uniquely identified modification request, Enter modification request repository.
**Output:**Validated modification request, Validated process determinations.

* * *

<center>**Analysis Phase**</center>

**Input:**Project document, Repository information, Validated modification request.
**Process:**Feasibility analysis, Detailed analysis.
**Control:**Conduct technical review, Verify test strategy, Verify whether the documentation is updated or not, Identify security issues.
**Output:**Feasibility report, Detailed analysis report, Updated requirements, Preliminary modification list, Test strategy.

* * *

<center>**Design phase**</center>

**Input:**Project document, Source code, Databases, Analysis phase output.
**Process:**Create test cases, Revise requirements, Revise implementation plan.
**Control:**Software inspections/reviews, Verify design.
**Output:**Revised modification list, revised detailed analysis, Updated test plans.

* * *

<center>**Implementation Phase**</center>

**Input:**Source code, system documentation, Results of design phase.
**Process:**Software code, Unit test, Test preparation review.
**Control:**Software inspections/review.
**Output:**Updated software, Updated design documents, Updated test documents, Updated user documents, Test preparation review report.

* * *

<center>**System Test Phase**</center>

**Input:**Updated software documentation, Test preparation review report, Updated system.
**Process:**Functional test, Interface testing, Test preparation review
**Control:**Software code listings, Modification request, Test documentation.
**Output:**Test system, Test reports.

* * *

<center>**Acceptance Test Phase**</center>

**Input:**Test preparation review report, Fully integrated system, Acceptance test plans, Acceptance test cases, Acceptance test procedures.
**Process:**Acceptance test, Interoperability test
**Control:**Acceptance test
**Output:**Acceptance test report.

* * *

<center>**Delivery Phase**</center>

**Input:**Tested/accepted system.
**Process:**Installation, Training.
**Control:**Version description document.
**Output:**Version description document.