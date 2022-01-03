# 评审会议的不同阶段

> 原文:[https://www . geeksforgeeks . org/不同阶段审查会议/](https://www.geeksforgeeks.org/different-phases-of-review-meeting/)

**评审会议**是[正式技术评审(FTR)](https://www.geeksforgeeks.org/formal-technical-review-ftr-in-software-engineering/) 的重要和基本形式之一。

当整个软件的一小部分或特定部分受到审查时，即关键观察或检查时，FTR 通常是有效的。该会议可能包含一些与发现的缺陷或错误相关的讨论，或一些发现的缺陷日志。与会者一般会记下发现的缺陷，供作者改正。

他们还可以建议控制和处理或纠正发现的缺陷或错误。在启动阶段，决定需要采取的方法，以便所有参与者简单地知道他们实际需要什么。采取这种方法的决定只是基于以下几个因素中的一个:

*   **可用时间–**
    如果可用时间很短或更短，那么会议可能只识别或收集缺陷或错误。
*   **作者要求–**
    作者对于简单的纠正或修复缺陷或错误是否有任何要求。
*   **审查类型–**
    检查中只允许收集缺陷。从来没有人讨论过这个问题。

会议基本上涉及不同的阶段，在这些阶段中执行与所审查的文件相关的各种任务。根据审核类型，会议包括三个阶段:

1.  **Logging Phase :**
    This phase is considered as initial duration of review meeting when all of members or participants of review simply mention all points i.e., defect, query, and concern that are identified during this phase. During this phase, all of issues that are being determined or identified during stage are either logged by author or scribe.

    每一个缺陷或错误及其严重性，即严重性，必须记录在三个不同的严重性等级中，如下所示:

    *   **危急–**
        his 表示完全关闭并造成下游损坏。这也表明没有什么可以继续进行下去。
    *   **重大–**
        这表明缺陷非常严重，会导致系统崩溃或可能造成下游损坏。然而，系统的某些部分仍然可以工作。
    *   **轻微–**
        这表明系统不会出现任何重大故障，也不太可能造成下游损坏。

    我们基本上知道参与者在准备步骤中确定或识别缺陷或错误。所有这些已确定或已识别的缺陷通常都包含在此阶段并记录在案。我们只是在整个培训过程中发现和检测问题或缺陷。

2.  **Discussion Phase :**
    After logging phase, team usually picks every point one by one and then discusses different aspects related to that point. All of main points like points criticality, areas that are impacted, and reasons are documented by either scribe or author.

    例如，如果发现任何缺陷，团队将讨论以下几点:

    *   缺陷是否有效。
    *   缺陷的严重程度和优先级。
    *   修复缺陷所需的时间。
    *   修复缺陷的方法。

    主持人通常负责控制和处理该阶段的所有活动。讨论结果通常会记录下来，以供进一步参考。

3.  **决策阶段:**
    讨论阶段之后，会议就在这个阶段。讨论阶段是正式会议的结束阶段。决策阶段有不同的退出标准，通常解释被发现或确定的缺陷的平均数量。决定基本上是由选手做出的。这一决定基于文件，有时取决于正式的退出标准。

**退出标准示例–**
如果每页发现的缺陷数量大于或等于某个限制，则主持人通常会将其发送进行返工，因为项目中的进一步处理需要文档上的返工。返工后再次审查。但是，如果每页发现的缺陷数量少于某个限制，那么版主只需在后续过程中进行检查。