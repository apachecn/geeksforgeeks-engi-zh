# 数据流图规则

> 原文:[https://www.geeksforgeeks.org/rules-for-data-flow-diagram/](https://www.geeksforgeeks.org/rules-for-data-flow-diagram/)

以下是绘制 [DFD(数据流图)](https://www.geeksforgeeks.org/what-is-dfddata-flow-diagram/)时需要牢记的规则。

*   **Data can not flow between two entities. –**
    Data flow must be from entity to a process or a process to an entity. There can be multiple data flows between one entity and a process.
*   **数据不能在两个数据存储之间流动**
    数据流动必须是从数据存储到一个进程或一个进程到一个数据存储。数据流可以从一个数据存储发生到多个进程。

*   **Data can not flow directly from an entity to data store –**
    Data Flow from entity must be processed by a process before going to data store and vice versa.*   **A process must have atleast one input data flow and one output data flow –**
    Every process must have input data flow to process the data and an output data flow for the processed data.*   **A data store must have atleast one input data flow and one output data flow –**
    Every data store must have input data flow to store the data and an output data flow for the retrieved data.*   Two data flows can not cross each other.*   系统中的所有进程必须链接到至少一个数据存储或任何其他进程。