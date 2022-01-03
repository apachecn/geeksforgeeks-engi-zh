# 软件检查清单

> 原文:[https://www . geesforgeks . org/software-inspection-核对表/](https://www.geeksforgeeks.org/software-inspection-checklist/)

[软件检查](https://www.geeksforgeeks.org/how-software-inspection-improves-software-quality/)流程通常需要检查表，只是为了在检查[软件产品](https://www.geeksforgeeks.org/software-engineering-software-product/)时向审查人员提供确定和识别缺陷的提示和一些建议。检查过程应该总是需要由一些常见编程错误的清单来驱动。

一个**检查清单**仅仅是一个特定软件产品已经被检查的保证。应通过与一些有经验的工作人员讨论制定检查清单，并随着检查过程中获得更多经验而定期更新。指南通常包括各种工件的清单，如设计文件、要求等。

不同的**清单**也是针对各种[编程语言](https://www.geeksforgeeks.org/introduction-to-programming-languages/)准备的，即针对不同的源语言分别给出源代码清单。清单中有一些项目是一般性的，因此需要大量的人工判断。检查过程中可能进行的一些检查如下:

1.  **[data failure:**
    *   Are all variables of the inspection program initialized before use?
    *   Do all constants have names?
    *   What are the chances of buffer overflow? Wait a minute.
2.  **Control failure:**
    *   Are the conditions of each conditional statement correct?
    *   Does every cycle have to end?
    *   Are compound word brackets correct?
3.  **Input/output (I/O) failure:**
    *   Are all input variables used?
    *   Are all output variables assigned values before output?
    *   Can you enter which ones are accidental corruption? Wait a minute.
4.  **Interface failure:**
    *   Are the parameters of all methods and functions correct?
    *   Does the type of parameter match actual and formal?
    *   Are the parameters in the correct order?
    *   If all components access shared memory, do they have the same type of shared memory structure?
5.  **Storage management failure:**
    *   If the link structure is modified, are all links redistributed correctly?
    *   If dynamic storage is used, is the space allocated correctly?
    *   Do you explicitly unassign the space when it is no longer needed? Wait a minute.
6.  **Abnormal management failure:**
    *   Have all possible error situations been considered or considered?

**示例:**

1.  **Requirements checklist:**
    *   Is there a clear distinction between requirements and data?
    *   Does the requirement accurately define all the information that needs to be presented to users?
    *   Are the requirements for system and user responses to all error situations?
    *   Is each requirement stated clearly, concisely and clearly?
    *   Is every requirement testable?
    *   Are there any ambiguous or implied requirements?
    *   Are there conflicting requirements?
    *   Is there anything to be solved in the software requirement specification (SRS)?
    *   Is a performance requirement, such as response time, data storage requirements, etc. Statement?
2.  **Error handling and recovery checklist:**
    *   Are there enough error conditions to test?
    *   Have you tested the error situation where there is a high probability of error or the error result is fatal to the system?
    *   Are all return codes recorded?
    *   Can all the return information be understood?
    *   Whether the program allows successful error recovery; Cross-module or process failure? Cross-operating system failure? Across the break? Hardware failure?