# 面向服务(SOA)和微服务架构(MSA)的区别

> 原文:[https://www . geesforgeks . org/面向服务的 soa 和微服务架构的区别-msa/](https://www.geeksforgeeks.org/difference-between-service-oriented-soa-and-micro-service-architecture-msa/)

**1。面向服务的体系结构(SOA) :**
它是一个巨大的服务集合，服务在其中相互通信。该框架用于使用将所有组件视为服务的软件体系结构来设计软件系统。通信是由 SOA 提供的，通常用于数据传递，它可以通信两个或多个服务并完成一些活动。

它提供各种微服务，功能如下–

```
1. Loosely coupled
2. Reusable
3. Composable
4. Autonomic
5. Standardized 
```

**2。微服务架构(MSA) :**
它接受大量的服务，并分解成小的服务或可共享的组件。它也被称为一个整体，所有的功能都放在一个单一的过程中。这种方法用于开发不同方法的应用程序和通信，这些方法可以用不同的编程语言和数据存储来编写。

以下是 MSA 的一些特色功能–

```
1. Business capabilities
2. Products
3. Smart End Point
4. Automation
5. Evolutionary 
```

**SOA 和 MSA 的区别:**

<center>

| SOA。 | 生活津贴。 |
| 它是一个巨大的服务集合，服务在其中相互通信。 | 它是一种通用的体系结构，采用大量的服务，并分解成小的服务或可共享的组件。 |
| 它采用尽可能多分享的方法。 | 它采用的是按承诺分享的方式。 |
| 它用于共享数据存储。 | 它有独立的数据存储。 |
| 它支持各种多协议。 | 它支持 HTTP/REST 轻量级协议。 |
| 在面向服务的体系结构中，有一个多线程，处理更多的输入/输出 | 在微服务架构中，有单线程和非锁定输入/输出句柄。 |
| 它拥有所有服务的通用平台。 | 它有像 Nodejs 这样的平台，没有使用应用服务器。 |
| 它使用的容器是不太流行的 Docker linux。 | 它的容器工作得很好。 |
| 它使用传统的数据库。 | 它使用非关系数据库。 |
| 它使用 ESB 服务进行通信。 | 它不使用 ESB 服务。它有一个简单的信息系统。 |
| 它有共同的治理标准。 | 更加关注人的宽松治理。 |

</center>