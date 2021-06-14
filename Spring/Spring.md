# 一.Spring概述

## ***1.初识：***

### **Java Web**

#### **--Servlet**

是一种Web服务器端编程技术。

是实现了特殊接口的Java类。

是作为来自 Web 浏览器或其他 HTTP 客户端的请求和 HTTP 服务器上的数据库或应用程序之间的中间层由支持Servlet的Web服务器调用和启动运行。

一个Servlet负责对应的一个或一组URL访问请求，并返回相应的响应内容。

#### --Jsp

特殊的servlet（Java）,通过jsp引擎将jsp转译成Servlet，逐渐淘汰的技术。

是能够在静态HTML页面中嵌入动态JAVA代码的技术。

它能实现的servlet都能实现，但servlet开发起来太繁琐。

类似的技术有ASP，PHP。



#### **Framework**

JAVA框架可以分为三层：表现层，业务层和物理层。框架又叫做开发中的半成品，它不能提供整个WEB应用程序的所有东西，但是有了框架，我们就可以集中精力进行业务逻辑的开发而不用去关心它的技术实现以及一些辅助的业务逻辑。大家熟知的Structs和Spring就是表现层和业务层框架的强力代表。



#### ***Java框架的演进：***

由JavaWeb技术: JSP+Servlet+JavaBean。

MVC三层架构。

![mvc](/Users/tsx/Desktop/img/mvc.png)

演变为基于JavaWeb的框架体系

最初是Struts（表现层）+ Spring（业务层） + Hibernate（持久层）

后来演变为Struts2 + Spring + Hibernate

再后来随着Spring的强大以及Struts漏洞上的等等问题，演变成为了Spring + SpringMVC + Hibernate/Mybatis 互联网这块比较常见的是Mybatis。

最近也慢慢演变为了Springboot + Mybatis。

从SSH到SSM只有spring经久不衰。

## 2.springframework

Spring--开发者的春天

Spring让Java编程对每个人都更快、更容易、更安全。Spring对速度、简单性和生产力的关注使其成为世界上最受欢迎的Java框架。它提供了在企业环境中接受 Java 语言所需的一切,，并支持 Groovy 和 Kotlin 作为 JVM 上的替代语言，并可根据应用程序的需要灵活地创建多种体系结构

他是一个开源框架，是为了简化企业开发而生的，使得开发变得更加优雅和简洁。

他是一个轻量级框架--相比于EJB开发,EJB是重量级框架（在使用的时候，过多的接口和依赖，侵入性强）

他是一个**IOC**和**AOP**的容器框架。



#### **优点**

1、Spring通过DI、AOP和消除样板式代码来简化企业级Java开发

2、低侵入式设计，代码的污染极低

3、Spring拥有一个构建在他之上的庞大生态圈

4、独立于各种应用服务器，基于Spring框架的应用，可以真正实现Write Once,Run Anywhere的承诺

5、Spring的IoC容器降低了业务对象替换的复杂性，提高了组件之间的解耦

6、Spring的AOP支持允许将一些通用任务如安全、事务、日志等进行集中式处理，从而提供了更好的复用

7、Spring的ORM和DAO提供了与第三方持久层框架的的良好整合，并简化了底层的数据库访问

8、Spring的高度开放性，并不强制应用完全依赖于Spring，开发者可自由选用Spring框架的部分或全部



**如何简化开发**

​		基于POJO的轻量级和最小侵入性编程

​		通过依赖注入和面向接口实现松耦合

​		基于切面和惯例进行声明式编程

​		通过切面和模板减少样板式代码



**Spring模块划分**

![spring-overview](/Users/tsx/Desktop/img/spring-overview.png)

模块解释：
Test:Spring的单元测试模块
Core Container:核心容器模块
AOP+Aspects:面向切面编程模块
Instrumentation:提供了class instrumentation支持和类加载器的实现来在特定的应用服务器上使用,几乎不用
Messaging:包括一系列的用来映射消息到方法的注解,几乎不用
Data Access/Integration:数据的获取/整合模块，包括了JDBC,ORM,OXM,JMS和事务模块
Web:提供面向web整合特性

#### Spring1.x

通过**xml文件配置bean**，随着项目的不断扩大，需要将xml配置分放到不同的配置文件中，需要频繁的在java类和xml配置文件中切换。

#### Spring2.x

随着JDK 1.5带来的注解支持，Spring2.x可以使用注解对**Bean进行申明和注入**（**spring2.5**），大大的减少了xml配置文件，同时也大大简化了项目的开发（应用的基本配置，如数据库配置，使用xml，业务的配置用注解）

#### Spring3.x到Spring4.x

从3.X版本开始使用Java配置方式【@Configuration @ComponentScan(basePackages="com.SpringBoot.javaConfig")】更清晰明了

4.x全面支持Java 8.0 Lambda表达式的使用，提供了对@Scheduled和@PropertySource重复注解的支持，提供了空指针终结者Optional，对核心容器进行增加：支持泛型的依赖注入、Map的依赖注入、Lazy延迟依赖的注入、List注入、Condition条件注解注入、对CGLib动态代理类进行了增强。支持groovy DSL定义bean。提供RestController注解和AsyncRest Template支持异步无阻塞请求

#### Spring5.X

5.x运行于java8之上，更新了核心容器，使用Kotlin进行函数式编程，提升了单元测试方面的能力。响应式编程模型。