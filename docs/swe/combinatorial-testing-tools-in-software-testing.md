# 软件测试中的组合测试工具

> 原文:[https://www . geesforgeks . org/组合测试-软件中的工具-测试/](https://www.geeksforgeeks.org/combinatorial-testing-tools-in-software-testing/)

[组合测试](https://www.geeksforgeeks.org/pairwise-software-testing/)是一种使用输入参数的多种组合来执行软件产品测试的测试技术。目的是确保产品没有错误，并且可以处理输入配置的不同组合或情况。最常用的组合测试方法之一是成对测试技术，它涉及测试所有成对的输入变量值。

### 为什么我们需要组合测试工具？

组合测试工具是易于使用的测试用例生成器，允许向输入参数模型提供输入和约束，然后使用该模型生成测试配置。

由于组合测试遵循一个复杂的过程，并且对许多输入参数手动执行这种测试可能是一项乏味的任务，因此，我们使用组合测试工具。这些工具不仅易于与许多输入参数一起使用，而且它们还可以在输入参数中添加约束，并相应地生成测试配置。互联网上有许多工具可以用来进行组合测试。在本文中，我们将讨论一些这样的工具，这些工具可以在互联网上免费获得，用于生成测试配置。

### 组合测试工具

在本节中，我们将讨论一些易于使用、免费且流行的组合测试工具。

#### 1.成对图片在线

这个工具最容易使用，因为我们只需要编写测试因子和约束(如果有的话)，测试配置就生成了。这个工具允许我们使用如下所示的 If-Then 格式来编写约束。对于初学者来说，从组合测试开始是一个很好的工具。

**点击尝试:** [成对 Pict Online](https://pairwise.yuuniworks.com/)

#### 2.覆盖阵列发生器的 CAGen

与以前的工具相比，这个工具提供了更多的功能和特性。首先，它允许我们创建多个输入参数模型，而不是像以前的工具那样只创建一个。此外，我们还可以保存这些模型，并将它们导出到不同类型的文件中。它还为用户提供了一个导入输入配置模型的选项。这个工具的另一个优点是它可以使用三种不同的算法(FIPOG，FIPOG-F，FIPOG-F2)来生成组合对象数组。

在这个工具中，必须一个接一个地添加因素和级别。但在此之前，需要遵循以下步骤:

1.  [<u>Click here</u>](https://matris.sba-research.org/tools/cagen/#/workspaces) to open the Kagan tool.
2.  Create a new workspace and give it a related name.
3.  Now click on the created workspace, and you will be able to see the input parameter model on the screen.
4.  Enter the factors in this model, their levels and cardinality (number of levels).
5.  After adding all factors and their levels in the input parameter model, click the "Generate button" on the left panel to generate the test configuration.

#### 3.Pairwiser

此工具需要用户帐户登录。登录后，您可以免费使用该工具。就像 CAGen 工具一样，Pairwiser 也需要一个接一个地输入所有因素及其值。同样，约束也可以 if-then 的格式输入。

与其他工具不同，Pairwiser 提供了广泛的功能和特性，可以在组合测试中探索。

1.  The tool comes with a visualization tool that shows the coverage of each test case added to the test suite.
2.  Another amazing feature is the generation of test scripts. If you want to perform a combination test for your application, you can simply use these test scripts for detailed evaluation. Test scripts can be modified according to our needs using many options in the tool.
3.  In the case of combinatorial testing (Pairwiser testing), pairwiser is a very popular tool because they provide faster pairwiser algorithms in the market.

**点击尝试:** [配对工具](https://inductive.no/pairwiser/)

#### 4.test cover . com-测试封面

执行组合测试的另一个直观工具是 testcover.com，在这里因子、值和约束简单地写在编辑器中，并生成测试配置。这个工具有一个非常快速和高效的算法，可以在 1 秒内生成大约 15 个测试用例。另一个优势是工具的简单生成器请求，我们只需要在新行中写入因子和值，就是这样！Testcover.com 还提供使用函数来添加约束。这个工具对于软件工程师和测试人员来说是一个很好的选择。

使用此工具需要注意以下事项:

1.  First, all factors are written.
2.  The value of one factor is written in the same line separated by spaces.
3.  Use the "with" keyword and brackets

被写入末尾

**点击试试:**[Testcover.com](https://www.testcover.com/index.php)

### 组合测试的优势

1.  一个主要优势是减少了执行测试用例的数量
2.  由于测试用例的数量减少了，执行测试套件所花费的时间变少了，因为它的体积很小
3.  测试覆盖率增加(高达 100%)
4.  覆盖率的提高也导致了 bug 产生率的提高
5.  随着测试覆盖率的提高，产品质量得到提高
6.  测试产品的总成本降低了

### 组合测试的缺点

1.  在组合测试中，如果没有正确选择输入变量的值，那么最终的测试配置是无效的
2.  类似地，上述观点也适用于选择和应用约束
3.  缺乏对输入参数的理解会导致不适当的组合对象数组
4.  手动执行组合测试是一项昂贵而乏味的任务
5.  即使使用自动化工具，生成测试配置也是一个耗时的过程