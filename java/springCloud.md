
# Spring Cloud

## 什么是 spring cloud？

从字面理解，Spring Cloud 就是致力于分布式系统、云服务的框架。  
Spring Cloud 是整个 Spring 家族中新的成员，是最近云服务火爆的必然产物。  
Spring Cloud 为开发人员提供了快速构建分布式系统中一些常见模式的工具，例如：  
配置管理 服务注册与发现 断路器 智能路由 服务间调用 负载均衡 微代理 控制总线 一次性令牌 全局锁 领导选举 分布式会话 集群状态 分布式消息 ……  

使用 Spring Cloud 开发人员可以开箱即用的实现这些模式的服务和应用程序。这些服务可以任何环境下运行，包括分布式环境，也包括开发人员自己的笔记本电脑以及各种托管平台。  

## spring cloud 断路器的作用是什么？

在Spring Cloud中使用了Hystrix 来实现断路器的功能，断路器可以防止一个应用程序多次试图执行一个操作，即很可能失败，允许它继续而不等待故障恢复或者浪费 CPU 周期，而它确定该故障是持久的。断路器模式也使应用程序能够检测故障是否已经解决，如果问题似乎已经得到纠正，应用程序可以尝试调用操作。  

断路器增加了稳定性和灵活性，以一个系统，提供稳定性，而系统从故障中恢复，并尽量减少此故障的对性能的影响。它可以帮助快速地拒绝对一个操作，即很可能失败，而不是等待操作超时（或者不返回）的请求，以保持系统的响应时间。如果断路器提高每次改变状态的时间的事件，该信息可以被用来监测由断路器保护系统的部件的健康状况，或以提醒管理员当断路器跳闸，以在打开状态。  

## spring cloud 的核心组件有哪些？

1. 服务发现——Netflix Eureka  
一个RESTful服务，用来定位运行在AWS地区（Region）中的中间层服务。由两个组件组成：Eureka服务器和Eureka客户端。Eureka服务器用作服务注册服务器。Eureka客户端是一个java客户端，用来简化与服务器的交互、作为轮询负载均衡器，并提供服务的故障切换支持。Netflix在其生产环境中使用的是另外的客户端，它提供基于流量、资源利用率以及出错状态的加权负载均衡。  

2. 客服端负载均衡——Netflix Ribbon  
Ribbon，主要提供客户侧的软件负载均衡算法。Ribbon客户端组件提供一系列完善的配置选项，比如连接超时、重试、重试算法等。Ribbon内置可插拔、可定制的负载均衡组件。  

3. 断路器——Netflix Hystrix  
断路器可以防止一个应用程序多次试图执行一个操作，即很可能失败，允许它继续而不等待故障恢复或者浪费 CPU 周期，而它确定该故障是持久的。断路器模式也使应用程序能够检测故障是否已经解决。如果问题似乎已经得到纠正，应用程序可以尝试调用操作。  

4. 服务网关——Netflix Zuul  
类似nginx，反向代理的功能，不过netflix自己增加了一些配合其他组件的特性。  

5. 分布式配置——Spring Cloud Config  
这个还是静态的，得配合Spring Cloud Bus实现动态的配置更新。  

## 目录

* [Java基础](/java/javaBase.md)
* [容器](/java/collection.md)
* [线程](/java/thread.md)
* [反射](/java/reflection.md)
* [对象克隆](/java/cloneable.md)
* [JavaWeb](/java/javaWeb.md)
* [异常](/java/exception.md)
* [网络服务](/java/netWork.md)
* [设计模式](/java/designpattern.md)
* [Spring](/java/spring.md)
* [Spring MVC](/java/springMVC.md)
* [Spring Boot](/java/springBoot.md)
* [Spring Cloud](/java/springCloud.md)
* [Hibernate](/java/hibernate.md)
* [Mybatis](/java/mybatis.md)
* [队列](/java/mq.md)
* [Zookeeper](/java/zookeeper.md)
* [MySql](/java/mySql.md)
* [Redis](/java/redis.md)
* [Jvm](/java/jvm.md)
