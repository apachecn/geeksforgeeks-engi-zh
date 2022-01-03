# 软件工程|引发需求的挑战

> 原文:[https://www . geesforgeks . org/软件-工程-挑战-引发-需求/](https://www.geeksforgeeks.org/software-engineering-challenges-eliciting-requirements/)

先决条件–[需求获取](https://www.geeksforgeeks.org/software-engineering-requirements-elicitation/)

获取需求是需求工程过程的第一步。它帮助分析师获得关于问题领域的知识，这些知识反过来又被用来产生软件的正式规范。在这个过程中遇到了许多问题和挑战。其中一些如下:

1.  **理解庞大而复杂的系统需求很难–**
    大这个词代表 2 个方面:
    *   ㈠安全等方面的巨大限制。由于用户数量庞大。
    *   ㈡需要履行大量职能。
2.  **Undefined system boundaries –** 
    There might be no defined set of implementation requirements. The customer may go on to include several unrelated and unnecessary functions besides the important ones, resulting in an extremely large implementation cost that may exceed the decided budget. 
3.  **Customers/Stakeholders are not clear about their needs. –** 
    Sometimes, the customers themselves may be unsure about the exhaustive list of functionalities they wish to see in the software. This might happen when they have a very basic idea about their needs but haven’t planned much about the implementation part. 
4.  **Conflicting requirements are there –** 
    There is a possibility that two different stakeholders of the project express demands which contradict each other’s implementation. Also, a single stakeholder might also sometimes express two incompatible requirements. 
5.  **Changing requirements is another issue –** 
    In the case of successive interviews or reviews from the customer, there is a possibility that the customer expresses a change in the initial set of specified requirements. While it is easy to accommodate some of the requirements, it is often difficult to deal with such changing requirements. 
6.  **Partitioning the system suitably to reduce complexity –** 
    The projects can sometimes be broken down into small modules or functionalities which are then handled by separate teams. Often, more complex and large projects require more partitioning. It needs to be ensured that the partitions are non-overlapping and independent of each other. 
7.  **Validating and Tracing requirements –** 
    Cross-checking the listed requirements before starting the implementation part is very important. Also, there should be forward as well as backward traceability. For eg, all the entity names should be the same everywhere, i.e., there shouldn’t be a case where ‘STUDENT’ and ‘STUDENTS’ are used at separate places to refer to the same entity. 
8.  **Identifying critical requirements –** 
    Identifying the set of requirements that have to be implemented at any cost is very important. The requirements should be prioritized so that crucial ones can be implemented first with the highest priority. 
9.  **Resolving the “to be determined” part of the requirements –** 
    The TBD set of requirements include those requirements which are yet to be resolved in the future. The number of such requirements should be kept as low as possible. 
10.  **适当的文件、适当的会议时间**、**和预算限制–**
    确保适当的文件是一个固有的挑战，尤其是在需求变化的情况下。时间和预算限制也需要谨慎和系统地处理。

**总结**

与需求工程相关的问题很多，包括界定系统范围的问题、促进受拟议系统影响的不同社区之间的理解的问题，以及解决需求不稳定的问题。这些问题可能会产生不可持续的需求，并取消程序开发，否则，系统的开发将被认为是不令人满意或不可接受的，具有高修复成本，或者会发生变化。通过改进服务交付，可以改进需求工程流程，从而提高系统需求和更好的系统。

工程需求可以从推广、规范和验证需求中推导出来。大多数当前的策略和需求都侧重于清晰性，即服务表示。该报告关注的不是提名问题，而是规范策略没有充分解决的工程需求问题。提出了一种解除方法来解决这些问题。

这种新的方法寻求纳入现有推广战略的好处，同时更仔细地观察在提供服务过程中开展的活动。这些活动包括事实调查、数据收集、评估和规划、优先排序和整合。就其本身而言，现有的促销策略在其中一个或多个方面存在不足