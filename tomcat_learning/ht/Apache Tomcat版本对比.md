官方链接：[http://tomcat.apache.org/whichversion.html](http://tomcat.apache.org/whichversion.html)
# 一、文档翻译
## Apache Tomcat版本
Apache Tomcat是一款实现了Java Servlet技术和JSP技术的开源软件，不同版本的Apache Tomcat实现了相应版本的Servlet和JSP规范，规范和Apache Tomcat各个版本之间的映射关系如下表所示：
| **Servlet Spec**   | **JSP Spec**   | **EL Spec**   | **WebSocket Spec**   | **JASPIC Spec**   | **Apache Tomcat Version**   | **Latest Released Version**   | **Supported Java Versions**   | 
|:----|:----|:----|:----|:----|:----|:----|:----|
| 4.0   | 2.3   | 3.0   | 1.1   | 1.1   | 9.0.x   | 9.0.24   | 8 and later   | 
| 3.1   | 2.3   | 3.0   | 1.1   | 1.1   | 8.5.x   | 8.5.45   | 7 and later   | 
| 3.1   | 2.3   | 3.0   | 1.1   | N/A   | 8.0.x (superseded)   | 8.0.53 (superseded)   | 7 and later   | 
| 3.0   | 2.2   | 2.2   | 1.1   | N/A   | 7.0.x   | 7.0.96   | 6 and later(7 and later for WebSocket)   | 
| 2.5   | 2.1   | 2.1   | N/A   | N/A   | 6.0.x (archived)   | 6.0.53 (archived)   | 5 and later   | 
| 2.4   | 2.0   | N/A   | N/A   | N/A   | 5.5.x (archived)   | 5.5.36 (archived)   | 1.4 and later   | 
| 2.3   | 1.2   | N/A   | N/A   | N/A   | 4.1.x (archived)   | 4.1.40 (archived)   | 1.3 and later   | 
| 2.2   | 1.1   | N/A   | N/A   | N/A   | 3.3.x (archived)   | 3.3.2 (archived)   | 1.1 and later   | 


Tomcat的每个版本都支持满足上述表中最后一列要求的任何稳定的Java版本。

Tomcat还能够在满足上述表中最后一列要求的任何Java的早期访问构建版本（early access build）中工作。例如，在第一个Java8的稳定版发布之前，已经有用户在Java8上成功的将Tomcat8运行了几个月了。然而，早期访问构建版本的用户需要注意以下这些内容：
  * 对于最初的早期访问构建版本来说，包含可能导致Tomcat上运行的应用程序出现问题的错误（bugs）并不罕见；
  * 如果新的Java版本引入了新的语言特性，那么默认的JSP编译器可能不会立即支持它们，将JSP编译器切换至javac可能会使这些新的语言特性可以在JSP中使用；
  * 如果在使用早期访问构建版本的过程中真的发现了问题，请根据链接（[http://tomcat.apache.org/findhelp.html](http://tomcat.apache.org/findhelp.html)）寻求帮助。

下面将更详细地描述这些版本，以帮助您确定哪个版本适合您。有关每个版本的更多详细信息，请参见相关的发行说明。
请注意，尽管我们提供旧版本的下载和文档，如ApacheTomcat7.x，但我们强烈建议用户尽可能使用最新稳定版本的ApacheTomcat。我们认识到，跨主要版本升级可能不是一项简单的任务，并且在邮件列表中仍然为旧版本的用户提供一些支持。但是，由于社区驱动的支持方式，您的版本越旧，对您感兴趣或能够支持您的人就越少。
## Alpha / Beta / Stable
当对发布进行投票时，审阅者指定他们认为发布已经达到的稳定性级别。一个新的主要版本的初始版本通常经历了从Alpha版到Beta版再到Stable版的过程，需要几个月的时间。然而，只有当发布版所实现的Java规范已经完成，稳定性级别才可用。这意味着在所有其他方面都被认为是稳定的版本，如果规范不是最终的，那么仍然可以标记为Beta。
下载页面将始终显示最新的稳定版本和任何更新的Alpha或Beta版本（如果存在）。Alpha和Beta版本总是清晰地标记在下载页面上。
稳定性是一种主观判断，对于您打算使用的任何版本，您都应该仔细阅读发行说明。如果您是发布的早期采用者，我们很高兴听到您对其稳定性的意见，作为投票的一部分：它发生在开发邮件列表上（链接：[http://tomcat.apache.org/lists.html](http://tomcat.apache.org/lists.html)）。
### Alpha
Alpha版本可能包含大量未经测试的功能、缺少规范所需的功能和重大错误，预计不会在任何时间段内稳定运行。
### Beta
Beta版本可能包含一些未测试的功能和一些相对较小的错误，预计不会稳定运行。
### Stable
Stable版本可能包含少量相对较小的错误，计划用于生产使用，预计将长期稳定运行。
## Apache Tomcat 9.x
**ApacheTomcat9.x**是当前开发的重点。它构建在Tomcat 8 .x和8.5 .x上，并实现**Servlet 4.0**、**JSP 2.3**、**EL 3**、**WebSoCK 1.1**和**JASPIC 1.1**规范（**JavaEE 8**平台所需的版本）。除此之外，还包括以下重大改进：
  * 添加对HTTP/2的支持（需要在Java 9上运行（因为Apache Tomcat 90.0.M18）或安装了Tomcat Native库）;
  * 添加了对使用OpenSSL来支持JSSE连接器（NIO和NIO2）的TLS的支持；
  * 添加对TLS虚拟主机（SNI）的支持；
## Apache Tomcat 8.x
**ApacheTomcat8.0.x**构建在Tomcat7.0.x之上，实现了**Servlet 3.1**、**JSP 2.3**、**EL 3.0**和**WebSocket 1.1**规范。除此之外，还包括以下重大改进：
  * 用于替换早期版本中提供的多个资源扩展功能的单一公共资源实现；

**ApacheTomcat8.5.x**支持与ApacheTomcat8.0.x相同的**Servlet**、**JSP**、**EL**和**WebSocket**规范版本。此外，它还实现了**JASPIC1.1**规范。
它创建于2016年3月，作为Tomcat9.0.0.m4（alpha）里程碑版本的一个分支。它提供了来自**Tomcat9.x代码库的HTTP/2支持和其他功能**，同时与**Tomcat8.0运行时和规范要求兼容**。（Tomcat 9的稳定版本无法在那时创建，因为Tomcat 9针对的JavaEE规范仅在几年后才最终确定。）
Tomcat8.5被认为是Tomcat8.0的替代品。有关迁移到Tomcat 8.5的指南，请参阅迁移指南（链接：[http://tomcat.apache.org/migration.html](http://tomcat.apache.org/migration.html)）。
Apache Tomcat 8.5.x包括以下重大改进：
  * 添加对**HTTP/2**的支持（需要Tomcat Native库）；
  * 添加了对使用OpenSSL来支持JSSE连接器（NIO和NIO2）的**TLS**的支持；
  * 添加对TLS虚拟主机（**SNI**）的支持；

在Apache Tomcat 8.5.x中删除了以下技术：
  * HTTP和AJP连接器的**BIO**实现；
  * 对Comet API的支持；

发动机罩下的许多区域都发生了重大变化，从而提高了性能、稳定性和总拥有成本。有关详细信息，请参阅Apache Tomcat 8.5更改日志。

Tomcat8.0的用户应该知道，Tomcat8.0现在已经到了生命的尽头。Tomcat 8.0.x的用户应该升级到Tomcat 8.5.x或更高版本。
## Apache Tomcat 7.x
**ApacheTomcat7.x**建立在Tomcat6.0.x的改进基础上，实现了**Servlet 3.0**、**JSP 2.2**、**EL 2.2**和**WebSocket 1.1**规范。除此之外，还包括以下改进：
  * Web应用程序**内存泄漏检测和预防**；
  * 改进了管理器和主机管理器应用程序的安全性；
  * 通用**CSRF保护**；
  * 支持将外部内容直接包含在Web应用程序中；
  * **重构（连接器、生命周期）**和大量内部**代码清理**；
## Apache Tomcat 6.x
**ApacheTomcat6.x**建立在Tomcat5.5.x中所做的改进之上，并实现了**Servlet 2.5**和**JSP 2.1**规范。除此之外，还包括以下改进：
  * 内存使用优化；
  * 高级IO功能；
  * 重构集群；

Tomcat6的用户应该知道，Tomcat6现在已经到了生命的尽头。Tomcat6.x的用户应该升级到Tomcat7.x或更高版本。
## Apache Tomcat 5.x
**ApacheTomcat5.x**可以从归档文件中下载。
### Apache Tomcat 5.5.x
ApacheTomcat5.5.x支持与ApacheTomcat5.0.x相同的servlet和JSP规范版本。发动机罩下的许多区域都发生了重大变化，从而提高了性能、稳定性和总拥有成本。有关详细信息，请参阅Apache Tomcat 5.5更改日志。
### Apache Tomcat 5.0.x
ApacheTomcat5.0.x在许多方面改进了ApacheTomcat4.1，包括：
  * 性能优化和减少垃圾收集；
  * **重构的应用程序部署程序**，带有可选的独立部署程序，允许在将Web应用程序投入生产之前对其进行验证和编译；
  * 使用**JMX**和**Manager** Web应用程序完成服务器监控；
  * **可扩展性（**Scalability**）**和**可靠性（**Reliability**）**增强；
  * 改进了**Taglibs**处理，包括高级池和标记插件；
  * 改进了平台集成，带有本机Windows和Unix包装器；
  * 使用JMX嵌入；
  * 增强的安全管理器支持；
  * 集成会话群集；
  * 扩展文档；

Tomcat 5的用户应该知道，Tomcat 5现在已经到了生命的尽头。Tomcat 5.x的用户应该升级到Tomcat 7.x或更高版本。
## Apache Tomcat 4.x
**ApacheTomcat4.x** 可以从归档文件中下载
ApacheTomcat4.x实现了一个**新的Servlet容器（称为Catalina）**，它基于全新的架构。4.x版本实现了**Servlet 2.3**和**JSP 1.2**规范。
### Apache Tomcat 4.1.x
ApacheTomcat4.1.x是ApacheTomcat4.0.x的一个重构，包含重要的增强功能，包括：
  * 基于**JMX**的管理功能；
  * 基于**JSP**和**Struts**的管理Web应用程序；
  * 新的**Coyote连接器**（支持**HTTP/1.1**、**AJP 1.3**和**JNI**）；
  * 重写**Jasper JSP页面编译器**；
  * 提高性能和内存效率；
  * 增强的管理器应用程序支持与开发工具集成；
  * 从**build.xml**脚本直接与管理器应用程序交互的自定义**Ant**任务；
### Apache Tomcat 4.0.x
ApacheTomcat4.0.6是旧的生产级版本。为了提高**灵活性和性能**，4.0 Servlet容器（Catalina）从一开始就得到了开发。版本4.0实现了Servlet 2.3和JSP 1.2规范的最终发布版本，根据规范的要求，ApacheTomcat4.0还支持为Servlet 2.2和JSP 1.1规范构建的Web应用程序，不做任何更改。

Tomcat4的用户应该知道，Tomcat4现在已经到了生命的尽头。Tomcat4.x的用户应该升级到Tomcat7.x或更高版本。
## Apache Tomcat 3.x
**ApacheTomcat3.x **可以从归档文件中下载
  * 版本**3.3**是当前的生产级版本，实现了Servlet 2.2 和 JSP 1.1规范。Apache Tomcat 3.3是Apache Tomcat 3.x架构的最新延续，它比3.2.4更先进，3.2.4是“旧”的生产级版本；
  * **3.2.4**是“旧”的生产级版本，现在只在维护模式；
  * 版本**3.1.1**是一个遗留版本；

所有Apache Tomcat 3 .x都将其遗产追溯到原始的Servlet和JSP实现，这些服务是Sun捐赠给Apache软件基金会的。3.x版本完全实现了**Servlet 2.2**和**JSP 1.1**规范。
### Apache Tomcat 3.3.x
版本3.3.2是当前的生产级版本。它**继续进行3.2版中开始的重构**，并得出其逻辑结论。3.3版提供了更**模块化的设计**，允许通过添加和删除控制Servlet请求处理的模块来定制Servlet容器。此版本还包含许多**性能改进**。
### Apache Tomcat 3.2.x
版本3.2自3.1以来增加了一些新功能，主要的工作是**重构内部结构以提高性能和稳定性**。3.2.1版本，如3.1.1，是一个安全补丁。版本3.2.2修复了大量的bug和所有已知的规范遵从性问题。版本3.2.3是一个安全更新，它关闭了一个严重的安全漏洞。版本3.2.4是一个小的错误修复版本。3.2.3之前版本的Apache Tomcat的所有用户都应尽快升级。除了修复关键的安全相关错误之外，ApacheTomcat3.2.x分支的开发已经停止。
### Apache Tomcat 3.1.x
3.1版本比ApacheTomcat3.0有几个改进，包括**servlet重新加载**、**war文件支持**以及**为IIS和Netscape Web服务器添加连接器**。最新的维护版本3.1.1包含**对安全问题的修复**。Apache Tomcat 3.1.x没有正在进行的积极开发。Apache Tomcat 3.1的用户应该更新到3.1.1以关闭安全漏洞，强烈建议他们迁移到当前的生产版本Apache Tomcat 3.3。
### Apache Tomcat 3.0.x
最初的ApacheTomcat版本。

Tomcat3的用户应该知道，Tomcat3现在已经到了生命的尽头。Tomcat3.x的用户应该升级到Tomcat7.x或更高版本。

