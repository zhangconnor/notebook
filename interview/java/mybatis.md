# Mybatis

## mybatis 中 #{}和 ${}的区别是什么？

    #{}是预编译处理，${}是字符串替换；  
    Mybatis在处理#{}时，会将sql中的#{}替换为?号，调用PreparedStatement的set方法来赋值；  
    Mybatis在处理${}时，就是把${}替换成变量的值；  
    使用#{}可以有效的防止SQL注入，提高系统安全性。  

## mybatis 有几种分页方式？

数组分页  
sql分页  
拦截器分页  
RowBounds分页

## mybatis 逻辑分页和物理分页的区别是什么？

物理分页速度上并不一定快于逻辑分页，逻辑分页速度上也并不一定快于物理分页。

物理分页总是优于逻辑分页：没有必要将属于数据库端的压力加诸到应用端来，就算速度上存在优势,然而其它性能上的优点足以弥补这个缺点。

## mybatis 是否支持延迟加载？延迟加载的原理是什么？

Mybatis仅支持association关联对象和collection关联集合对象的延迟加载，association指的就是一对一，collection指的就是一对多查询。在Mybatis配置文件中，可以配置是否启用延迟加载lazyLoadingEnabled=true|false。

它的原理是，使用CGLIB创建目标对象的代理对象，当调用目标方法时，进入拦截器方法，比如调用a.getB().getName()，拦截器invoke()方法发现a.getB()是null值，那么就会单独发送事先保存好的查询关联B对象的sql，把B查询上来，然后调用a.setB(b)，于是a的对象b属性就有值了，接着完成a.getB().getName()方法的调用。这就是延迟加载的基本原理。

当然了，不光是Mybatis，几乎所有的包括Hibernate，支持延迟加载的原理都是一样的。

## 说一下 mybatis 的一级缓存和二级缓存？

一级缓存: 基于 PerpetualCache 的 HashMap 本地缓存，其存储作用域为 Session，当 Session flush 或 close 之后，该 Session 中的所有 Cache 就将清空，默认打开一级缓存。

二级缓存与一级缓存其机制相同，默认也是采用 PerpetualCache，HashMap 存储，不同在于其存储作用域为 Mapper(Namespace)，并且可自定义存储源，如 Ehcache。默认不打开二级缓存，要开启二级缓存，使用二级缓存属性类需要实现Serializable序列化接口(可用来保存对象的状态),可在它的映射文件中配置\<cache/> ；

对于缓存数据更新机制，当某一个作用域(一级缓存 Session/二级缓存Namespaces)的进行了C/U/D 操作后，默认该作用域下所有 select 中的缓存将被 clear。

## mybatis 和 hibernate 的区别有哪些？  

1. Mybatis和hibernate不同，它不完全是一个ORM框架，因为MyBatis需要程序员自己编写Sql语句。

2. Mybatis直接编写原生态sql，可以严格控制sql执行性能，灵活度高，非常适合对关系数据模型要求不高的软件开发，因为这类软件需求变化频繁，一但需求变化要求迅速输出成果。但是灵活的前提是mybatis无法做到数据库无关性，如果需要实现支持多种数据库的软件，则需要自定义多套sql映射文件，工作量大。 

3. Hibernate对象/关系映射能力强，数据库无关性好，对于关系模型要求高的软件，如果用hibernate开发可以节省很多代码，提高效率。 

## mybatis 有哪些执行器（Executor）？

Mybatis有三种基本的执行器（Executor）：  
SimpleExecutor：每执行一次update或select，就开启一个Statement对象，用完立刻关闭Statement对象。  
ReuseExecutor：执行update或select，以sql作为key查找Statement对象，存在就使用，不存在就创建，用完后，不关闭Statement对象，而是放置于Map内，供下一次使用。简言之，就是重复使用Statement对象。  
BatchExecutor：执行update（没有select，JDBC批处理不支持select），将所有sql都添加到批处理中（addBatch()），等待统一执行（executeBatch()），它缓存了多个Statement对象，每个Statement对象都是addBatch()完毕后，等待逐一执行executeBatch()批处理。与JDBC批处理相同。  
## mybatis 分页插件的实现原理是什么？

分页插件的基本原理是使用Mybatis提供的插件接口，实现自定义插件，在插件的拦截方法内拦截待执行的sql，然后重写sql，根据dialect方言，添加对应的物理分页语句和物理分页参数。

## mybatis 如何编写一个自定义插件？

转自：blog.csdn.net/qq_30051265/article/details/80266434

Mybatis自定义插件针对Mybatis四大对象（Executor、StatementHandler 、ParameterHandler 、ResultSetHandler ）进行拦截，具体拦截方式为：  
Executor：拦截执行器的方法(log记录)  
StatementHandler ：拦截Sql语法构建的处理  
ParameterHandler ：拦截参数的处理  
ResultSetHandler ：拦截结果集的处理  

Mybatis自定义插件必须实现Interceptor接口：  

```java
public interface Interceptor {
    Object intercept(Invocation invocation) throws Throwable;
    Object plugin(Object target);
    void setProperties(Properties properties);
}
```

intercept方法：拦截器具体处理逻辑方法   
plugin方法：根据签名signatureMap生成动态代理对象   
setProperties方法：设置Properties属性  

自定义插件demo：  

```java
// ExamplePlugin.java
@Intercepts({@Signature(
  type= Executor.class,
  method = "update",
  args = {MappedStatement.class,Object.class})})
public class ExamplePlugin implements Interceptor {
  public Object intercept(Invocation invocation) throws Throwable {
  Object target = invocation.getTarget(); //被代理对象
  Method method = invocation.getMethod(); //代理方法
  Object[] args = invocation.getArgs(); //方法参数
  // do something ...... 方法拦截前执行代码块
  Object result = invocation.proceed();
  // do something .......方法拦截后执行代码块
  return result;
  }
  public Object plugin(Object target) {
    return Plugin.wrap(target, this);
  }
  public void setProperties(Properties properties) {
  }
}
```

一个@Intercepts可以配置多个@Signature，@Signature中的参数定义如下：   
type：表示拦截的类，这里是Executor的实现类；  
method：表示拦截的方法，这里是拦截Executor的update方法；  
args：表示方法参数。  


## mapper 常用标签有哪些

SQL语句标签 inster select delete update  
sql片段标签<sql>  
映射管理器resultMap  
动态语句标签 <where> <if> <set> <foreach>  
<choose><when></when><otherwise></otherwise></choose>条件判断标签组

### SQL语句标签 inster select delete update  
需要配置的属性：id=”xxxx” >>> 表示此段sql执行语句的唯一标识，也是接口的方法名称【必须一致才能找到】  
parameterType=”” >>>表示该sql语句中需要传入的参数， 类型要与对应的接口方法的类型一致【可选】  
resultMap=“ ”>>> 定义出参，调用已定义的<resultMap>映射管理器的id值  
resultType=“ ”>>>定义出参，匹配普通java类型或自定义的pojo【出参类型若不指定，将为语句类型默认类型，如<insert>语句返回值为int】  

p.s： 至于为何<insert><delete><update> 语句的返回值类型为什么是int，有过JDBC操作经验的朋友可能会有印象，增删改操作实际上返回的是操作的条数。而Mybatis框架本身是基于JDBC的，所以此处也沿袭这种返回值类型。  

传参和取值：mapper.xml 的灵活性还体现在SQL执行语句可以传参，参数类型通过parameterType= “” 定义  
取值方式1：#{value jdbcType = valuetype}：jdbcType 表示该属性的数据类型在数据库中对应的类型，如 #{user jdbcType=varchar} 等价于 String username；  
取值方式2：{value } :&nbsp;<span style="color:#cc0000;"><strong>这种方式不建议大量使用</strong></span>，可能会发送sql注入而导致安全性问题。一般该取值方式可用在非经常变化的值上，如orderby{columnName}；  

### sql片段标签<sql>  
通过该标签可定义能复用的sql语句片段，在执行sql语句标签中直接引用即可。这样既可以提高编码效率，还能有效简化代码，提高可读性  
需要配置的属性：id=”” >>>表示需要改sql语句片段的唯一标识  
引用：通过<include refid=”” />标签引用，refid=”” 中的值指向需要引用的<sql>中的id=“”属性

### 映射管理器resultMap  
映射管理器，是Mybatis中最强大的工具，使用其可以进行实体类之间的关系，并管理结果和实体类间的映射关系  
需要配置的属性：<resultMap id=”  ” type=”  ”></resutlMap>   id=” “>>>表示这个映射管理器的唯一标识，外部通过该值引用； type = ” “>>> 表示需要映射的实体类；  
需要配置的参数：<id column = ” ” property= ” ” />    <id>标签指的是：结果集中结果唯一的列【column】 和 实体属性【property】的映射关系，注意：<id>标签管理的列未必是主键列，需要根据具体需求指定；  
<result column= ” ” property=” ” />  <result>标签指的是：结果集中普通列【column】 和 实体属性【property】的映射关系；  
需要维护的关系：所谓关系维护是值在主表查询时将其关联子表的结果也查询出来

一对一关系<assocation property = ” ” javaType=” “>   property = “ ” 被维护实体在宿主实体中的属性名，javaType = ” ” 被维护实体的类型  
在resultMap映射管理器中，通过<association> 进行了维护，也就是在查询Orderitem对象时，可以把关联的Product对象的信息也查询出来  
一对多关系的维护<collection property=” ” ofType=” “> property = “ ” 被维护实体在宿主实体中的属性名 ，ofType=“ ”是被维护方在宿主类中集合泛型限定类型  
【由于在一对多关系中，多的一放是以List形式存在，因此ofType的值取用Lsit<?> 的泛型对象类型】

在resultMap 中需要注意两点：  
关联关系的维护可以根据实体类之间的实际情况进行嵌套维护
关于出现重复列名的处理：在实际操作过程中，查询到的结果可能会出现相同的列名，这样会对映射到实体属性带来影响甚至出现报错，那么对待这个问题可以通过对列取别名的方式处理
