# 软件工程中的故障减少技术

> 原文:[https://www . geesforgeks . org/fault-reduction-technologies-in-software-engineering/](https://www.geeksforgeeks.org/fault-reduction-techniques-in-software-engineering/)

**故障**是程序中的缺陷，当在特定条件下执行时，导致程序操作的结果与其要求不同。这是导致软件无法执行所需功能的情况。

以下是用于减少软件故障的技术:

1.  **Fault Prevention –**
    Fault Prevention/Avoidance strategies identify all potential areas where a fault can occur and close the gaps. These prevention strategies address system requirements and specification, software design methods, re-usability, or formal methods. They are employed during the development phase of the software to avoid or prevent fault occurrence.

    它们通过对系统需求、编程方法和软件可重用性的严格规范来提高系统的可靠性。但是很难量化故障避免策略对系统可靠性的影响。因此，尽管做了故障预防工作，故障还是会产生，因此需要排除故障。

2.  **Fault Removal –**
    Fault removal strategies are dependability enhancing techniques employed during verification and validation. They improve by detecting existing faults and eliminating the defected faults. They are employed after the development phase of the software to contribute to the validation of the software.

    常见的故障排除技术包括测试。因此，最小化组件尺寸和相互关系可以最大化测试的准确性。测试程序时遇到的困难通常与高昂的成本和详尽的测试有关。因此，故障排除是不完善的，因此需要容错。

3.  **Fault Tolerance –**
    Fault tolerance include dependability enhancing techniques that are used during the validation of software to estimate the presence of faults. It is used to reduce system design faults and enhance reliability of the software.

    在软件开发阶段采用容错技术，使系统能够容忍开发后系统中存在的故障，并在出现故障的情况下提供符合要求规范的操作。因此，当故障发生时，它可以防止系统故障。

故障预防、故障排除和故障排除代表了针对软件系统故障的偶然性及其对系统的影响的连续防线。尽管事实上，每一种技术的好处都是显著的，但是收益递减法则主张它们应该在每一种技术最有效的地方统一使用。