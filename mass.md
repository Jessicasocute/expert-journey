# 一.`aop`

## 1.`xml`方式实现`aop`

1. 切面：切点 + 通知

2. 织入：告诉`spring`框架哪些方法（切点）需要进行哪些加强（前置、后置）

3. ``xml``配置

```java
<!--目标对象-->
<bean id="target" class="com.swpu.aop.Target"/>
<!--切面对象-->
<bean id="myAspect" class="com.swpu.aop.MyAspect"/>
<!--配置织入 哪些方法（切点）需要进行哪些增强（前置，后置）-->
<aop:config>
    <aop:aspect ref="myAspect">
        <!--切面：切点+通知-->
        <aop:before method="before" pointcut="execution(public void com.swpu.aop.Target.save())"/>
    </aop:aspect>
</aop:config>
```

4. 切点表达式：

`execution（【修饰符】 返回值类型 包名.类名.方法名（参数））`

![image-20230313200046408](C:\Users\25692\AppData\Roaming\Typora\typora-user-images\image-20230313200046408.png)

## 2.注解方式实现``aop``

1.使用@Aspect标注切面类

2.使用@通知注解标注通知方法

3.在配置文件中配置``aop``自动代理

```<aop:aspectj-autoproxy/>```

![image-20230313204101023](C:\Users\25692\AppData\Roaming\Typora\typora-user-images\image-20230313204101023.png)

# 二.自动装配的原理

1. `SpringBoot`启动时会加载大量的自动配置类
2. 我们看我们需要的功能有没有在`SpringBoot`默认写好的自动配置类当中
3. 我们再来看这个自动配置类中到底配置了哪些组件（只要我们要用的组件存在在其中，我们就不需要再手动配置了）
4. 给容器中自动配置类添加组件的时候，会从properties类中获取某些属性。我们只需要在配置文件中指定这些属性的值即可

# 三.`JDBC ` VS  `druid`

1.`JDBC`（Java Database Connectivity）是Java语言中用于连接和操作数据库的标准`API`。它提供了一种方法来连接到各种不同类型的数据库，执行`SQL`语句，处理事务等。

2.`Druid`是一个Java语言中的高性能开源连接池。它提供了与`JDBC`兼容的`API`，用于连接到各种不同类型的数据库，并通过复用连接来提高性能。

3.区别在于，`JDBC`是Java语言中的标准`API`，它只提供了一组接口和规范，没有实现。而Druid是实现了`JDBC` `API`的一个连接池，它提供了额外的功能，如**监控、性能优化和防御`SQL`注入**等。

4.因此，当你需要在Java应用程序中连接到数据库时，你需要使用`JDBC API`，但是当你需要在应用程序中使用连接池来提高性能时，你可以使用Druid或其他连接池库。

# 四.前端传回来参数 `@requestbody`是什么意思

​	在前端传递数据时，通常会使用` HTTP` 请求的正文部分（Body）来传递复杂的数据结构，比如 `JSON `格式的数据。使用 `@RequestBody` 注解可以让 Spring 自动将请求体中的数据**反序列化为 Java 对象**，从而方便后续的业务逻辑处理。

# 五.`LambdaQueryWrapper`和`QueryWrapper`

1.它们的主要区别在于构造查询条件的方式不同。`LambdaQueryWrapper`使用**Lambda表达式**构造查询条件，而`QueryWrapper`使用**字符串**构造查询条件。

2.具体来说，`LambdaQueryWrapper`使用`Java8`中的Lambda表达式构造查询条件，可以使用类型安全的方式构造查询条件，避免了手写字符串可能出现的拼写错误、大小写问题等。`LambdaQueryWrapper`的代码简洁易懂，使用Lambda表达式可以**避免写出容易出错的字符串拼接代码，提高代码的可读性和可维护性。**

3.而`QueryWrapper`则使用字符串构造查询条件，需要手写字符串，容易出现拼写错误、大小写问题等。但是，`QueryWrapper`更加灵活，可以自由地拼接各种查询条件，适用于一些特殊的查询需求。

4.除了构造查询条件的方式不同，`LambdaQueryWrapper`还有一些其他的优点。例如，`ambdaQueryWrapper`支持链式调用，可以方便地组合多个查询条件；`LambdaQueryWrapper`支持类型转换，可以自动将Java类型转换为数据库类型；`LambdaQueryWrapper`支持分页查询，可以方便地进行分页查询等。

# 六.路径匹配器`AntPathMatcher`

```java
AntPathMatcher matcher = new AntPathMatcher();
boolean match = matcher.match("/path/*", "/path/file.txt"); // 返回 true
```

在这个例子中，我们创建了一个 `AntPathMatcher` 对象，并使用 `match()` 方法来判断 `/path/file.txt` 是否符合 `/path/*` 的路径规则，如果匹配成功则返回 true。
