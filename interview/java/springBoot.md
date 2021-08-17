# Spring Boot

## 什么是 spring boot？

在Spring框架这个大家族中，产生了很多衍生框架，比如 Spring、SpringMvc框架等，Spring的核心内容在于控制反转(IOC)和依赖注入(DI),所谓控制反转并非是一种技术，而是一种思想，在操作方面是指在spring配置文件中创建\<bean>，依赖注入即为由spring容器为应用程序的某个对象提供资源，比如 引用对象、常量数据等。  

SpringBoot是一个框架，一种全新的编程规范，他的产生简化了框架的使用，所谓简化是指简化了Spring众多框架中所需的大量且繁琐的配置文件，所以 SpringBoot是一个服务于框架的框架，服务范围是简化配置文件。  

## 为什么要用 spring boot？

Spring Boot使编码变简单  
Spring Boot使配置变简单  
Spring Boot使部署变简单  
Spring Boot使监控变简单  
Spring的不足  

## spring boot 核心配置文件是什么？

Spring Boot提供了两种常用的配置文件：  
properties文件  
yml文件  

## spring boot 配置文件有哪几种类型？它们有什么区别？  

Spring Boot提供了两种常用的配置文件，分别是properties文件和yml文件。相对于properties文件而言，yml文件更年轻，也有很多的坑。可谓成也萧何败萧何，yml通过空格来确定层级关系，使配置文件结构跟清晰，但也会因为微不足道的空格而破坏了层级关系。  

## spring boot 有哪些方式可以实现热部署？

SpringBoot热部署实现有两种方式：
1. 使用spring loaded
在项目中添加如下代码：

```xml
<build>
        <plugins>
            <plugin>
                <!-- springBoot编译插件-->
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <dependencies>
                    <!-- spring热部署 -->
                    <!-- 该依赖在此处下载不下来，可以放置在build标签外部下载完成后再粘贴进plugin中 -->
                    <dependency>
                        <groupId>org.springframework</groupId>
                        <artifactId>springloaded</artifactId>
                        <version>1.2.6.RELEASE</version>
                    </dependency>
                </dependencies>
            </plugin>
        </plugins>
    </build>
```

添加完毕后需要使用mvn指令运行：  
首先找到IDEA中的Edit configurations ,然后进行如下操作：（点击左上角的"+",然后选择maven将出现右侧面板，在红色划线部位输入如图所示指令，你可以为该指令命名(此处命名为MvnSpringBootRun)）  

![图片17][图片17]

点击保存将会在IDEA项目运行部位出现，点击绿色箭头运行即可  

![图片18][图片18]

2. 使用spring-boot-devtools  
在项目的pom文件中添加依赖：

```xml
 <!--热部署jar-->
 <dependency>
     <groupId>org.springframework.boot</groupId>
     <artifactId>spring-boot-devtools</artifactId>
 </dependency>
```

然后：使用 shift+ctrl+alt+"/" （IDEA中的快捷键） 选择"Registry" 然后勾选 compiler.automake.allow.when.app.running  

## jpa 和 hibernate 有什么区别？

JPA Java Persistence API，是Java EE 5的标准ORM接口，也是ejb3规范的一部分。  
Hibernate，当今很流行的ORM框架，是JPA的一个实现，但是其功能是JPA的超集。  
JPA和Hibernate之间的关系，可以简单的理解为JPA是标准接口，Hibernate是实现。那么Hibernate是如何实现与JPA的这种关系的呢。Hibernate主要是通过三个组件来实现的，及hibernate-annotation、hibernate-entitymanager和hibernate-core。  
hibernate-annotation是Hibernate支持annotation方式配置的基础，它包括了标准的JPA annotation以及Hibernate自身特殊功能的annotation。  
hibernate-core是Hibernate的核心实现，提供了Hibernate所有的核心功能。  
hibernate-entitymanager实现了标准的JPA，可以把它看成hibernate-core和JPA之间的适配器，它并不直接提供ORM的功能，而是对hibernate-core进行封装，使得Hibernate符合JPA的规范。  



[图片17]:https://picabstract-preview-ftn.weiyun.com/ftn_pic_abs_v3/82985903d8202dc128dd81de3cb1e9779120f8da9bef38d0ac6df234453c49bffb34724b3059d0a95105de2c8dc82c7f?pictype=scale&from=30113&version=3.3.3.3&uin=495869333&fname=Image%2017.png&size=750
[图片18]:https://picabstract-preview-ftn.weiyun.com/ftn_pic_abs_v3/2dfee76b58864a59b2285b236c7f0fa5905d685687e61b5ca1284b4db35b22da465a22f4ba3e79032ada8b5fbf87f813?pictype=scale&from=30113&version=3.3.3.3&uin=495869333&fname=Image%2018.png&size=750