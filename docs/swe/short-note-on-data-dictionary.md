# 数据字典上的简短注释

> 原文:[https://www . geesforgeks . org/data-dictionary 上的简短注释/](https://www.geeksforgeeks.org/short-note-on-data-dictionary/)

[数据字典](https://practice.geeksforgeeks.org/problems/what-is-data-dictionary)由两个词组成，即简单地表示通过某些来源收集的信息的数据和表示该信息可用的字典。

**数据字典**可以定义为数据库所有数据元素或内容的信息集合，如数据类型、系统的文本描述等。它使用户和分析师更容易使用数据，也更容易理解和掌握关于输入、输出、数据库组件和中间计算的常识。

**为什么数据字典必不可少？**

*   数据模型提供的信息和细节较少。因此，一个数据字典是非常必要的，需要有适当的知识和内容的使用。
*   数据字典提供系统模型中使用的名称的所有信息。
*   数据字典还提供关于系统模型中存在的实体、关系和属性的信息。
*   作为结构化分析和设计工具的一部分，实现了一个数据字典。

以下类型的信息用于存储在数据字典中:

<center>

| 名字 | 描述 |
| **名称** | 名称通常包括所有可用复合数据或控制项的主要名称、外部实体或数据存储的名称。 |
| **别名** | 任何其他代替名字的词 |
| **在哪里或如何使用？** | 数据字典通常给出关于数据或控制项在哪里以及如何被使用的信息，这些信息可以包括作为输入/输出来处理。 |
| **描述** | 表示内容的符号 |

数据字典包括以下类型的符号:

<center>

| 数据结构 | 注释 | 意义 |
| **成分** | = | 是由 |
| **序列** | + | 代表“与” |
| **选择** | [ &#124;] | 代表或 |
| **重复** | { } <sup>n</sup> | 代表 n 次重复或重复 n 次 |
| **括号** | ( ) | 可能存在也可能不存在的可选数据 |
| comment | *…* | 界定注释或注释信息 |

</center>

Let us understand this by taking a example of reservation system. In reservation system, “passenger” is an data item whose information is available on data dictionary as follows:

<center>

| 键 | 价值观念 |
| **名称:** | 乘客 |
| **别名** | 没有人 |
| **在哪里或如何使用？** | 乘客查询(输入)
车票(输出) |
| **描述** | 

*   Passenger = passenger _ name+passenger _ address
*   Passenger _ name = passenger _ last name+passenger _ first name+passenger _ middle _ initials
*   Passenger address = local address+community address+zip code
*   Local _ address = house number+street name+apartment number
*   Community _ address = city _ name+state _ name

 |

</center>

</center>