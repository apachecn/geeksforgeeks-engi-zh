# 手动代码审查:安全评估

> 原文:[https://www . geesforgeks . org/manual-code-review-security-assessment/](https://www.geeksforgeeks.org/manual-code-review-security-assessment/)

[安全代码评审](https://www.geeksforgeeks.org/secure-code-review-assessment/)是在开发生命周期的早期阶段识别安全漏洞的代码评估。当与渗透测试(自动化和手动)一起使用时，它可以显著改善组织的安全状况。本文不讨论执行安全代码审查的过程，而是讨论审查代码的机制。

**如何开始考核？**
定义一个通用的清单可以给安全审查者想要的上下文，并且是开发人员已经纳入的安全检查水平的一个很好的晴雨表。核对表应涵盖最关键的安全控制和漏洞领域，例如:

*   数据有效性
*   证明
*   批准
*   会话管理
*   错误处理
*   密码系统
*   记录
*   安全配置错误

不可能涵盖所有领域，但是在这里我们将讨论在代码评审期间发现的一些缺陷及其缓解技术，以给出一个如何进行代码评审评估的观点。

**代码评估需要考虑哪些因素？**

1.  **Review Input Validation mechanism :**
    Always validate user data with full knowledge of what your application is trying to accomplish. Types of validation :
    *   **数据验证:**如果可能，应实施精确匹配验证，以允许符合预期值的数据。白名单(稍微弱一点但更灵活的方法)很常见，它允许在白名单中定义字符/正则表达式。另一种选择是“坏角色”黑名单。这种方法需要定期维护，因为设计了更多的机制来通过新的攻击有效载荷绕过该列表。
    *   **业务验证:**在审查代码之前，需要了解业务逻辑。它可以用来限制用户输入的值范围或交易，并拒绝没有商业意义的输入。

    对于验证，分析师必须确保以下几点:

    *   存在数据验证机制。
    *   对所有输入进行适当的长度检查。
    *   所有字段、cookies、http 头/正文和表单字段都经过验证。
    *   验证发生在服务器端。
2.  **审阅注释代码:**
    审阅者应确保在应用程序推出到生产环境之前，删除所有包含敏感信息的注释代码。
3.  **审查错误处理机制:**
    审查错误处理机制的目的是确保应用程序优雅地处理异常，并且不向用户呈现敏感信息。
4.  **查看与安全相关的 HTTP 头:**
    HTTP 响应头用于提高应用程序的安全性，并限制现代浏览器遇到容易预防的错误。这为部分缓解现有问题提供了更快、更便宜的方法，并为新应用提供了额外的防御层。分析师可以确定的常见标题有:

    | 标题名称 | 例子 |
    | 严格的运输安全 | 严格-运输-安全：最大年龄= 16070400;包括域名 |
    | x-框架-选项 | x-帧-选项：拒绝 |
    | X-XSS 保护 | x-XSS-保护:1;模式=块 |
    | 内容-安全-策略内容-安全-策略， | 内容-安全性-策略：默认-自我 |

5.  **审查 cookie:**
    cookie 通常是恶意用户的关键媒介，因此审查者必须查看为 cookie 设置了哪些属性，并测试它们是否安全。需要审核的属性有:

    | 属性 | 理由 |
    | 安全的 | 包含敏感信息的饼干通过加密连接传输 |
    | 客户端应用程序接口（如 JavaScript)无法访问饼干. |
    | 期满 | 表示浏览器应该使用甜饼干多长时间以及何时删除 |