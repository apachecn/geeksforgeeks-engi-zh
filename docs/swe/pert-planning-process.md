# 计划评审技术计划流程

> 原文:[https://www.geeksforgeeks.org/pert-planning-process/](https://www.geeksforgeeks.org/pert-planning-process/)

[项目评估和评审技术(PERT)](https://www.geeksforgeeks.org/project-evaluation-and-review-technique-pert/) 通过网络图描述活动和活动或任务的时间表。PERT 用于估计项目的完成时间。

计划包括以下步骤:

1.  **Identification of definite activities and breakthroughs:**
    It is convenient to list all the tasks and breakthroughs required to complete the project in the table. The breakthroughs represent the starting point and deadline of one or more activities. With the help of identification of activities, tasks at later stage can be expanded to build information on sequence and duration.

2.  **Determining the proper sequence of the activities:**
    This step in PERT planning process is used to regulate the sequence of activities. Activities can be serial or parallel, the sequence represents the dependency of one activity on other activity. As in the first step the identification of the activities is done, it is necessary to identify the relationships between activities in this step. The analysis of exact order in which the activities performed are required for other tasks.
3.  **Construction of network diagram:**
    A network diagram is drawn with the help of the activity identification and activity sequence information. In the network diagram, the activities are illustrated by arrowed lines and breakthroughs are illustrated by circles. To convert the tabular activity information into a network diagram, various CASE tools like MS-PROJECT are available which simplify the process of conversion easily.
4.  **Estimation of the time required for each activity:**
    All activities in the project are illustrated by the persistent or steady unit of time. PERT has the capacity to deal with ambiguity and unpredictability in the completion time of the activities. The commonly used unit in software engineering for the activity completion time is weeks.
5.  **Determination of Critical Path:**
    Critical path is the path which takes the maximum amount of time. There are many paths in the network diagram which demonstrates the start and end events of the project. Critical path is determined by adding the time taken by the activities in each sequence and then determining the longest path in the project. Total calendar time needed for the project is given by the critical path.
6.  **PERT 图表的更新:**
    PERT 图表随着项目工作的进展而修改。随着项目工作的继续，对 PERT 图表进行了许多更改，例如增加资源和根据实际时间更改估计时间。