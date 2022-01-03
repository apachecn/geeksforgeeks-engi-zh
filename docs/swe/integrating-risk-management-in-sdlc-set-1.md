# 在 SDLC 中集成风险管理|第 1 集

> 原文:[https://www . geesforgeks . org/integrated-risk-management-in-SDLC-set-1/](https://www.geeksforgeeks.org/integrating-risk-management-in-sdlc-set-1/)

软件开发生命周期(SDLC)是一个概念模型，用于定义在软件开发过程的每一步执行的任务。虽然 SDLC 有各种模型，但通常 SDLC 包括以下步骤-

1.  初步分析
2.  系统分析和需求定义
3.  系统设计
4.  发展
5.  集成和系统测试
6.  安装、运行和验收测试
7.  维护
8.  处理

我们将简要讨论这些步骤，以及如何在这些步骤中纳入风险评估和管理，以确保降低软件开发中的风险。

**1。初步分析:**
这一步你需要搞清楚:

1.  该组织的目标
2.  正在研究的问题的性质和范围
3.  在对问题和竞争对手正在做的事情有深刻的理解后，提出替代的解决方案和建议
4.  描述成本和收益。

**来自风险管理活动的支持–**

1.  建立风险管理的流程和职责
2.  记录初始已知风险
3.  项目经理应该优先考虑风险

**2。系统分析和需求定义:**
这一步对于清楚了解客户期望和需求非常重要。因此，非常重要的是以最大的谨慎和适当的时间来进行这一阶段，因为任何可能的错误都将导致整个过程的失败。以下是在此阶段进行的一系列步骤:

1.  最终用户需求通过文档、客户访谈、观察和问卷调查获得
2.  识别当前系统的优点和缺点，以便在新系统中避免缺点并发扬优点。
3.  任何特定的用户建议都用于准备规格，并针对第二步中发现的缺点找到解决方案。
    1.  确定需要保护的资产，并根据机密性、完整性和可用性分配其重要性
    2.  确定这些资产面临的威胁和由此带来的风险
    3.  确定现有的安全控制措施以降低风险
4.  **Feasibility Study –** This is the first and most important phase. Often this phase is conducted as a standalone phase in big projects not as a sub phase under requirement definition phase. This phase allows the team to get an estimate of major risk factors cost and time for a given project. You might be wondering why this is so important? Feasibility study help us to get an idea whether it is worthy to construct the system or not. It helps to identify main risk factors. 

    **风险因素–**
    以下是可行性研究阶段的风险因素列表:

    *   项目经理经常在估计项目的成本、时间、资源和范围时出错。不切实际的预算、时间、资源不足和不明确的范围往往会导致项目失败。
    *   不切实际的预算:如上所述，不准确的预算估计可能会导致项目在 SDLC 早期资金耗尽。准确的预算估计直接关系到对时间、精力和资源的正确认识。
    *   不切实际的时间表:不正确的时间估计会导致项目经理给开发人员带来按时交付项目的负担。从而损害项目的整体质量，并因此使系统更不安全和更易受攻击。
    *   资源不足:在某些情况下，可用的技术、工具不是最新的，无法满足项目要求，或者可用的资源(人员、工具、技术)不足以完成项目。在任何情况下，该项目都将被推迟，或者在最坏的情况下，它可能导致项目失败。
    *   不清楚的项目范围:清楚地了解项目应该做什么，哪些功能是重要的，哪些功能是强制性的，哪些功能可以被认为是额外的，这对项目经理非常重要。对系统了解不足可能会导致项目失败。
5.  **Requirement Elicitation –** It starts with analysis of application domain. This phase requires the participation from different stake holders to ensure efficient, correct and complete gathering of system services, its performance and constraints. This data set is then reviewed and articulated to make it ready for the next phase. 

    **风险因素–**

    *   不完整的需求:在 60%的情况下，用户无法在开始时陈述所有的需求。因此，需求在整个软件开发生命周期过程中具有最动态的性质。如果任何用户需求、约束或其他功能性/非功能性需求没有被覆盖，那么需求集就被认为是不完整的。
    *   不准确的需求:如果需求集没有反映真实的用户需求，那么在这种情况下，需求就是不准确的。
    *   需求不明确:在 SDLC 的过程中，用户和开发者之间往往存在沟通的鸿沟。这最终会影响需求集。如果分析人员和开发人员不能理解用户陈述的需求，那么这些需求就被认为是不清楚的。
    *   忽略非功能性需求:有时开发人员和分析师忽略了非功能性需求与功能性需求同等重要的事实。在这种混乱中，他们专注于交付系统应该做什么，而不是系统应该如何，如可伸缩性、可维护性、可测试性等。
    *   冲突的用户需求:系统中的多个用户可能有不同的需求。如果不仔细列出和分析，这可能会导致要求不一致。
    *   镀金:一开始就列出所有要求是非常重要的。在开发的后期添加需求可能会导致系统中出现威胁。镀金不过是给系统增加了之前没有考虑到的额外功能。从而招致威胁并使系统易受攻击。
    *   真实操作环境描述不清晰:对真实操作环境的了解不足会导致某些遗漏的漏洞，因此威胁直到软件开发生命周期的后期才被发现。
6.  **Requirement Analysis Activity –** In this step requirements that are gathered by interviewing users or brainstorming or by another means will be: first analysed and then classified and organised such as functional and non functional requirements groups and then these are prioritized to get a better knowledge of which requirements are of high priority and need to be definitely present in the system. After all these steps requirements are negotiated. 

    **风险因素–**
    本步骤风险管理有以下任务要做:

    *   不可验证的需求:如果像测试、检查等有限的成本有效的过程不可用于检查软件是否满足需求，那么该需求被称为不可验证的。
    *   不可行的需求:如果没有足够的资源来成功地实现需求，那么它就被认为是不可行的需求。
    *   不一致的要求:如果一个要求与任何其他要求相矛盾，那么这个要求就被认为是不一致的。
    *   不可追溯的需求:每个需求都有一个来源是非常重要的。在文档编制过程中，有必要编写每个需求的原始来源，以便将来需要时可以追溯。
    *   不现实的需求:如果一个需求满足所有上述标准，比如它是完整的、准确的、一致的、可追踪的、可验证的等等，那么这个需求就足够现实，可以被记录和实现。
7.  **Requirement Validation Activity –** This involves validating the requirements that are gathered and analyzed till now to check whether they actually defines what user want from the system. 

    **风险因素–**

    *   被误解的领域特定术语:开发人员和应用程序专家经常使用领域特定术语，或者我们可以说大多数最终用户无法理解的技术术语。从而在最终用户和开发人员之间造成误解。
    *   使用自然语言表达需求:自然语言并不总是表达需求的最佳方式，因为不同的用户可能有不同的标志和约定。因此，建议使用正式的语言来表达和记录。
8.  **Requirement Documentation Activity –** This steps involves creating a Requirement Document(RD) by writing down all the agreed upon requirements using formal language. RD serves as a means of communication between different stakeholders. 

    **风险因素–**

    *   不一致的需求数据和研发:有时可能会发生这种情况，由于收集和记录过程中的小故障，实际需求可能与记录的不同。
    *   不可修改的研发:如果在研发准备期间，没有考虑具有可维护性的研发结构，那么在变更过程中，如果不重写文档，将很难编辑文档。