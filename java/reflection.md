# 反射

## 什么是反射？
反射主要是指程序可以访问、检测和修改它本身状态或行为的一种能力  
Java反射：  
在Java运行时环境中，对于任意一个类，能否知道这个类有哪些属性和方法？对于任意一个对象，能否调用它的任意一个方法  
Java反射机制主要提供了以下功能：  
在运行时判断任意一个对象所属的类。  
在运行时构造任意一个类的对象。  
在运行时判断任意一个类所具有的成员变量和方法。  
在运行时调用任意一个对象的方法。  

## 什么是 java 序列化？什么情况下需要序列化？
简单说就是为了保存在内存中的各种对象的状态（也就是实例变量，不是方法），并且可以把保存的对象状态再读出来。虽然你可以用你自己的各种各样的方法来保存object states，但是Java给你提供一种应该比你自己好的保存对象状态的机制，那就是序列化。  
什么情况下需要序列化：  
1. 当你想把的内存中的对象状态保存到一个文件中或者数据库中时候；  
2. 当你想用套接字在网络上传送对象的时候；  
3. 当你想通过RMI传输对象的时候；  

## 动态代理是什么？有哪些应用？
动态代理：  
当想要给实现了某个接口的类中的方法，加一些额外的处理。比如说加日志，加事务等。可以给这个类创建一个代理，故名思议就是创建一个新的类，这个类不仅包含原来类方法的功能，而且还在原来的基础上添加了额外处理的新类。这个代理类并不是定义好的，是动态生成的。具有解耦意义，灵活，扩展性强。  
动态代理的应用：  
Spring的AOP  
加事务  
加权限  
加日志  

## 怎么实现动态代理？
首先必须定义一个接口，还要有一个InvocationHandler(将实现接口的类的对象传递给它)处理类。再有一个工具类Proxy(习惯性将其称为代理类，因为调用他的newInstance()可以产生代理对象,其实他只是一个产生代理对象的工具类）。利用到InvocationHandler，拼接代理类源码，将其编译生成代理类的二进制码，利用加载器加载，并将其实例化产生代理对象，最后返回。  

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
