# 软件工程|确定软件开发指标

> 原文:[https://www . geesforgeks . org/software-engineering-identificati on-software-development-metrics/](https://www.geeksforgeeks.org/software-engineering-identifying-software-development-metrics/)

机器人和飞行汽车的未来时代可能还没有到来，但人们不能否认这样一个事实，即技术确实为自己创造了一个整洁的空间，一个不容忽视的空间。软件吞噬了每一个工业空间，以至于今天软件和商业齐头并进。这个大大小小的组织骨干都是由严谨、勤奋和创造性的发展造就的。公司将相当一部分资源投入到昂贵的员工身上，这些员工推动了组织运行所依赖的技术的发展。因此，当务之急是通过赋予团队跟踪效率的能力来探索和定量衡量此类投资的绩效。这项任务被委托给指定的软件开发经理。

那么，软件开发经理如何衡量他的团队的生产力呢？没有度量标准，经理该如何衡量？
本文讨论了一些度量标准，并确定它们是否可以作为软件开发经理自信地做出关于交付项目的最有效方式的决策的手段。

1.  **Counting Lines of Code:** 
    Can we associate quality of a developer with the number of lines of code contributed? While greater contribution does evaluate to more work it does not necessarily, attribute better quality of work. We cannot assume that a developer that has contributed greater volume of code is working efficiently. 

    目标是用最少的代码实现功能。因此，尽管代码行表明一致性和工作进度，但它不是评估生产率的有效指标。这将我们引向下一点，功能是关键。

2.  **Function Points:** 
    Functionality seems like the pivotal purpose to write code and a function point represents a step towards achieving the desired functionality. Can we monitor user functionality developed and delivered by the developer to evaluate performance? There are also several task-tracking tools such as Bugzilla and JIRA widely used that eradicate the manual effort of administrating progress. 

    那么我们可以不计算使用这些工具完成的功能点数量吗？这里的问题源于每个函数的动态特性。每个功能都不一样。虽然有些可能非常简单，但有些需要更大的努力和时间。虽然用一种编程语言完成一个函数可能很容易，但用另一种语言可能更具挑战性。因此，完成更多功能点的开发人员不能凌驾于团队其他成员之上。此外，这样的度量标准会妨碍团队合作，因为开发人员很容易挑选简单可实现的功能点。因此，这不能作为可靠的判断标准。

3.  **Story Points:** 
    Similar to function points, story points are often used during the stages of software development. Frequently adopted in agile methodology, a story represents a business requirement of the project. Depending on the amount of work, complexity, risk and uncertainty of the task at hand, the effort required is calculated and accordingly a size is assigned to each user story. This size represents the number of story points. Burn down charts are often used to estimate the story points’ progress. Here, a measure of the coding effort is the unifying factor; yet again this metric presents a fallacy, as the initial estimation of the size assigned is left to the manager’s discretion. 

    例如，应该是 2 的故事点可能被不准确地测量为 4，因此发展缓慢。那么开发人员是否可以因为任务的完成而获得更多的荣誉呢？该指标提供了一个合适的衡量标准来确定工作进度，但不能确定工作效率。衡量编码工作似乎是获得可靠度量的正确途径，但是手动估计故事点的大小使得这个度量不可靠。

4.  **Coding Effort:** 
    As discussed in the previous point, measuring the coding effort seems like the way to go to assess work progress but not work productivity as it is often falsely estimated which results in inaccurate size of story points. There is a need to better estimate the coding effort required and tools such as blue optima have been designed for this purpose. The tool measures the developer’s rate by analyzing the coding effort between code commits. It then gives a measure of cost per unit time. A ratio of cost per hour to coding effort per hour gives a cost per coding effort ratio that provides valuable insight into a team’s efficiency. 

    通过分析这个度量，组织可以获得关于各种功能或故事点所需的实际编码工作的情报，这将允许经理更好地估计故事点的大小，并胜任地交付项目。

由于项目的规模、依赖性、风险和时间限制要求，软件项目交付在企业级遇到了许多障碍和挑战。组织必须尽最大努力确保项目顺利交付，以最大限度地减少业务影响，软件开发经理的职责是在其轨道上运行时保护开发列车。通过确定合适的指标，可以实现经济高效且可靠的交付指南，