# GitOps 概述

> 原文:[https://www.geeksforgeeks.org/overview-of-gitops/](https://www.geeksforgeeks.org/overview-of-gitops/)

**运筹:T1】**

GitOps 是一种新兴技术，它基本上是指一套理想的实践，使开发人员能够执行属于信息技术操作范畴的特定任务。GitOps 在延续的基础上描述、观察和声明是有用的，包括一切但不限于[连续积分(CI)](https://www.geeksforgeeks.org/what-is-ci-cd/) 的情况。

它坚持一个原则，即 Git 是真理的唯一来源。对期望状态的所有改变都是可追踪的。它也是开发和交付基于 Kubernetes 的基础设施和应用程序的操作模型。它授权开发者进行操作，并以自己的方式发货。然而，GitOps 可以通过使用聚合来管理整个系统，而无需 Kubernetes 的支持。

因此，简单来说，我们可以说 GitOps 是运营框架，它是 DevOps 的最佳实践，使用 DevOps 并将其用于版本控制、应用程序开发。

**GitOps 特别练习:**

*   GitOps is not limited to a single product, plug-in or platform.
*   GitOps workflow helps manage the entire IT infrastructure through processes. It needs three core components, namely IaC, MRs and CI/CD.

**GitOps 工作:**

GitOps 原则是灵活的，可以应用于许多类型的基础设施自动化，主要包括虚拟机和容器，并有效地对管理基于 Kubernetes 的基础设施的团队产生影响。GitOps 的变体在关注开发者中心体验时有所不同。GitOps 已经接受了具有持续集成代码的组织，因此它是一个首选的工作流。使用 GitOps，基础设施的任何变更都需要与应用程序的任何变更一起提交给 git 存储库。

**GitOps 的未来:**

人们普遍认为 GitOps 可能是 DevOps 的未来，因为 GitOps 是声明性的，并且具有配置和管理的云原生方法。然而，GitOps 的未来可能不会对所有人都有利。因为 Git 只能将请求作为其基础设施的最佳工作流。

**GitOps 的特点:**

使用它有很多原因。但是重要的特性是

*   It supports continuous deployment delivery and provides a way for organizations to push applications faster, and continuous deployment eliminates the need for any separate deployment.
*   In addition, it allows organizations to use a single tool to control the infrastructure, while supporting versioning of configuration changes.

**GitOps 的优势:**

GitOps 提供了很多有益的东西-

*   Undoubtedly, productivity, delivery and deployment are improved through the characteristics of reply and bifurcation.
*   The reliability of.
*   以饭桶
*   Standardized workflow for the center enables organizations to use a single set of tools.
*   Provides additional visibility.
*   Reduce potential variables in management
*   Provide a potential attack surface
*   Is lightweight and vendor neutral.
*   Closer development and operation.

**GitOps 的缺点:**

*   Users can face broken references from YAML.
*   It creates a pull method, and users can only use the tools that cause the pull.
*   Has the potential to apply programming interface throttling, because GitOps will always keep polling Git Repo.
*   The explosion of repositories
*   Can't keep up with the update of programming.

**最后**，这个 GitOps 有它的甜蜜点，但不是针对每一个部署问题，但是核心有所有的能力，用团队正在利用的工具和过程创建不可变的部署过程。但是有一点我们可以说，GitOps 的未来在持续部署方面是光明的。