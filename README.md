# notebook

## 说明

这是一个私人Maredown笔记本，目前包含java部分笔记

## 规范

[Markdown](/interview/markdown.md)

## 站点

本文档支持以下站点访问：

[dyy-zhangyu](https://www.cnblogs.com/dyy-zhangyu/)

[gitee](https://gitee.com/sj_zhang/notebook.git)

[github](https://github.com/zhangconnor/notebook.git)

## 目录

### Java

* [Java基础](/interview/javaBase.md)
* [容器](/interview/collection.md)
* [线程](/interview/thread.md)
* [反射](/interview/reflection.md)
* [对象克隆](/interview/cloneable.md)
* [JavaWeb](/interview/javaWeb.md)
* [异常](/interview/exception.md)
* [网络服务](/interview/netWork.md)
* [设计模式](/interview/designpattern.md)
* [Spring](/interview/spring.md)
* [Hibernate](/interview/hibernate.md)
* [Mybatis](/interview/mybatis.md)
* [队列](/interview/mq.md)
* [Zookeeper](/interview/zookeeper.md)
* [MySql](/interview/mySql.md)
* [Redis](/interview/redis.md)
* [Jvm](/interview/jvm.md)

### Goland

## 临时笔记

### BIO、NIO、AIO 有什么区别？

BIO：Block IO 同步阻塞式 IO，就是我们平常使用的传统 IO，它的特点是模式简单使用方便，并发处理能力低。  
NIO：New IO 同步非阻塞 IO，是传统 IO 的升级，客户端和服务器端通过 Channel（通道）通讯，实现了多路复用。  
AIO：Asynchronous IO 是 NIO 的升级，也叫 NIO2，实现了异步非堵塞 IO ，异步 IO 的操作基于事件和回调机制。  

### Files的常用方法都有哪些？

Files.exists()：检测文件路径是否存在。  
Files.createFile()：创建文件。  
Files.createDirectory()：创建文件夹。  
Files.delete()：删除一个文件或目录。  
Files.copy()：复制文件。  
Files.move()：移动文件。  
Files.size()：查看文件个数。  
Files.read()：读取文件。  
Files.write()：写入文件。  





## 参考资料

每一个程序员都有一个梦想，梦想着能够进入阿里、腾讯、字节跳动、百度等一线互联网公司，由于身边的环境等原因，不知道 BAT 等一线互联网公司使用哪些技术？或者该如何去学习这些技术？或者我该去哪些获取这些技术资料？没关系，平头哥一站式服务，上面统统不是问题。平头哥整理了 BAT 等一线大厂的必备技能，并且帮你准备了对应的资料。对于整理出来的技术，如果你掌握的不牢固，那就赶快巩固，如果你还没有涉及，现在就立马学习起来吧。

> 文章很长，越到后面越精彩，如果文章对你有帮助，欢迎点赞转发一条龙服务

# 基础篇

## Java

* [菜鸟教程](https://www.runoob.com/java/java-tutorial.html)
* [Java SE 社区](https://www.oracle.com/technetwork/cn/java/javase/community/index.html)
* [JDK 8 中文手册](http://www.matools.com/api/java8)
* [Java入门第一季 慕课网](https://www.imooc.com/learn/85)
* [Java入门第二季 慕课网](https://www.imooc.com/learn/124)
* [Java入门第三季 慕课网](https://www.imooc.com/learn/110)
* [马士兵 Java 基础教程](http://www.bjsxt.com/2014/down_0425/13.html)
* [高淇 Java 300 集教程视频](https://www.bjsxt.com/down/9107.html)
* [小马哥一入Java深似海](https://segmentfault.com/n/1330000017785588)
* [Java核心技术36讲 极客时间](https://time.geekbang.org/column/intro/82)
* [尚硅谷 NIO 视频](https://www.bilibili.com/video/av44816144/)
* [尚硅谷 Java8新特性视频教程](https://www.bilibili.com/video/av21399242)
* Java核心技术卷II(书籍)
* Head First Java（中文版）(书籍)

## 代码规范

* [阿里巴巴 Java 开发手册](https://https://github.com/alibaba/p3c/)
* [effctive-java 第三版](https://sjsdfg.github.io/effective-java-3rd-chinese/#/README)
* [Google Java 编程风格指南](http://hawstein.com/2014/01/20/google-java-style/)
* [阿里巴巴 Java 代码规约扫描插件 P3C](https://github.com/alibaba/p3c)

## 编辑工具

* [Idea](https://www.jetbrains.com/idea/)
* [myeclipsecn](https://www.myeclipsecn.com/)
* [eclipse](https://www.eclipse.org/)
* [VS Code](https://code.visualstudio.com/)

## 数据结构与算法

* [Java 数据结构与算法视频教程全集](https://www.bilibili.com/video/av59600020/)
* [数据结构与算法之美 极客时间](https://time.geekbang.org/column/intro/126)
* [算法面试通关40讲(视频) 极客时间](https://time.geekbang.org/course/intro/130)
* [leetcode 中国](https://leetcode-cn.com/)
* [尚硅谷-韩顺平图解Java数据结构和算法](https://www.bilibili.com/video/av54029771/)
* Java数据结构和算法中文版（第二版）(书籍)

## 设计模式

* [Java 设计模式视频教程全集](https://www.bilibili.com/video/av59599696)
* [尚学堂设计模式](https://www.bjsxt.com/down/8754.html)
* [23个设计模式](https://www.bilibili.com/video/av24176315?from=search&amp;seid=8737394704280817861)
* [尚硅谷图解Java设计模式](https://www.bilibili.com/video/av57936239)
* 图解Java多线程设计模式(书籍)

## 多线程

* [菜鸟教程](https://www.runoob.com/java/java-multithreading.html)
* [慕课网 深入浅出Java 多线程](https://www.imooc.com/learn/202)
* [Java并发编程实战 极客时间](https://time.geekbang.org/column/intro/159)
* [尚硅谷 JUC 视频教程](https://www.bilibili.com/video/av21398578)
* [Java多线程编程实战 -- 高并发编程第一,二阶段](https://www.bilibili.com/video/av43529474)
* [Java多线程编程实战 -- 高并发编程第三阶段](https://www.bilibili.com/video/av43532833)
* Java多线程编程实战指南(核心篇)

## HttpClient

* [HttpClient 官网](https://hc.apache.org/)
* [Apache HttpClient 官方教程中文版](https://www.ctolib.com/topics-80581.html)
* [一头扎进HttpClient](http://www.java1234.com/a/yuanchuang/httpclient/)

## 性能优化

* 《Java性能优化权威指南》(书籍)
* 《大话java性能优化》(书籍)

# 数据库

## Mysql

* [MySQL 官网](https://www.mysql.com/)
* [MySQL 菜鸟教程](https://www.runoob.com/mysql/mysql-tutorial.html)
* [MySQL从入门到精通视频教程](https://www.bilibili.com/video/av19538278?from=search&amp;seid=4463927256593098191)
* [MySQL 论坛](https://bbs.csdn.net/forums/MySQL)
* [MySQL实战45讲 极客时间](https://time.geekbang.org/column/intro/139)
* [与MySQL的零距离接触 慕课网](https://www.imooc.com/learn/122)
* [数据库设计那些事 慕课网](https://www.imooc.com/learn/117)
* [性能优化之MySQL优化 慕课网](https://www.imooc.com/learn/194)
* [MySQL提升课程 全面讲解MySQL架构设计 慕课网](https://coding.imooc.com/class/49.html)
* [尚硅谷MySQL核心技术](https://www.bilibili.com/video/av21400736/)
* 高性能 MySQL (书籍)
* MySQL必知必会（书籍）

## Redis

* [Redis 菜鸟教程](https://www.runoob.com/redis/redis-tutorial.html)
* [Redis 官网](https://redis.io/)
* [Redis 中文网](http://www.redis.cn/)
* [Redis 中文教程](http://www.redis.com.cn/redis-tutorial)
* [Redis 在线测试](http://try.redis.io/)
* [Redis 命令参考](http://redisdoc.com/index.html)
* [千峰教育 2019最新Redis教程](https://www.bilibili.com/video/av49517046?from=search&amp;seid=16610152865250508889)
* [黑马教育 Redis视频教程](https://www.bilibili.com/video/av7950222?from=search&amp;seid=16610152865250508889)
* [尚硅谷 Redis视频](https://www.bilibili.com/video/av20974126)
* [Redis入门 慕课网](https://www.imooc.com/learn/839)
* [redis的入门与应用 慕课网](https://www.imooc.com/learn/809)
* redis实战(书籍)

## MOngodb

* [mongodb 官网](https://www.mongodb.com/)
* [mongodb 中文网](https://www.mongodb.org.cn/)
* [菜鸟教程 MongoDB 教程](https://www.runoob.com/mongodb/mongodb-tutorial.html)
* [MongoDB 教程](https://www.w3cschool.cn/mongodb/)
* [尚硅谷 MongoDB夯实基础视频](https://www.bilibili.com/video/av21989676?from=search&amp;seid=9070860896856801467)
* [慕课网 MongoDB视频集合](https://www.imooc.com/course/list?c=mongodb)
* [玩转MongoDB4.0(最新版) 从入门到实践 慕课网](https://coding.imooc.com/class/324.html)
* MongoDB权威指南 第2版(书籍)

# 网络协议

* [网络协议 TCP/IP 视频教程全集](https://www.bilibili.com/video/av59638344?from=search&amp;seid=8766142930495269590)
* [透视HTTP协议 极客时间](https://time.geekbang.org/column/intro/189)
* [趣谈网络协议 极客时间](https://time.geekbang.org/column/intro/85)
* 图解 HTTP(书籍)
* 图解TCP/IP_第5版(书籍)
* TCP-IP详解卷1：协议(书籍)

# Linux 系统

* [Linux性能优化实战 极客时间](https://time.geekbang.org/column/intro/140)
* [趣谈Linux操作系统 极客时间](https://time.geekbang.org/column/article/108227)
* [尚硅谷_韩顺平_Linux教程](https://www.bilibili.com/video/av21303002/)

# Java Web

## JDBC

* [JDBC 使用说明](https://www.runoob.com/w3cnote/jdbc-use-guide.html)
* [尚硅谷 JDBC 视频教程](https://www.bilibili.com/video/av21399547)
* [黑马程序员JDBC视频教程](https://www.bilibili.com/video/av7751581?from=search&amp;seid=2640253484566695421)
* [JDBC视频教程从入门到精通](https://www.bilibili.com/video/av34494390?from=search&amp;seid=2640253484566695421)

## Servlet

* [Servlet 菜鸟教程](https://www.runoob.com/servlet/servlet-tutorial.html)
* [w3cschool Servlet教程](https://www.w3cschool.cn/servlet/)
* [Servlet3.1规范翻译](https://www.iteye.com/blogs/subjects/Servlet-3-1)
* [【北京尚学堂·百战程序员】Servlet ](https://www.bilibili.com/video/av44919297)

## spring

* [spring 官网](https://spring.io/projects/spring-framework)
* [Spring Framework 5 中文文档](https://lfvepclr.gitbooks.io/spring-framework-5-doc-cn/content/)
* [w3cschool Spring 教程](https://www.w3cschool.cn/wkspring/)
* [IBM Spring 教程](https://www.ibm.com/developerworks/cn/java/wa-spring1/index.html)
* [Spring 视频教程全集](https://www.bilibili.com/video/av59570922)
* [玩转Spring全家桶(视频) 极客时间](https://time.geekbang.org/course/intro/156)
* [探秘Spring AOP 慕课网](https://www.imooc.com/learn/869)
* [Spring入门篇 慕课网](https://www.imooc.com/learn/196)
* [Spring MVC起步 慕课网](https://www.imooc.com/learn/47)
* [Spring事务管理 慕课网](https://www.imooc.com/learn/478)
* [轻松愉快之玩转SpringData 慕课网](https://www.imooc.com/learn/821)
* [尚硅谷首套_Spring4 视频教程](https://www.bilibili.com/video/av21335209/)
* [尚硅谷 Spring注解驱动开发视频教程](https://www.bilibili.com/video/av20967380)
* [尚硅谷 SpringMVC视频](https://www.bilibili.com/video/av21272240)
* [尚硅谷 Spring Data视频](https://www.bilibili.com/video/av21083608)
* [Spring事务管理机制视频](https://www.bilibili.com/video/av46130817)

## mybatis

* [mybatis 官网](http://www.mybatis.org)
* [mybatis3 中文文档](http://www.mybatis.org/mybatis-3/zh/index.html)
* [MyBatis-Plus入门 慕课网](https://www.imooc.com/learn/1130)
* [尚硅谷 MyBatis 视频教程](https://www.bilibili.com/video/av21272940)
* [千锋 Mybatis框架从入门到实战](https://www.bilibili.com/video/av43935832)
* MyBatis技术内幕(书籍)

## Hibernate

* [Hibernate 官网](https://hibernate.org/)
* [Hibernate中文手册](http://www.kubiji.cn/book/hibernate/)
* [w3cschool Hibernate 教程](https://www.w3cschool.cn/hibernate/)
* [极客学院 Hibernate 教程](http://wiki.jikexueyuan.com/project/hibernate/)
* [Hibernate入门这一篇就够了](https://segmentfault.com/a/1190000013568216)
* [尚硅谷 Hibernate4 视频教程](https://www.bilibili.com/video/av21335712)
* [千锋 Hibernate 视频教程](https://www.bilibili.com/video/av44756882)
* [黑马程序员Hibernate视频教程](https://www.bilibili.com/video/av7744375?from=search&amp;seid=14166178899669484642)
* [Hibernate5框架视频教程-Hibernate入门到实战](https://www.bilibili.com/video/av55231479?from=search&amp;seid=14166178899669484642)

## Jpa

* [Jpa 官网](https://spring.io/projects/spring-data-jpa)
* [Spring Data JPA 从入门到进阶系列教程](http://www.spring4all.com/article/500)
* [尚硅谷 JPA视频](https://www.bilibili.com/video/av21263089)
* [云课堂jpa视频教程](https://www.bilibili.com/video/av61454398?from=search&amp;seid=5754201681590662665)
* [黑马程序员jpa详解视频教程](https://www.bilibili.com/video/av7755689?from=search&amp;seid=5754201681590662665)

## SpringBoot

* [springboot 官网](https://spring.io/projects/spring-boot)
* [Spring Boot 中文文档](https://docshome.gitbooks.io/springboot/content/)
* [Spring Boot 中文索引](http://springboot.fun/)
* [IBM Spring Boot 基础](https://www.ibm.com/developerworks/cn/java/j-spring-boot-basics-perry/index.html)
* [程序猿DD Spring Boot基础教程](http://blog.didispace.com/Spring-Boot%E5%9F%BA%E7%A1%80%E6%95%99%E7%A8%8B/)
* [纯洁的微笑 Spring Boot基础教程](http://www.ityouknow.com/spring-boot)
* [尚硅谷好评如潮【SpringBoot】视频](https://www.bilibili.com/video/av20965295/)
* [Spring Boot进阶之Web进阶 慕课网](https://www.imooc.com/coursescore/810)
* [SpringBoot+MyBatis搭建迷你小程序 慕课网](https://www.imooc.com/learn/945)
* [Spring Boot热部署 慕课网](https://www.imooc.com/learn/915)
* [Java 微服务实践 - Spring Boot 系列](https://segmentfault.com/ls/1650000011063780)
* [小马哥 Spring Boot2.0深度实践之核心技术篇 慕课网](https://coding.imooc.com/class/252.html)
* [Spring Boot实战与原理分析视频课程](https://www.bilibili.com/video/av42150427)

## 文档工具

* [swagger 官网](https://swagger.io/)
* [SpringBoot 结合 Swagger 构建 Api Demo](https://juejin.im/post/5d4000b7f265da03e3695bc9)
* [Spring Boot中使用Swagger2构建强大的RESTful API文档](http://blog.didispace.com/springbootswagger2/)
* [在 Spring Boot 项目中使用 Swagger 文档](https://www.ibm.com/developerworks/cn/java/j-using-swagger-in-a-spring-boot-project/index.html)
* [一篇文章带你搞懂 SpringBoot与Swagger整合](https://blog.csdn.net/itguangit/article/details/78978296)

# JVM虚拟机

* [JVM 底层原理知识总结](https://github.com/doocs/jvm)
* [深入理解Java虚拟机（JVM性能调优+内存模型+虚拟机原理）](https://www.bilibili.com/video/av29502877?from=search&amp;seid=18098903232145604601)
* [深入理解JVM-张龙](https://www.bilibili.com/video/av47756459?from=search&amp;seid=18098903232145604601)
* [深入拆解Java虚拟机 极客时间](https://time.geekbang.org/column/article/41800)
* [2019最新JVM虚拟机面试必问全集](https://www.bilibili.com/video/av61408412?from=search&amp;seid=10256072510957459060)
* [尚学堂-JVM虚拟机深度讲解教程](https://www.bilibili.com/video/av47477945?from=search&amp;seid=10256072510957459060)
* [关于Jvm知识看这一篇就够了](https://zhuanlan.zhihu.com/p/34426768)
* 揭秘Java虚拟机：JVM设计原理与实现

# 消息中间件

## Kafka

* [Kafka 官网](https://kafka.apache.org/)
* [Kafka 中文网](http://kafka.apachecn.org/)
* [Kafka 中文手册](http://www.kubiji.cn/book/apache_kafka/)
* [w3cschool Apache Kafka 教程](https://www.w3cschool.cn/apache_kafka/)
* [尚硅谷 Kafka 视频教程](https://www.bilibili.com/video/av35354301)
* [Kafka从入门到精通](https://www.bilibili.com/video/av36607048?from=search&amp;seid=10247561166017399606)

## RabbitMQ

* [RabbitMQ 官网](https://www.rabbitmq.com/)
* [消息队列之 RabbitMQ](https://www.jianshu.com/p/79ca08116d57)
* [【朱小厮】RabbitMQ 源码解析](https://blog.csdn.net/u013256816/article/category/6532725/2)
* [RabbitMQ 实现原理与源码解析系统](http://www.iocoder.cn/RabbitMQ/good-collection/)
* [王磊 RabbitMQ系列文章](https://github.com/vipstone/rabbitmq-java)
* [纯洁的微笑 RabbitMQ 详解](http://www.ityouknow.com/springboot/2016/11/30/spring-boot-rabbitMQ.html)
* [RabbitMQ消息中间件极速入门与实战 慕课网](https://www.imooc.com/learn/1042)
* [RabbitMQ 入门到进阶](https://www.bilibili.com/video/av18997807?from=search&amp;seid=10858926357316740687)

## RocketMQ

* [RocketMQ 官网](https://rocketmq.apache.org/)
* [芋道源码 RocketMQ源码解析](http://www.iocoder.cn/categories/RocketMQ/)
* [十分钟入门RocketMQ](http://jm.taobao.org/2017/01/12/rocketmq-quick-start-in-10-minutes/)
* [RocketMQ 实战](https://www.bilibili.com/video/av42180586?from=search&amp;seid=13687488303558801963)

## ActiveMQ

* [ActiveMQ 官网](https://activemq.apache.org/)
* [尚硅谷消息中间件之ActiveMQ](https://www.bilibili.com/video/av55976700?from=search&amp;seid=10858926357316740687)
* [ActiveMQ入门和消息中间件](https://www.bilibili.com/video/av32390735?from=search&amp;seid=8676191738416183023)
* [ActiveMQ教程](https://my.oschina.net/Auhgnahz?tab=newest&amp;catalogId=3428475)

# 构建管理工具

## Maven

* [Maven 官网](https://maven.apache.org/)
* [Maven 中文手册](http://www.kubiji.cn/book/maven/)
* [Maven 菜鸟教程](https://www.runoob.com/maven/maven-tutorial.html)
* [项目管理利器——maven 慕课网](https://www.imooc.com/learn/443)
* [尚硅谷 Maven视频](https://www.bilibili.com/video/av21004567)

## Git

* [Git 官网](https://git-scm.com)
* [Git 中文手册](http://www.kubiji.cn/book/git/)
* [廖雪峰 Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
* [玩转Git三剑客 极客时间](https://time.geekbang.org/course/intro/145)
* [Git入门 慕课网](https://www.imooc.com/learn/1052)
* [尚硅谷_Git&amp;GitHub视频](https://www.bilibili.com/video/av24441039/)
* [千锋 Java版本控制实战教程](https://www.bilibili.com/video/av43936824)

## Svn

* [Svn 官网](https://subversion.apache.org/)
* [Svn 中文手册](http://www.kubiji.cn/book/svn/)
* [Svn 菜鸟教程](https://www.runoob.com/svn/svn-tutorial.html)
* [版本管理工具介绍---SVN篇 慕课网](https://www.imooc.com/learn/109)
* [尚硅谷 SVN 高级视频教程](https://www.bilibili.com/video/av27204378)

## Gradle

* [gradle 官网](https://gradle.org/)
* [Gradle 中文手册](http://www.kubiji.cn/book/gradle/)
* [Gradle学习系列](https://www.cnblogs.com/davenkin/tag/gradle/)
* [新一代构建工具gradle 慕课网](https://www.imooc.com/learn/833)
* [w3cschool gradle教程](https://www.w3cschool.cn/gradle/)

# 安全中间件

## Shiro

* [Shiro 官网](https://shiro.apache.org/)
* [跟我学Shiro](https://www.iteye.com/blogs/subjects/shiro)
* [Shiro安全框架【快速入门】就这一篇](https://zhuanlan.zhihu.com/p/54176956)
* [尚硅谷 Shiro视频](https://www.bilibili.com/video/av21260992)
* [千锋 Shiro 框架从入门到实战](https://www.bilibili.com/video/av43940441)

## Security

* [Security 官网](https://spring.io/projects/spring-security)
* [社区 Spring Security 从入门到进阶系列教程](http://www.spring4all.com/article/428)
* [Spring Security开发安全的REST服务 慕课网](https://coding.imooc.com/class/134.html)

# 搜索引擎中间件

## Lucene

* [Lucene 官网](https://lucene.apache.org/)
* [Lucene从入门到精通](https://www.bilibili.com/video/av57891048?from=search&amp;seid=14798257461831592466)
* [Lucene全文检索技术](https://www.bilibili.com/video/av60513286?from=search&amp;seid=5793175095784382853)
* [Lucene 实例教程](https://blog.csdn.net/ch656409110/article/category/1570275)
* 解密搜索引擎技术实战：Lucene&amp;Java精华版(第3版)

## Solr

* [solr 官网](https://lucene.apache.org/solr/)
* [Solr中国](https://www.solr.cc/blog/)
* [Solr官方中文文档](https://www.w3cschool.cn/solr_doc/)
* [Solr视频教程从入门到案例实战](https://www.bilibili.com/video/av34261318?from=search&amp;seid=2314333354843835443)
* [solr从入门到精通](https://www.bilibili.com/video/av35510289?from=search&amp;seid=2314333354843835443)

## ElasticSearch

* [ElasticSearch 中文社区](https://elasticsearch.cn/explore/category-2)
* [Elasticsearch 技术分析](https://www.cnblogs.com/jajian/category/1280015.html)
* [Elasticsearch核心技术与实战 极客时间](https://time.geekbang.org/course/intro/197)
* [ElasticSearch入门 慕课网](https://www.imooc.com/learn/889)
* [千锋Java ElasticSearch6入门教程](https://www.bilibili.com/video/av43957643)
* [Elasticsearch顶尖高手系列-快速入门篇](https://www.bilibili.com/video/av29521652?from=search&amp;seid=366095727202838043)

# 容器化技术

## docker

* [菜鸟教程](https://www.runoob.com/docker/docker-tutorial.html)
* [docker中文社区](http://www.docker.org.cn/)
* [Docker入坑教程【33集】](https://www.bilibili.com/video/av17854410?from=search&amp;seid=10026979048851310046)
* [尚硅谷 Docker视频教程](https://www.bilibili.com/video/av26993050)
* [尚硅谷】Docker核心技术](https://www.bilibili.com/video/av30010765/)
* [2018黑马docker容器技术+k8s集群技术](https://www.bilibili.com/video/av35847195?from=search&amp;seid=10026979048851310046)
* Docker实战(书籍)
* 深入浅出Docker(书籍)

## kubernetes

* [kubernetes中文社区](https://www.kubernetes.org.cn/k8s)
* [Kubernetes（K8s）从入门到精通](https://www.bilibili.com/video/av44264629?from=search&amp;seid=10612284828584367292)
* [kubernetes（k8s）教程](https://www.bilibili.com/video/av40743487?from=search&amp;seid=10612284828584367292)
* [一天入门 Kubernetes/K8S](https://www.bilibili.com/video/av49783277?from=search&amp;seid=10612284828584367292)
* [深入剖析Kubernetes 极客时间](https://time.geekbang.org/column/intro/116)
* Kubernetes权威指南(书籍)
* Kubernetes in Action中文版(书籍)

# 分布式服务架构

## SpringCloud

* [SpringCloud 官网](https://spring.io/projects/spring-cloud)
* [SpringCloud 中文网](http://springcloud.cc/)
* [Spring Cloud Alibaba](https://github.com/alibaba/spring-cloud-alibaba/blob/master/README-zh.md)
* [尚硅谷_SpringCloud（全）](https://www.bilibili.com/video/av22613028/)
* [千锋 SpringCloud 全套视频）](https://www.bilibili.com/video/av44311231)
* [Java 微服务实践 - Spring Cloud 系列](https://segmentfault.com/ls/1650000011386794)
* [微服务架构实战160讲(视频) 极客时间](https://time.geekbang.org/course/intro/84)
* [史上最简单的 SpringCloud 教程](https://blog.csdn.net/forezp/article/details/70148833)
* [Spring Cloud 中文索引](http://springcloud.fun/)

## Dubbo

* [dubbo 官网](https://dubbo.apache.org/zh-cn/)
* [尚硅谷 Dubbo 视频教程](https://www.bilibili.com/video/av30612478)
* [动力节点 Dubbo 视频教程](https://www.bilibili.com/video/av44712206)
* [分布式系统架构解决方案之Dubbo视频](https://www.bilibili.com/video/av42128740)
* [Dubbo分布式系统架构实战视频教程--基础篇](https://www.bilibili.com/video/av43387399)
* [Dubbo分布式系统架构实战视频教程--高级篇](https://www.bilibili.com/video/av43368464)
* [Dubbo分布式系统架构实战视频教程--高可用架构篇](https://www.bilibili.com/video/av43480823)

## 分库分表

* [shardingsphere 官网](https://shardingsphere.apache.org/index_zh.html)
* [MyCAT](https://github.com/MyCATApache/Mycat-Server)
* [cobar](https://github.com/alibaba/cobar)
* [Ctrip-DAL](https://github.com/ctripcorp/dal)
* [“分库分表" ？选型和流程要慎重，否则会失控](https://segmentfault.com/a/1190000017272697)

## Zookeeper

* [zookeeper 官网](https://zookeeper.apache.org/)
* [zookeeper 中文手册](http://www.kubiji.cn/book/zookeeper/ZOOKEEPERZhongWenShouCe/ZOOKEEPERGaiShu.html)
* [w3cschool zookeeper 教程](https://www.w3cschool.cn/zookeeper/)
* [漫画：什么是ZooKeeper？](https://juejin.im/post/5b037d5c518825426e024473)
* [可能是全网把 ZooKeeper 概念讲的最清楚的一篇文章](https://segmentfault.com/a/1190000016349824)
* [尚硅谷 Zookeeper 视频教程](https://www.bilibili.com/video/av32093417)

## Nginx

* [nginx 官网](http://nginx.org/)

* [nginx 菜鸟教程](https://www.runoob.com/w3cnote/nginx-setup-intro.html)

* [8分钟带你深入浅出搞懂Nginx](https://zhuanlan.zhihu.com/p/34943332)

* [Nginx 容器教程](http://www.ruanyifeng.com/blog/2018/02/nginx-docker.html)

* [Nginx核心知识100讲 极客时间](https://time.geekbang.org/course/intro/138)

* [Nginx 教程 尚学堂](https://www.bjsxt.com/down/3243.html)

## 定时任务框架

* [quartz](http://www.quartz-scheduler.org)
* [light-task-scheduler](https://github.com/ltsopensource/light-task-scheduler)
* [XXL-JOB](http://www.xuxueli.com/xxl-job/#/)
* [elasticjob](https://github.com/elasticjob/elastic-job-lite)
* [Saturn](https://github.com/vipshop/Saturn)
* [jobx](https://github.com/jobxhub/JobX)

## JSON Web Token

* [JWT 官网](https://jwt.io/introduction/)
* [JSON Web Token 入门教程](http://www.ruanyifeng.com/blog/2018/07/json_web_token-tutorial.html)
* [JWT 完整使用详解](https://learnku.com/articles/10885/full-use-of-jwt)
* [JWT 解码器](http://calebb.net/)

## OAuth

* [OAuth 官网](https://oauth.net/2/)
* [OAuth 2.0 的一个简单解释](http://www.ruanyifeng.com/blog/2019/04/oauth_design.html)
* [OAuth 2.0 的四种方式](http://www.ruanyifeng.com/blog/2019/04/oauth-grant-types.html)
* [GitHub OAuth 第三方登录示例教程](http://www.ruanyifeng.com/blog/2019/04/github-oauth.html)
* [10 分钟理解什么是 OAuth 2.0 协议](https://deepzz.com/post/what-is-oauth2-protocol.html)

## 分布式架构

* [从0开始学架构 极客时间](https://time.geekbang.org/column/intro/81)
* [亿级流量网站架构核心技术](https://www.iteye.com/blogs/subjects/as-core)
* 大型网站技术架构(书籍)
* 分布式服务框架：原理与实践(书籍)

# 面试相关

* [Java高频面试题-尚硅谷-Java面试题第一季](https://www.bilibili.com/video/av37602130/?spm_id_from=333.788.videocard.0)
* [尚硅谷 互联网大厂高频重点面试题（第2季）](https://www.bilibili.com/video/av48958673/)
* [尚硅谷面试技巧与就业指导](https://www.bilibili.com/video/av53785429)
* [Java工程师面试突击第1季（可能是史上最好的Java面试突击课程）](https://www.bilibili.com/video/av49561181/)
* 剑指offer(书籍)

> 如果有侵权，请及时联系，即删
