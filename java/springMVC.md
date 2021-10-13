
# Spring MVC

## 说一下 spring mvc 运行流程？

Spring MVC运行流程图：

![Spring MVC运行流程图][Spring MVC运行流程图]

Spring运行流程描述：
1. 用户向服务器发送请求，请求被Spring 前端控制Servelt DispatcherServlet捕获；
2. DispatcherServlet对请求URL进行解析，得到请求资源标识符（URI）。然后根据该URI，调用HandlerMapping获得该Handler配置的所有相关的对象（包括Handler对象以及Handler对象对应的拦截器），最后以HandlerExecutionChain对象的形式返回；
3. DispatcherServlet 根据获得的Handler，选择一个合适的HandlerAdapter；（附注：如果成功获得HandlerAdapter后，此时将开始执行拦截器的preHandler(...)方法）
4.  提取Request中的模型数据，填充Handler入参，开始执行Handler（Controller)。 在填充Handler的入参过程中，根据你的配置，Spring将帮你做一些额外的工作：  
HttpMessageConveter： 将请求消息（如Json、xml等数据）转换成一个对象，将对象转换为指定的响应信息  
数据转换：对请求消息进行数据转换。如String转换成Integer、Double等  
数据根式化：对请求消息进行数据格式化。 如将字符串转换成格式化数字或格式化日期等  
数据验证： 验证数据的有效性（长度、格式等），验证结果存储到BindingResult或Error中  
5.  Handler执行完成后，向DispatcherServlet 返回一个ModelAndView对象；  
6.  根据返回的ModelAndView，选择一个适合的ViewResolver（必须是已经注册到Spring容器中的ViewResolver)返回给DispatcherServlet ；  
7. ViewResolver 结合Model和View，来渲染视图；  
8. 将渲染结果返回给客户端。  

## spring mvc 有哪些组件？

Spring MVC的核心组件：  
DispatcherServlet：中央控制器，把请求给转发到具体的控制类  
Controller：具体处理请求的控制器  
HandlerMapping：映射处理器，负责映射中央处理器转发给controller时的映射策略  
ModelAndView：服务层返回的数据和视图层的封装类  
ViewResolver：视图解析器，解析具体的视图  
Interceptors ：拦截器，负责拦截我们定义的请求然后做处理工作  

## @Controller和@RestController的区别?

1. Controller, RestController的共同点
都是用来表示Spring某个类的是否可以接收HTTP请求

2.  Controller, RestController的不同点  
@Controller标识一个Spring类是Spring MVC controller处理器  
@RestController：@RestController是@Controller和@ResponseBody的结合体，两个标注合并起来的作用。

3、如果只是使用@RestController注解Controller，则Controller中的方法无法返回jsp页面，配置的视图解析器InternalResourceViewResolver不起作用，返回的内容就是Return 里的内容。  
例如：本来应该到success.jsp页面的，则其显示success.

4、如果需要返回到指定页面，则需要用 @Controller配合视图解析器InternalResourceViewResolver才行。

5、如果需要返回JSON，XML或自定义mediaType内容到页面，则需要在对应的方法上加上@ResponseBody注解。

## @RequestBody @ResponseBody 的作用
### @RequestBody

1. 作用：
该注解用于读取 Request 请求的 body 部分数据，使用系统默认配置的 HttpMessageConverter 进行解析，然后把相应的数据绑定到要返回的对象上；
再把 HttpMessageConverter 返回的对象数据绑定到 controller 中方法的参数上。
2. 使用时机：
GET、POST方式提交时， 根据 request header Content-Type 的值来判断:
application/x-www-form-urlencoded：可选（即非必须，因为这种情况的数据 @RequestParam, @ModelAttribute 也可以处理，当然@RequestBody也能处理）；
multipart/form-data：不能处理（即使用@RequestBody不能处理这种格式的数据）；
其他格式：必须（其他格式包括application/json, application/xml等。这些格式的数据，必须使用@RequestBody来处理）；
PUT 方式提交时， 根据request header Content-Type的值来判断:
application/x-www-form-urlencoded：必须；
multipart/form-data：不能处理；
其他格式：必须；

作者：希希里之海
链接：https://www.jianshu.com/p/64b22da6c9ab
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

### @ResponseBody

1. 作用：
该注解用于将 Controller 的方法返回的对象，通过适当的 HttpMessageConverter 转换为指定格式后，写入到 Response 对象的body 数据区。

2. 使用时机：
返回的数据不是 html 标签的页面，而是其他某种格式的数据时（如 json、xml 等）使用。

作者：希希里之海
链接：https://www.jianshu.com/p/64b22da6c9ab
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

## @RequestMapping 的作用是什么？

RequestMapping是一个用来处理请求地址映射的注解，可用于类或方法上。用于类上，表示类中的所有响应请求的方法都是以该地址作为父路径。  

RequestMapping注解有六个属性，下面我们把她分成三类进行说明。

value， method：  
value：指定请求的实际地址，指定的地址可以是URI Template 模式（后面将会说明）；  
method：指定请求的method类型， GET、POST、PUT、DELETE等；  

consumes，produces  
consumes：指定处理请求的提交内容类型（Content-Type），例如application/json, text/html；  
produces：指定返回的内容类型，仅当request请求头中的(Accept)类型中包含该指定类型才返回；  

params，headers  
params： 指定request中必须包含某些参数值是，才让该方法处理。  
headers：指定request中必须包含某些指定的header值，才能让该方法处理请求。  

## @Autowired 的作用是什么？

《@Autowired用法详解》：blog.csdn.net/u013257679/article/details/52295106  

首先要知道另一个东西，default-autowire，它是在xml文件中进行配置的，可以设置为byName、byType、constructor和autodetect；比如byName，不用显式的在bean中写出依赖的对象，它会自动的匹配其它bean中id名与本bean的set**相同的，并自动装载。

@Autowired是用在JavaBean中的注解，通过byType形式，用来给指定的字段或方法注入所需的外部资源。
两者的功能是一样的，就是能减少或者消除属性或构造器参数的设置，只是配置地方不一样而已。
autowire四种模式的区别：

| 模式 | 说明 |  
| :----: | :----: |
| no | |
| byName | 根据属性名自动装配。此选项将检查容器并根据名字查找与属性完全一致的bean, 并将其与属性自动装配。例如，再bean中将autowire设置为 by name, 而该 bean 包含 master 属性（同时提供setMaster(..)方法），Spring 就会查找名为 master 的 bean 定义，并且用它来装配给master属性 |
| byType | 如果容器中存在一个与制定属性类型相同的 bean,那么将与该属性自动装配。入股哦存在多个该类型的 bean，那么将会抛出异常，并指出不能使用 byType 方式进行自动装配。若没有找到相匹配的 bean，则什么事都不发生，属性也不会被设置。如果你不希望这样，那么可以通过设置 dependency-check="object" 让Spring 抛出异常 |
| constructor | 与 byType 的方式类似，不同指出在于它应用于构造器参数。如果在容器中没有找到与构造器参数类型一直的 bean，那么将会抛出异常 |
| autodetect | 通过 bean 类的自省机制(introspection)来决定是使用 constructor 还是 byType 方式进行自动装配。如果发现默认的构造器，那么将使用 byType 方式 |  

先看一下bean实例化和@Autowired装配过程：
一切都是从bean工厂的getBean方法开始的，一旦该方法调用总会返回一个bean实例，无论当前是否存在，不存在就实例化一个并装配，否则直接返回。（Spring MVC是在什么时候开始执行bean的实例化过程的呢？其实就在组件扫描完成之后）

实例化和装配过程中会多次递归调用getBean方法来解决类之间的依赖。

Spring几乎考虑了所有可能性，所以方法特别复杂但完整有条理。

@Autowired最终是根据类型来查找和装配元素的，但是我们设置了\<beans default-autowire="byName"/>后会影响最终的类型匹配查找。因为在前面有根据BeanDefinition的autowire类型设置PropertyValue值得一步，其中会有新实例的创建和注册。就是那个autowireByName方法。

下面通过@Autowired来说明一下用法

Setter 方法中的 @Autowired
你可以在 JavaBean中的 setter 方法中使用 @Autowired 注解。当 Spring遇到一个在 setter 方法中使用的 @Autowired 注解，它会在方法中执行 byType 自动装配。
这里是 TextEditor.java 文件的内容：

```java
package com.tutorialspoint;
import org.springframework.beans.factory.annotation.Autowired;
public class TextEditor {
   private SpellChecker spellChecker;
   @Autowired
   public void setSpellChecker( SpellChecker spellChecker ){
      this.spellChecker = spellChecker;
   }
   public SpellChecker getSpellChecker( ) {
      return spellChecker;
   }
   public void spellCheck() {
      spellChecker.checkSpelling();
   }
}
```

下面是另一个依赖的类文件 SpellChecker.java 的内容：

```java
package com.tutorialspoint;
public class SpellChecker {
   public SpellChecker(){
      System.out.println("Inside SpellChecker constructor." );
   }
   public void checkSpelling(){
      System.out.println("Inside checkSpelling." );
   }  
}
```

下面是 MainApp.java 文件的内容：

```java
package com.tutorialspoint;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class MainApp {
   public static void main(String[] args) {
      ApplicationContext context = new ClassPathXmlApplicationContext("Beans.xml");
      TextEditor te = (TextEditor) context.getBean("textEditor");
      te.spellCheck();
   }
}
```

下面是配置文件 Beans.xml：

```xml
<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context-3.0.xsd">

   <context:annotation-config/>

   <!-- Definition for textEditor bean without constructor-arg  -->
   <bean id="textEditor" class="com.tutorialspoint.TextEditor">
   </bean>

   <!-- Definition for spellChecker bean -->
   <bean id="spellChecker" class="com.tutorialspoint.SpellChecker">
   </bean>

</beans>
```

一旦你已经完成的创建了源文件和 bean 配置文件，让我们运行一下应用程序。如果你的应用程序一切都正常的话，这将会输出以下消息：

    Inside SpellChecker constructor.
    Inside checkSpelling.

属性中的 @Autowired
你可以在属性中使用 @Autowired 注解来除去 setter 方法。当时使用 为自动连接属性传递的时候，Spring 会将这些传递过来的值或者引用自动分配给那些属性。所以利用在属性中 @Autowired 的用法，你的 TextEditor.java 文件将变成如下所示：

```java
package com.tutorialspoint;
import org.springframework.beans.factory.annotation.Autowired;
public class TextEditor {
   @Autowired
   private SpellChecker spellChecker;
   public TextEditor() {
      System.out.println("Inside TextEditor constructor." );
   }  
   public SpellChecker getSpellChecker( ){
      return spellChecker;
   }  
   public void spellCheck(){
      spellChecker.checkSpelling();
   }
}
```

下面是配置文件 Beans.xml：

```xml
<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context-3.0.xsd">

   <context:annotation-config/>

   <!-- Definition for textEditor bean -->
   <bean id="textEditor" class="com.tutorialspoint.TextEditor">
   </bean>

   <!-- Definition for spellChecker bean -->
   <bean id="spellChecker" class="com.tutorialspoint.SpellChecker">
   </bean>

</beans>
```

一旦你在源文件和 bean 配置文件中完成了上面两处改变，让我们运行一下应用程序。如果你的应用程序一切都正常的话，这将会输出以下消息：

    Inside TextEditor constructor.
    Inside SpellChecker constructor.
    Inside checkSpelling.

构造函数中的 @Autowired
你也可以在构造函数中使用 @Autowired。一个构造函数 @Autowired 说明当创建 bean 时，即使在 XML 文件中没有使用 元素配置 bean ，构造函数也会被自动连接。让我们检查一下下面的示例。
这里是 TextEditor.java 文件的内容：

```java
package com.tutorialspoint;
import org.springframework.beans.factory.annotation.Autowired;
public class TextEditor {
   private SpellChecker spellChecker;
   @Autowired
   public TextEditor(SpellChecker spellChecker){
      System.out.println("Inside TextEditor constructor." );
      this.spellChecker = spellChecker;
   }
   public void spellCheck(){
      spellChecker.checkSpelling();
   }
}
```

下面是配置文件 Beans.xml：

```xml
<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context-3.0.xsd">

   <context:annotation-config/>

   <!-- Definition for textEditor bean without constructor-arg  -->
   <bean id="textEditor" class="com.tutorialspoint.TextEditor">
   </bean>

   <!-- Definition for spellChecker bean -->
   <bean id="spellChecker" class="com.tutorialspoint.SpellChecker">
   </bean>

</beans>
```

一旦你在源文件和 bean 配置文件中完成了上面两处改变，让我们运行一下应用程序。如果你的应用程序一切都正常的话，这将会输出以下消息：

    Inside TextEditor constructor.
    Inside SpellChecker constructor.
    Inside checkSpelling.

@Autowired 的（required=false）选项  
默认情况下，@Autowired 注解意味着依赖是必须的，它类似于 @Required 注解，然而，你可以使用 @Autowired 的 （required=false） 选项关闭默认行为。  
即使你不为 age 属性传递任何参数，下面的示例也会成功运行，但是对于 name 属性则需要一个参数。你可以自己尝试一下这个示例，因为除了只有 Student.java 文件被修改以外，它和 @Required 注解示例是相似的。  

```java
package com.tutorialspoint;
import org.springframework.beans.factory.annotation.Autowired;
public class Student {
   private Integer age;
   private String name;
   @Autowired(required=false)
   public void setAge(Integer age) {
      this.age = age;
   }  
   public Integer getAge() {
      return age;
   }
   @Autowired
   public void setName(String name) {
      this.name = name;
   }   
   public String getName() {
      return name;
   }
}
```

————————————————
版权声明：本文为CSDN博主「阿文施瓦辛格」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/u013257679/article/details/52295106

[Spring MVC运行流程图]:https://picabstract-preview-ftn.weiyun.com/ftn_pic_abs_v3/d1f3cfcfacc0c82aa4f6870eaca54d649c6b8358aaff78b9ffa1413397124e3f1c0ec0ad425d6fe651ce7a7e1ee52520?pictype=scale&from=30113&version=3.3.3.3&uin=495869333&fname=springMVC%E8%BF%90%E8%A1%8C%E6%B5%81%E7%A8%8B.png&size=750


