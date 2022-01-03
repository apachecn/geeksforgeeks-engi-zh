# 保护网络应用

> 原文:[https://www.geeksforgeeks.org/securing-web-applications/](https://www.geeksforgeeks.org/securing-web-applications/)

网站和网络应用已经成为这个世界的必需品，从商业、公司、教育、协作、个人博客、食品和杂货、健康和医药、社交媒体平台、访问政府服务和数字支付，甚至投票，互联网上的一切都是可用的。如今，通过点击屏幕上的按钮和常见的问题“网站安全吗？”。答案是大部分但不完全。每一个合法的网站都试图提供最多的安全性，但是没有任何形式的互联网是完全的，100%安全的。

**网站 vs WebApp :**
网站是静态的 HTML，CSS，一些 JS 文件按照 CSS 中提供的样式显示。网站不是动态的，它们不能提交表单，不能动态生成页面，并且可能在其他方面也受到限制。网络应用程序是可以接受表单提交、动态生成页面、与数据库通信以完成凝乳过程等的程序。

网站所有者的一些安全提示一般是:

*   获得 SSL 证书

*   创建安全密码

*   保留备份

*   将网站更新到最新版本

这些是技术知识有限的网站所有者遵循的一些一般安全原则。这些原则对那些刚带来域名和主机的人来说很好，wordpress 用一个很好的主题补充道。这些人不需要担心服务器更新和安全性，不需要担心 wordpress 如何工作，他们只关心内容，有时还关心速度。对于这些类型的人来说，上述步骤基本上就足够了，但是对于网络应用程序来说，我们需要的东西比网站更多？

让我们研究一下在部署他们的 webapp 时需要注意的事项。

*   **Never put Debug mode ON in production –** 
    Many web frameworks like WordPress, Django, Larvel provide a development server which should be never used in production. Debug mode ON provides better error logs, with the availability of information such as variable names and line numbers from the source code for developers. 
*   **Restrict Access to server and close unused ports –** 
    Running our web app in cloud is very good option. Some of the good options are Digitalocean, google cloud, azure and AWS. When you rent for the virtual server limit the people who can access to the server. its better to use SSH to access the server. Always close unnecessary ports while running the server. 
*   **Always update frameworks and application –** 
    Updates are the best way to reduce bugs in our application. in the same manner updating the framework we used to build the application might be helpful but sometimes we have to rewrite the code for our application but if the update is long term it would be best to do it even we have to rewrite the code. 
*   **Keep the Database secure –** 
    Many times we miss that database is also the part of our application and its also necessary for us to keep our database secure. Always keep strong passwords, limit users who can have access to run native commands with the database. Its also very good to choose the database according to application need. 
*   **DNS hosting –** 
    DNS is the backbone of internet, its the phonebook for the internet. In simple word DNS is the protocol which converts human readable hostnames like geeksforgeeks.org to computer understanding numbers like 34.218.62.116\. Its necessary for our web app to have better and widespread DNS like Cloudflare, cloud based DnS which reduces the lookup time to find our server IP and to connect to it. 
*   **Limiting API usage –** 
    Many of the webapp use external services which will be included using specially configured API’s for specific functions. Most of API providers limit the usage according to their plan and its also better for web app developers also to implement rate limiting of API’s according to need so that we don’t pay any extra. 
*   **Bot and Spam –** 
    Many web application also contain forms for allowing to subscribe email, or some other query form, Many bots these days have the ability to submit the plain forms. To protect its better to keep recaptcha with every form which will keep most of the bots out. Google provides recaptcha for free for basic usage. 
*   **HTTP 头–**
    大多数 web 应用程序框架允许发送像 HSTS、CSP、Referrer 和 Permission Policy 这样的 HTTP 头，这有助于浏览器确定它应该允许加载样式、源和媒体的源和协议，从而强化 webapps 的安全性，例如升级到 HTTPS、XSS 保护等。

这些是一些需要注意的基本事项，您可以通过查看用于创建 web 应用程序的框架文档来了解更多的安全特性和策略。