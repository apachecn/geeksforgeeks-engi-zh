# 缺陷优先级

> 原文:[https://www.geeksforgeeks.org/defect-priority/](https://www.geeksforgeeks.org/defect-priority/)

先决条件–[缺陷严重性](https://www.geeksforgeeks.org/defect-severity/)
缺陷是对规范或语法错误的误解的表示，其中表示是表达方式。**缺陷优先级**是根据待修复缺陷的重要性或优先级对缺陷进行分类。迫使软件系统变得无效的缺陷被赋予比导致软件的小功能失败的缺陷更高的优先级。

缺陷的优先级由业务涉众、产品负责人、项目经理、业务分析师根据缺陷的[严重程度](https://www.geeksforgeeks.org/defect-severity/)和业务需求来定义。优先级分类与软件调度相关联。

**缺陷优先级–**
根据最终用户的角度，下面是软件开发中不同的缺陷优先级:

1.  **立即:**
    由于严重影响系统和业务需求，需要立即修复的缺陷。它限制系统执行关键功能，并阻止软件测试的执行，迫使软件系统变得无效。

任何影响业务需求的缺陷都需要立即考虑，并被归类为立即。所有严重缺陷都属于立即优先类别，但所有立即优先缺陷不一定属于严重缺陷。以 **P1** 为代表。

**例–**
我们有一个电商购物网站，网站首页的公司名称拼错了，那么缺陷优先级高但严重程度低。
由于拼写错误可能会对公司网站造成负面印象(人们可能会认为网站是假的)，导致业务损失，但拼写错误不会影响网站的功能。

*   **High :**
    This defect comes after immediate as it needs less attention but still more than other remaining priority categories. These defects are resolved once critical issues are solved.
    A defect that affects business and major functionality/feature of software due to a program defect or sometimes environmental problem comes under category of High Priority. It is represented by **P2**.

    **示例–**
    我们有一个电子商务购物网站，每当我们在愿望清单部分添加一个项目时，它就会崩溃。

    *   **Medium :**
    A defect with minor severity that need not be fixed right away as it does not cause any significant functionality issues or business. These defects are fixed after Immediate and High priority defects are removed. All the Minor severity defects fall into this category. It is represented by **P3**.
    Sometimes, even trivial errors such as wrong error message in a system can qualify for a medium priority defect.

    **示例–**
    我们有一个电子商务购物网站，我们进行了购买。购买的项目被添加到网站的订单部分，但付款入口显示错误的“付款不成功”提示。

    *   **Low :**
    A defect that does not have any major impact on functionality of software and hence does not need any immediate attention. It can be repaired in future or once higher priority defects are fixed. All the Low severity defects fall into this category. It is represented by **P4**.
    Sometimes, low priority defects are also used to suggest some enhancements in existing software design or to create a small feature to enhance user experience.

    **示例–**
    我们有一个电商购物网站，主屏幕上的导航栏没有对齐。