# 软件测试|可扩展性测试

> 原文:[https://www . geesforgeks . org/software-testing-scalability-testing/](https://www.geeksforgeeks.org/software-testing-scalability-testing/)

**可伸缩性测试**是一种非功能性测试，在这种测试中，软件应用程序、系统、网络或进程的性能是根据其放大或缩小用户请求负载数量的能力或其他此类性能属性来测试的。它可以在硬件、软件或数据库级别执行。可伸缩性测试被定义为网络、系统、应用程序、产品或流程在系统规模或容量发生变化以满足不断增长的需求时正确执行功能的能力。它确保软件产品可以管理用户流量、数据量、事务计数频率和许多其他方面的计划增长。它测试系统、进程或数据库满足不断增长的需求的能力。

可伸缩性测试是测量软件产品或系统停止伸缩的时间点，并确定其背后的原因。用于此测试的参数因应用程序而异。例如，网页的可伸缩性测试取决于用户数量、CPU 使用率、网络使用率，而 web 服务器的可伸缩性测试取决于处理的请求数量。

**可扩展性测试的目标:**
可扩展性测试的目标是:

*   确定应用程序如何随着工作负载的增加而扩展。
*   确定软件产品的用户限制。
*   确定负载下的客户端降级和最终用户体验。
*   确定服务器端的健壮性和降级。

**可扩展性测试属性:**

*   **Response Time:**
    Response time is the time consumed between the user’s request and the application’s response. Response time may increase or decrease based on different user load on the application. Basically, the response time of an application decreases as the user load increases. Application having the lesser response time is considered as the higher performance application.
*   **Throughput:**
    Throughput is the measurement of number of requests processed in a unit time by the application. It differs from one application to another as in web application it is measured in number of user requests processed in a unit time whereas in database application it is measured in number of queries processed in a unit time.
*   **Performance measurement with number of users:**
    Depending on the application type, it is always tested for the number of users that it can support without its breakdown or busy standby situation.
*   **Threshold load:**
    Threshold load is the number of requests or transactions the application can process with desired throughput.
*   **CPU Usage:**
    CPU Usage is the measurement of the CPU utilization while executing application code instructions. It is basically measured in terms of the unit *Megahertz*.
*   **Memory Usage:**
    Memory usage is the measurement of the memory consumed for performing a task by an application. It is basically measured in terms of the unit *bytes*.
*   **网络使用率:**
    网络使用率是对被测应用消耗的带宽的度量。它是根据每秒接收的字节数、每秒接收的帧数、每秒接收和发送的段数等来衡量的。

**可伸缩性测试涉及的步骤:**
以下是可伸缩性测试涉及的步骤:

1.  为执行可伸缩性测试定义一个可重复的过程。
2.  确定可伸缩性测试的标准。
3.  确定执行测试所需的软件工具。
4.  设置测试环境，配置执行可伸缩性测试所需的硬件。
5.  创建并验证可视化脚本。
6.  创建并验证负载测试场景。
7.  执行测试。
8.  评估结果。
9.  生成所需的报告。