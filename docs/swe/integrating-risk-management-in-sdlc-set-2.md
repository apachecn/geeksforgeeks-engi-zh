# 在 SDLC 中集成风险管理|第 2 集

> 原文:[https://www . geesforgeks . org/integrated-risk-management-in-SDLC-set-2/](https://www.geeksforgeeks.org/integrating-risk-management-in-sdlc-set-2/)

先决条件–[在 SDLC 中集成风险管理|第 1 集](https://www.geeksforgeeks.org/integrating-risk-management-in-sdlc-set-1/)
在本文中，我们将讨论 SDLC 的系统设计和开发阶段。
T4【3】。系统设计:
这是软件开发生命周期的第二阶段，其中必须建立系统架构，并且需要解决所有记录的需求。
在这个阶段，使用屏幕布局、伪代码、业务规则、流程图等详细描述系统(操作和特性)。
**来自风险管理活动的支持–**

*   资产重要性的准确分类
*   准确识别计划控制

它包括一系列七项活动:

1.  **Examine requirement Document –** It is quite important for the developers to be a part of examining requirement document to ensure understandability of requirements listed in requirement document.

    **风险因素–**
    研发对开发人员来说不清楚:开发人员有必要参与需求定义和分析阶段，否则他们不会对要开发的系统有很好的了解。他们将无法基于对系统需求的扎实理解开始设计。因此将为系统创建一个设计，而不是预期的设计。

2.  **Choosing the architectural design method activity –** It is method to decompose system into components. Thus it is a way to define software system components. There exist many methods for architectural design like structured object oriented, Jackson system development and formal methods. But there is no standard architectural design method.

    **风险因素–**
    建筑设计方法不当:如上所述，没有标准的建筑设计方法，可以根据项目的需要选择最合适的方法。但选择方法时要格外小心。如果选择不当，可能会导致系统实施和集成出现问题。即使实现和集成成功，架构设计也可能无法在当前机器上成功运行。编程语言的选择取决于所选择的架构模型。

3.  **Choosing the programming language activity –**Choosing programming language should be done side by side with architectural method. As programming language should be compatible with the architectural method chosen.

    **风险因素–**
    编程语言选择不当:编程语言选择不当可能不支持选择的架构方法。从而可能降低系统的可维护性和可移植性。

4.  **Constructing physical model activity –** The physical model consisting of symbols is a simplified description of hierarchical organized system.

    **风险因素–**

    *   复杂系统:如果要开发的系统非常大和复杂，那么它会给开发人员带来问题。因为开发人员会感到困惑，无法弄清楚从哪里开始，以及如何将如此庞大而复杂的系统分解成组件。
    *   复杂的设计:对于一个大型复杂的系统，由于混乱和缺乏足够的技能，开发人员可能会创建一个复杂的设计，这将很难实现。
    *   大尺寸组件:在大尺寸组件被进一步分解为子组件的情况下，可能在实现上遇到困难，并且也给这些组件分配功能带来困难。
    *   缺乏可重用的专业知识:缺乏适当的专业知识来确定可重用的组件给项目带来了严重的风险。因为与重用组件相比，从头开始开发组件要花费很多时间。从而延迟投影完成。
    *   可重用组件较少:在分析阶段对可重用组件的不正确估计会导致项目面临两个严重的风险——第一是项目完成延迟，第二是预算超支。开发人员会惊讶地发现，被认为已经准备好的代码的百分比需要从头重写，这最终会使项目预算超支。
5.  **验证设计活动–**验证设计是指确保设计是在建系统的正确解决方案，并满足所有用户要求。
    **风险因素–**
    *   验证设计是否符合需求的困难:有时开发人员很难检查提议的设计是否满足所有用户需求。为了确保设计是系统的正确解决方案，设计必须满足所有要求。
    *   许多可行的解决方案:当验证设计时，开发人员可能会遇到同一问题的许多替代解决方案。因此，选择满足所有要求的最佳设计是困难的。选择取决于系统及其性质。
    *   不正确的设计:在验证设计时，建议的设计可能只符合很少的需求或者根本不符合需求。可能是完全不同的设计。
6.  **Specifying design activity –** This activity involves following main tasks:
    1.  确定组件并定义它们之间的数据流
    2.  对于每个识别的组件，说明其功能、数据输入、数据输出和资源利用。

    **风险因素–**

    *   将功能分配给组件的困难:在两种情况下，开发人员可能会面临将功能分配给组件的困难——首先是当系统没有正确分解时，其次是如果需求文档没有正确完成，在这种情况下，开发人员会发现很难识别组件的功能，因为功能需求构成了组件的功能。
    *   扩展规范:应避免模块处理的扩展规范，以保持设计文档尽可能小。
    *   省略数据处理功能:像创建、读取这样的数据处理功能是组件对数据执行的操作。应避免意外遗漏这些功能。
7.  **记录设计活动–**在此阶段，准备设计文件(DD)。这将有助于在实施和其他阶段控制和协调项目。
    **风险因素–**
    *   不完整的 DD:设计文档应该足够详细，充分详细地解释每个组件、子组件、子子组件，以便开发人员可以在不同的模块上独立工作。如果 DD 缺少这个特性，那么程序员就不能独立工作。
    *   不一致的 DD:如果同一功能由多个组件执行。那么在这种情况下，它将导致设计文档的冗余，并最终导致不一致的文档。
    *   不清楚的 DD:如果设计文档没有明确定义组件，并且是用不常见的自然语言编写的，那么在这种情况下，开发人员可能很难理解提议的设计。
    *   大 DD:设计文档应该足够详细，列出所有组件，包括功能、输入、输出、所需资源等全部细节。它不应该包含不必要的信息。大型设计文档对程序员来说很难理解。

**4。开发:**
这个阶段包括按照开发人员和客户之间商定的要求对软件进行实际编码。
**风险管理活动的支持–**
所有设计的控制措施都在此阶段实施。

这个阶段包括两个步骤:编码和单元测试。

1.  **编码活动–**这一步包括为要开发的系统编写源代码。用户界面是在这一步开发的。然后在单元测试步骤中测试每个开发的模块。
    **风险因素–**
    *   设计文档不清晰:如果设计文档很大，不清晰，程序员很难理解文档，也很难找到从哪里开始编码。
    *   缺乏独立的工作环境:由于设计文档不清晰和不完整，开发人员团队很难分配独立的模块来工作。
    *   开发错误的用户界面和用户功能:不完整、不一致和不清晰的设计文档导致错误地实现用户界面和功能。糟糕的用户界面降低了系统在真实环境中的可接受性。
    *   与架构设计不兼容的编程语言:架构方法的选择单独驱动编程语言的选择。它们必须按顺序选择，否则如果不兼容，编程语言可能无法使用所选的方法。
    *   重复代码:在大型项目中，需要一次又一次地重写同一段代码。这消耗了大量时间，也增加了代码行数。
    *   不同程序员开发的模块:在大型项目中，模块在程序员之间划分。但是不同的程序员有不同的风格和思维方式。这导致代码不一致、复杂且不明确。
2.  **Unit Testing Activity –** Each module is tested individually to check whether it meets the specified requirements or not and perform the functions it is intended to do.

    **风险因素–**

    *   缺乏完全自动化的测试工具:直到今天，单元测试还没有完全自动化。这使得测试过程变得枯燥和单调。测试人员不会费心去生成所有可能的测试用例。
    *   审阅者无法理解的代码:在单元测试期间，开发人员需要审阅代码并对其进行更改。如果代码不可理解，更新代码将非常困难。
    *   编码驱动程序和存根:在单元测试期间，模块需要来自其他模块的数据，或者需要将数据传递给其他模块。因为没有一个模块是完全独立的。存根(Stub)是一段替代模块的代码，该模块接受来自被测试模块的数据。驱动程序是替换模块的代码，它将数据传递给被测试的模块。编写驱动程序和存根需要花费大量的时间和精力。因为这些不会随最终系统一起交付，所以这些被认为是额外的。
    *   测试用例的文档记录不佳:测试用例需要被适当地记录下来，以便将来可以使用。
    *   测试团队没有经验:测试团队没有足够的经验来处理自动化工具，并为驱动程序和存根编写简短的代码。
    *   糟糕的回归测试:回归测试意味着在变更时重新运行所有成功的测试用例。这节省了时间和精力，但是如果所有的测试用例都被选择重新运行，这可能会很耗时。

参考其他四个阶段–[在 SDLC 中整合风险管理|第 3 集](https://www.geeksforgeeks.org/integrating-risk-management-in-sdlc-set-3/)