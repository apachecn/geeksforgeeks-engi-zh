# 软件工程|洁净室测试

> 原文:[https://www . geesforgeks . org/software-engineering-clean room-testing/](https://www.geeksforgeeks.org/software-engineering-cleanroom-testing/)

**洁净室测试**由 IBM 首创。这种测试在很大程度上依赖于演练、检查和正式验证。除了使用编译器做一点语法测试之外，程序员似乎不被允许通过体罚来检查他们的任何代码。计算机代码开发理念依赖于通过采用严格的检查方法来避免计算机代码缺陷。这个计算机代码的目标是零缺陷计算机代码。

“洁净室”这个名字来源于与半导体制造单位的类比。在这些单元(洁净室)中，缺陷区域单元通过在超洁净的空气中生产来避免。在这个合理的开发过程中，确定零件与其规格的一致性的检查已经取代了单元测试。

据报道，这种技术产生的文档和代码比依赖基于代码执行的测试的各种开发方法更加可靠和可修复。

计算机代码开发的洁净室方法依赖于 5 个特征:

1.  **正式规范:**
    正式给出待开发的计算机代码。一个显示系统对刺激反应的状态转移模型被用来精确说明。
2.  **增量开发:**
    计算机代码被分割成区域单元开发的增量，并在个别基础上有效，不使用白室方法。这些增量区域单位是在护理助理在方法的早期阶段根据客户输入给出的。
3.  **结构化编程:**
    仅使用有限范围的管理和信息抽象构建区域单元。程序开发方法是逐步细化规范的方法。
4.  **静态验证:**
    开发的计算机代码被静态验证虐待严格的计算机代码检查。没有针对代码部分的单元或模块测试方法。
5.  **系统统计测试:**
    对整合后的计算机代码增量进行统计测试，算出其责任。这些应用数学测试区域单元支持与系统规范并行开发的操作概要。

**注意:**这种方法的主要缺点是测试工作量随着单位时间内的演练、检查和验证而增加。