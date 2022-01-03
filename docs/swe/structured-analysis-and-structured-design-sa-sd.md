# 结构化分析和结构化设计(SA/SD)

> 原文:[https://www . geesforgeks . org/structured-analysis-and-structured-design-sa-SD/](https://www.geeksforgeeks.org/structured-analysis-and-structured-design-sa-sd/)

**结构化分析和结构化设计(SA/SD)** 是一个图表符号，旨在帮助人们理解系统。SA/SD 的基本目标是提高质量，降低系统故障风险。它建立了具体的管理规范和文档。它侧重于系统的坚固性、易弯曲性和可维护性。

基本上，SA/SD 的方法基于**数据流图**。这很容易理解，但它侧重于定义明确的系统边界，而 JSD 方法太复杂，没有任何图形表示。

SA/SD 组合称为 SAD，主要关注以下 3 点:

1.  系统
2.  过程
3.  技术

服务协议/可持续发展包括两个阶段:

1.  **分析阶段:**使用数据流图、数据字典、状态转移图、ER 图。
2.  **设计阶段:**采用结构图和伪代码。

**1。分析阶段:**
分析阶段涉及数据流图、数据字典、状态转移图、实体关系图。

1.  **Data Flow Diagram:** 
    In the data flow diagram, the model describes how the data flows through the system. We can incorporate the Boolean operators and & or link data flow when more than one data flow may be input or output from a process. 

    例如，如果我们必须在流程的两条路径之间进行选择，我们可以添加一个运算符，或者如果流程需要两个数据流，我们可以添加一个运算符。“支票订单”流程的输入需要信用信息和订单信息，而该流程的输出将是现金订单或良好信用订单。

2.  **Data Dictionary:** 
    The content that is not described in the DFD is described in the data dictionary. It defines the data store and relevant meaning. A physical data dictionary for data elements that flow between processes, between entities, and between processes and entities may be included. This would also include descriptions of data elements that flow external to the data stores. 

    还可以为每个这样的数据元素包括逻辑数据字典。所有系统名称，无论是实体名称、类型名称、关系名称、属性名称还是服务名称，都应该输入到字典中。

3.  **状态转移图:**
    状态转移图类似于动态模型。它指定函数执行所需的时间以及事件触发的数据访问。它还描述了一个对象可以具有的所有状态，对象改变状态的事件，在转换发生之前必须满足的条件，以及在对象的生命周期中进行的活动。

4.  **ER Diagram:** 
    ER diagram specifies the relationship between data store. It is basically used in database design. It basically describes the relationship between different entities. 

**2。设计阶段:**
设计阶段涉及结构图和伪代码。

1.  **Structure Chart:** 
    It is created by the data flow diagram. Structure Chart specifies how DFS’s processes are grouped into tasks and allocate to the CPU. The structured chart does not show the working and internal structure of the processes or modules and does not show the relationship between data or data-flows. Similar to other SASD tools, it is time and cost-independent and there is no error-checking technique associated with this tool. 

    结构化图表的模块是任意排列的，来自 DFD 的任何过程都可以根据分析人员自己的感知选择作为中心变换。结构化图表很难修改、验证、维护和检查其完整性和一致性。

2.  **伪代码:**
    是系统的实际实现。这是一种非正式的编程方式，不需要任何特定的编程语言或技术。