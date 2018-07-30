---
layout: post
title:  "学习笔记之Spring基础配置"
date:   2016-11-28 19:41:00 +0800
categories: 学习笔记
tag: Spring
---

* content
{:toc}


# 《Spring Boot实战》

## Spring基础配置

----------

### Spring 四大原则

 1.使用POJO进行轻量级和最小侵入式开发；

>POJO（Plain Ordinary Java Object）简单的Java对象，实际就是普通JavaBeans，是为了避免和EJB混淆所创造的简称。
使用POJO名称是为了避免和EJB混淆起来, 而且简称比较直接. 其中有一些属性及其getter setter方法的类,没有业务逻辑，有时可以作为VO(value -object)或dto(Data Transform Object)来使用.当然,如果你有一个简单的运算属性也是可以的,但不允许有业务方法,也不能携带有connection之类的方法。

2.通过依赖注入和基于接口编程实现松耦合；

3.通过AOP和默认系统进行声明式编程；

4.使用AOP和模版(template)减少模式化代码；

### 依赖注入

>控制反转(Inversion of Control-IOC)、依赖注入(dependency injecttion-DI)

```
在Spring 环境中是等同概念，控制反转是通过依赖注入实现的。
依赖注入目的是为了解耦。以组合的方式替代继承。
Spring IoC容器(ApplicationContext)负责创建Bean,并通过容器将功能类Bean注入到你需要的Bean中。
```
Spring 提供了3种方式实现Bean的创建和管理依赖。

```
1.xml；
2.Java配置；
3.groovy配置。
```
#### 声明Bean的注解：
```
1.@Component 组件，没有明确的角色
2.@Service 在业务逻辑层(service层) 使用
3.@Repository 在数据访问层(dao层) 使用
4.@Controller 在展示层(MVC-->Spring MVC) 使用
```

#### 注入Bean的注解

```
1.@Autowired: Spring提供的注解；
2.@Inject: JSR-330提供的注解；
3.@Resource: JSR-250提供的注解。
注：JSR-330和JSR-250 是Java依赖注入标准  三个注解可以注解在set方法上或属性上
```
#### 配置类中常用注解

```
1.@Configuration 声明当前类是一个配置类；
2.@ComponentScan
自动扫描包名下所有使用@Service、@Component、@Repository和@Controller的类，并注册为Bean；
3.@EnableAspectJAutoProxy注解开启Spring对AspectJ代理的支持。
```

### Java 配置

Java配置是Spring 4.x 推荐的配置方式，可以完全替代xml配置；Java配置也是Spring Boot推荐的配置方式。

Java配置是通过@Configuration和@Bean 来实现。
```
@Configuration 声明当前类是一个配置类，相当于一个Spring配置的xml 文件。
@Bean 注解在方法上，声明当前方法的返回值为一个Bean。
```
### AOP

AOP:面向切面编程，相当于OOP面向对象编程。

>Spring的AOP目的是为了解耦。
<br/>Spring 支持AspectJ的注解式切面编程。

#### AspectJ

>AspectJ是一个面向切面的框架，它扩展了Java语言。AspectJ定义了AOP语法，所以它有一个专门的编译器用来生成遵守Java字节编码规范的Class文件。

1.使用@AspectJ 声明是一个切面。
<br/>2.使用@After、@Before、@Around 定义建言(advice),可直接将拦截规则(切点)作为参数。
<br/>3.其中@After、@Before、@Around参数的拦截规则为切点(PointCut),为了使切点复用，可使用@PointCut专门定义拦截规则，然后在@After、@Before、@Around参数中调用。
<br/>4.其中符合条件的每一个被拦截处为连接点(JoinPoint)。

#### Maven依赖

```
spring-aop
aspectjrt
aspectjweaver
```

#### 元注解
编写拦截规则的注解可能用到元注解，即 @Retention、 @Target、 @Document、 @Inherited四种。

>元注解是指注解的注解。

##### @Retention

>@Retention: 定义注解的保留策略

```
1.@Retention(RetentionPolicy.SOURCE)    //注解仅存在于源码中，在class字节码文件中不包含
2.@Retention(RetentionPolicy.CLASS)  // 默认的保留策略，注解会在class字节码文件中存在，但运行时无法获得，
3.@Retention(RetentionPolicy.RUNTIME)   // 注解会在class字节码文件中存在，在运行时可以通过反射获取到
```
##### @Target

>定义注解的作用目标 注：elementType 可以有多个，一个注解可以为类的，方法的，字段的等等

```bash
1.@Target(ElementType.TYPE) // 接口、类、枚举、注解
2.@Target(ElementType.FIELD)  // 字段、枚举的常量
3.@Target(ElementType.METHOD)  // 方法
4.@Target(ElementType.PARAMETER)  // 方法参数
5.@Target(ElementType.CONSTRUCTOR)   // 构造函数
6.@Target(ElementType.LOCAL_VARIABLE) // 局部变量
7.@Target(ElementType.ANNOTATION_TYPE) // 注解
8.@Target(ElementType.PACKAGE) / // 包
```

##### @Document

>@Document：说明该注解将被包含在javadoc中

##### @Inherited

>@Inherited：说明子类可以继承父类中的该注解

#### 拦截方式

##### 1.注解式拦截

>1)即在方法上方使用利用元注解编写的注解；
<br/>2)在切面类  @Pointcut("@annotation(xx.xxx.xxx)")
<br/>对有应用 xx.xxx.xxx 进行注解的方法进行横切面拦截 
<br/>@After、@Before、@Around方法中将自定义的注解取出

```
MethodSignature signature=(MethodSignature)joinPoint.getSignature();
Method method=signature.getMethod();
XX xx=method.getMethod(XX.class);//获得注解类
```
##### 2.方法规则式拦截

>主要通过表达式 execution定义切入点

###### 关于execution

>（* com.jettylee.service.*.*（..））中几个通配符的含义： 
<br/>|第一个 * —— 通配 随便率性返回值类型| 
<br/>|第二个 * —— 通配包com.evan.crm.service下的随便率性class| 
<br/>|第三个 * —— 通配包com.evan.crm.service下的随便率性class的随便率性办法| 
<br/>|第四个 .. —— 通配 办法可以有0个或多个参数|
```bash
MethodSignature signature=(MethodSignature)joinPoint.getSignature();
Method method=signature.getMethod();
System.out.println("方法规则式拦截,"+method.getName());
```




[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help