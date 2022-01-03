# 缺陷严重程度

> 原文:[https://www.geeksforgeeks.org/defect-severity/](https://www.geeksforgeeks.org/defect-severity/)

A **缺陷**是对规范或语法错误的误解的表示，其中表示是表达方式。**缺陷严重性**是基于缺陷对软件需求规格的破坏性影响程度对缺陷进行的分类。

**缺陷严重性:**
以下是软件开发中一些常用的缺陷严重性级别:

1.  **Critical –**
    A defect that completely obstructs the execution of a core functionality/feature of the software is classified a critical defect. This defect affects the critical functionalities and data and makes the testing of the software difficult. It is represented by S1.

    示例:我们有一个移动应用程序的登录界面。当用户点击忘记密码时，系统会要求用户输入他/她通过其注册的手机号码或电子邮件收到的动态口令。输入动态口令(正确/不正确)后，会显示一个加载程序，并无限期地继续。由于用户无法登录来访问移动应用程序的功能，这是一个严重的缺陷。

2.  **Major –**
    A defect that makes a major functionality/feature to behave grossly away from what is specified in the requirements specification of the software is classified a major defect. This defect affects the major functionalities and data. It is represented by S2.

    示例:我们有一个移动应用程序的登录界面，系统允许以输入的用户名访问平台，而无需验证其各自用户名的密码。因此，未经授权的用户可以访问该帐户，从而导致重大缺陷，导致个人数据被盗和犯罪活动。

3.  **Minor –**
    A defect which occurs when a functionality/feature does not behave as intended or exhibits some unnatural behavior, however the functionality/feature as a whole is not much impacted is classified a minor defect. This minimally affects the functionalities and data. It is represented by S3.

    示例:我们有一个移动应用程序的登录界面。用户输入用户名和密码，验证后，用户成功登录其帐户，但显示**“登录不成功，请稍后再试”**提示窗口。这是一个小缺陷，因为他只是显示了一个错误的提示窗口。

4.  **Trivial –**
    Any cosmetic defects such as misplaced images, spelling mistakes or alignment issues or font casing is classified a trivial defect. This defect does not affect functionalities and data. It is represented by S4.

    示例:我们有一个移动应用程序的登录界面，登录凭据的顺序不正确，即密码字段位于用户名字段上方。