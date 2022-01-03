# 左移测试方法

> 原文:[https://www.geeksforgeeks.org/shift-left-testing-approach/](https://www.geeksforgeeks.org/shift-left-testing-approach/)

[软件测试](https://www.indiumsoftware.com/software-testing-services/)是必须的。它确保产品被无故障地发布给最终客户。作为一个被广泛讨论的话题，测试软件的方法有很多。

一些公司倡导产品设计的“T0”瀑布方法。这里，软件是按顺序设计的。它严格经过以下开发周期:

```
1. Requirements/Gathering
2. Design
3. Development
4. Deployment 
```

测试被委托给产品设计的最后阶段(部署阶段之前)。这通常被称为“右移测试”。

**最后阶段的测试–劣势策略:**
所有代码都容易出现 bug。根据错误的类型，bug 可以是次要的(低风险)也可以是主要的(高风险)。

越早抓住这些虫子越好。它让开发团队有时间毫不延迟地修复软件，并避免长时间的最终测试阶段。当太多的错误没有同时出现时，修复被窃听的软件也更容易。这就是为什么在大多数情况下，转变正确的策略是无效的。

实际上，仔细检查一个最终产品的每一行代码都很累——只是为了找到一两个 bug。最好在开发代码时修复每个单元。这就是左移的作用！

1.  **Improved Code Quality:**
    The earlier you detect a bug, the better. It allows for better communication between testing and developing teams. It allows both teams to address each bug 1-by-1.

    对比一下极右的方法。在这里，所有的错误都被一次解决。许多人可能会被遗忘或忽视(由于时间或预算的限制)。

2.  **Multiple test types:**
    When codes are tested at each design stage – a multitude of test types can be applied.

    例如，单元测试是左移方法的一种可能性。这里，每个组件都被单独测试，以检查单个的 bug。此外，集成测试可以在整个设计阶段频繁进行。这确保了 bug 不会因为不同的单元被分配到一起而产生。

    与右移策略形成对比，右移策略只允许系统测试的可能性。即使这样也不准确，也不能有效地发现所有的 bug。

    **发现设计缺陷和架构问题:**
    有时候，bug 不是问题。正在实施的可能有缺陷的主要方面(或想法)。这些缺陷(可能会干扰其他代码)应该尽早发现。否则，在实施不可行的主要设计计划上浪费了太多时间。

    这是左移测试的另一个附加优点。毕竟，较小的单元测试是自动化的，它们的测试用例很容易设计。

    相比之下，系统测试需要时间，而且必须手动完成。也不能经常重复。这种可重复性使得左移方法更好。它允许更好的代码质量的产品，减少高风险错误的机会！

3.  **Reduced development and testing costs:**
    Bugs that are caught early reduce the chances of side-effects.

    由于需要担心的副作用更少，产品发布可以按时完成。最终代码可以交付给最终客户，而不需要未来的修复。在这里，建议在每次构建后进行 bug 测试。这允许更好的自动化连续测试，这对于大的 bug 是不可能的。

    此外，左移方法减少了对系统测试的需求。事实上，如果测试频繁进行，这种情况可能会完全消除。

    **未来版本问题更少:**
    很多软件都是用线上功能设计的。它们的设计也是为了修补未来的版本。如果以前的版本有未修复的 bug，这些未来的版本就不能被添加进来。

    这导致了“弓形波”效应，多个 bug 副作用可能会叠加。结果是，某些 bug 变得无法修复。

4.  **Keeps all project stakeholders informed:**
    With the shift-left approach, testing is done at each critical stage of the software’s development. As a result, the testing team ends up (by necessity) being involved in the planning of the project. They’re also informed on its business goals.

    这让他们对软件的目的有了更好的认识。它允许他们在测试过程中找到创造性的想法和解决方案。另外，这能让他们保持动力。因为测试团队明白从长远来看他们的努力有什么贡献。

5.  **让开发团队尽职尽责:**
    很多设计项目都把开发人员放在了创造代码的位置。但是在写每一行的时候检查质量呢？

通过鼓励频繁的测试，这种心态已经在开发人员中根深蒂固。由于测试需要耗时的修改，它确保开发人员在编写代码时最大限度地减少错误。

采用左移方法，鼓励开发人员更加负责。这也提高了他们的技能和熟练程度！

10.  **Improved testing collaboration:**
    Shift-left approaches take advantage of frequent “automation”. It lets them perform continuous testing to reduce time. But, that still leaves the problem of designing those tests. And this is often left to the testing team to figure out.

    此外，这里的问题是，设计最好的测试需要知道产品的目的，以及它的业务目标。

    使用左移方法，由于开发人员和测试团队一起工作，他们可以利用彼此的输入来设计自动化测试。这导致了测试场景的开发，这些场景在发现错误和问题时是真实和准确的。

**选择适合你的方法:**
左移方法可以通过多种方式练习。它们适合各种规模的软件(从大型在线平台到小型移动应用)。因此，您会发现您的设计截止日期因项目而异。因此，你选择的方法不同。

*   **基于模型:**
    在需求收集阶段，给定软件至少有一半的 bug 出现。在那个阶段发现 bug 减少了以后修复 bug 的需要。另外，他们让测试团队了解项目的基本目标。
*   **Traditional testing:**
    Here, the focus is on continuous testing, through unit and integration tests. It focuses on automation as much as possible, thus saving time and development costs.

    这种形式的测试倾向于忽略验收和系统测试(通过频繁的单元/集成测试，其结果或多或少得到保证)。

*   **增量测试:**
    这试图模仿传统的测试模型——但它是针对大型项目的。测试被分解成小块，在那里测试一组代码。代码集成在一起后，将再次测试它们，以确保没有错误。
*   **DevOps/易碎测试:**
    执行频率低于传统模型，这种形式的测试适用于期限紧迫的小型项目。