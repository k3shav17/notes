# Spring Framework

- Spring is a frame work, which is  free, open source and lightweight.
  - Which provides patterns and structures to manage the objects life cycle and dependencies for the components and services in the code through dependency injection and application context.

- Spring can do a lot of things, so we have to exactly say what we want to do using it, it does need a lot of configurations to setup.
  - Spring boot is different, it enables us achieve auto configuration.
  - It is convention over configuration, means we can focus on the code part and spring boot takes care of the configuration part.

 > maven is a build and dependency providing tool

- What is a framework?
  - Framework is a combination or set of classes and interfaces which provide ready made architecture to simplify the developing process.

- Why to use spring?
 Spring is a free and open source framework which is lightweight and is an alternative to the heavier enterprise java technologies such as EJB. Spring address the complexity of enterprise application development, by providing easy data access, Srping MVC, transaction management and security. Spring framework simplifies the Java development. It is lightweight because it is developed using the POJO. POJO is Plain Old Java Object, it means an object of a class without any bounded restrictions with any framework.

- What is Dependency Injection?

  - Dependency is a term used to say that how a software depends or relise on other software.
  - Dependency or coupling are the terms used. Coupling is of two types Loose coupling and tight coupling.
  - Spring framework provides us a way to achieve loose coupling through dependency injection.
  - The way spring acheives dependency injection is, Spring is a container of beans. It is similar to servlet container, where a servlet container creates the objects for interfaces or classes that are declared in the servlet. The servlet  container takes care of the object creation.
  - Similarly spring is also a container but of beans where we can have any no of objects in the container and spring will take care of instantiations, lifecycles and destructions of the objects.

- What is Dependency injection?
  - First of all, what is dependency? Consider two classes Class A and Class B, if Class A wants to use the functionalities of Class B to run, then the Class A is said to Dependent on Class B.
  
  - In java, if we want to use the methods of other class, we have to create the object of that class and then we can use the methods.
  - Dependency injection means transferring the task of creating the objects to some one else and directly using the dependencies.

- Why do i need Dependency injection?
  - Dependecy Injection is like a middle man who creates the preferred objects and provides it to class, it makes our class independent of creating the objects  of dependencies.
  - Dependency injection is a way of acheiving IoC, where IoC is a concept which states that there is no need to create objects manually, instead describe how they should be created.
  - Spring frame work provides dependecy injection.

> Benefits of Dependency Injection

1. It helps reduce the boiler plate code, as initializing the dependencies is done by the injector component
2. Extending the application becomes easier.
3. Helps enabling loose coupling.

> Different types of dependency injections

1. Constructor injection: Class constructor is used to inject the dependencies
2. Setter injection: Setter methods are used to pass the dependencies
3. Interface injection: We have to provide a inteface with injector method, and have to provide the setter methods to provide the dependencies to any client passes to it.

The responsibility of the dependency injection is to

1. Create the objects
2. Know which class requires those objects
3. And provide all those objects

- Which dependecy is better?
  - Constructor depedency is used for mandatory dependencies and Setter based dependency is used for optional dependencies.
  - If our application cannot operate without any dependencies, then those dependencies need to be injected using the constructor dependency, constructor DI fails to achieve Circular Dependency.
  - Circular dependency is a situation where A is dependent on B and B is dependent on A. Setter injection helps us to acheive Circular dependency.

## IoC(Inversion of Control) container

- It is a principle which transfers the control of objects and parts of a program to a container or a framework. It is the basic context of Object Oriented Programming.

- Framework takes the control of the flow of the program and makes the method calls to the custom code, to enable this, frameworks use abstraction with additional behaviour built-in.

- According to this principle a class should concentrate on fullfilling the responsibilites and not on creating the objects that fulfill those responsibilities.
Inversion of Control can be achieved through various mechanisms such as, Dependency injection, service locator pattern, factory pattern and strategy design pattern.

> IoC and DI are almost same the difference is that IoC creates the objects and manages them, while Dependency Injection injects the dependencies wherever it has to.

### Application Context

- Spring is based on the principle of IoC container, it is responsible for managing the objects of application, it uses dependency injection to inject the dependencies.

- Application context and Bean factory represents the IoC container. Bean Factory is the root interface of Spring framework, which provides basic functionalities for managing beans.Bean factory interface doesn't support annotation configuration.

- Application context is an interface which extends the bean factory interface, so it provides all the functionalites of bean factory and more. Bean factory is used for lightweight applications.

- ApplicationContext provides more enterprise specific features, the important features are resolving messages, supporting internationalization, publishing events and application layer specific context.

> Types of application context

 1.AnnotationConfigApplicationContext: is a class used with java based configuration.

 2.AnnotationConfigWebApplicationContext : is a class used with java based configuration for web application.

 3.XmlWebApplicationContext: is a class and can be used with xml based configuration.

 4.FileSystemApplicationContext: is a class, used for xml based configuration, this class takes file path as a parameter.

 5.ClassPathXmlApplicationContext: is same as previous one but xml file path is provided as parameter.

- What is a bean?

  - A bean is nothing but an object which is instantiated, assembled and managed by the spring IoC container which is either Bean factory or application context.
  - Should we have to configure all the objects as spring beans? The answer is no. According to spring documentation we have to configure beans for service layer objects, data access objects and presentation objects.

### MVC

- MVC is short for Model View Controller, Basically our code has different sections, one is for  how the interface should look like, other is to hold the data, and other is how the application should work or the functionality of the application. MVC is a way to organize the code in its own way.

Model code reflects the real world entities, like it holds the raw data of the application, or holds the essential components of the app.
View code is about how the user will interact with the application, or how the app should look or feel.
Controller is the brain of the application, it takes the user input and decides what to do with it, it ties Model and View together.

Then what is the difference between MVC and Spring MVC?
MVC is a design pattern and Spring MVC is an implementation of that design pattern. Just like TCP/IP is an implementation of OSI  reference model.

Spring MVC
Flow of spring MVC
In the web application there are lots of controllers or servlets, it is difficult to manage them all, so Spring MVC provides a front controller called DispatcherServlet which takes care of which servlet to be called. But before that when there is a request from client request goes to web.xml and request will go to dispatcher servlet, and how will it done, we have to configure request to be go through the dispatcher servlet. And how dispatcher servlet knows which controller or servlet to call, the calling will be done using annotations which is an @Controller annotation, which will be having some mapping.

ModelAndView
Model and view is  a class that holds both model and view, this class makes possible for a controller to return the model and view return type as a single return type.

Spring Annotations

Spring annotations are used to perform different types of tasks. Component annotation is used to specify that I need an object for this class, @Componentscan is used to scan the packages for the @Component annotations. @Autowired is used to wire the dependencies, where @Componentscan will scan the packages and @Autowire will inform spring, where the injection has to occur. @Qualifier is used to remove confusion, if two class implement same interface, then @Qualifier is used to specify which class to be called, by providing the id, @Primary is also used for the same purpose but is used with specific class, so that it will get the highest priority.

@RequestMapping is an annotation used to tell the spring that map this request when the user enters a request which is having same url as the mapping and by default request mapping annotation is a GET method annotation and if we want other http request we have to explicitly mention them.

@RestController annotation is used to automatically convert a return value to JSON format, if we not use @RestController we have to use @ResponseBody in combination with @Controller annotation.

@ModelAttribute annotation is used to inject or load the data objects in the model before the jsp page loads, and the other scenario is to read the data from an existing model.

@Autowired
We are informing spring that if framework wants to set some property, and if a bean is available it connects or wire automatically, that is auto wire it.

We can use this annotation to mark the dependency which spring is going to resolve and inject. We can use this with setter methods, constructor methods and fields as well.@Autowired has a default boolean argument called request  whose default value is true. It tunes spring's behaviour when it doesnot find a Bean to wire. When true, an exception is thrown and otherwise nothing is wired. If we use constructor injection all the constructor arguments are mandatory.
or
Autowired annotation is used to inject the dependencies implicitly or automatically, it uses internal setter or constructor injection. this does not work on primitive or string values and works only on reference types.

```Java
class Car{
 Engine engine;
 @Autowired
 Car(Engine engine){
  this.engine=engine;
}
}
```

@Bean
This methods is used to instantiate a Spring bean. Spring calls these methods when instantiation is required of a return type. The resulting should have the  same name as the factory method, but if we want to name it differently then we can use the name and value arguments.

Bean annotation is used at method level and that indicates that this method return an object which should be managed by the spring container, mostly Bean annotations are used with configuration classes.

```Java
@Bean
Engine engine(){
 return new Engine();
}
```

@Qualifier
Qualifier is used in a situation when we create more than one bean with same type and want to wire only one them to the property, the Qualifier with autowired can be used to remove the confusion.
This annotations is used in confused situations. For example consider there is an interface and two class implements that interface and we want to inject a bean, then spring will be confused with multiple matching definitions. We can explicitly provide bean's name using this annotation.

```Java
@Autowired
@Qualifier("bike")
void setVehicle(Vehicle vehicle)[
 this.vehicle=vehicle;
}
```

@Required
If we want to inject the dependencies through XML configuration then, this annotation can be used with the setter methods.

```Java
@Required
void setVehicle(Vehicle vehicle){
 this.vehicle=vehicle;
}
```

``` XML
<bean id="vehicle" class="fully qualified name">
<property>name="bike" value="Ducati"</property>
</bean>
```

@Value
We can use this annotation to inject the property values into the beans, and it is compatible with all the injecting techniques.

```Java
@Autowired
@Value("int value")
void setSomething(int value){
 this.value=value;
}
```

@Component
Component annotation allows spring to automatically detect our custom beans, without writing any explicit code. Spring will scan our application for the classes annotated with component annotation and injects the required dependencies.
This annotation is used, when we want an object for a class.

```Java
@Component
class Frame {
}
```

@ModelAttribute
This annotation is used to access the attributes of the model or to instantiate a model object if it is not present.
@RequestHeader
It is used to bind the request header of a http reqeust with the method argument

Difference between @Component and @Autowired annotations is that @Component is used to let the spring to know that I may need an object for this class  and @Autowired does the job of creating the objects

## Aspect Oriented Programming

Aspect oriented programming is about breaking the program logic into distinct parts called concerns, the concerns that span across multiple parts of the program is called cross-cutting concers, these cross-cutting concers are conceptually different from the business logic. Different types of aspects are logging, security, transaction, cashing etc.

cross-cutting means, the objects that concerns other objects in the problem

Terms in AOP
Aspect
Aspect is a module which has set of API's providing cross-cutting requirements.

Join point
Join point represents the place where one can plug-in the aspect.

Advice
This is the actual action that can be taken before or after method execution

point cut
It is a set of one or more number of join points where an advice execution is done. We can specify point cuts using expressions and patterns.

Introduction
Introduction allows us to add methods and attributes to the existing classes.

Weaving
weaving is about linking the aspects with other application types or objects to create an advised object. This can be done at compile time, load time, or runtime.

Types of advice
Before: This is invoked before method execution
After: This is invoked after method execution, irrespective of the result.
After returning: This is invoked after succesfull completion of the method execution
After throwing:  This is invoked after the method execution throws an exception.
Around. This is invoked before and after of the method execution

@ResponseBody
This annotation tells the controller that the returned object is automatically serialized into JSON and passed back into HttpResponse object

@RESTcontroller
This annotation is a combination of both @Controller and @ResponseBody annotations.

AOP proxy
Proxy is nothing but an object that wraps another object maintaining its interface and optionally providing aditional features.

Spring Boot
Spring boot is similar to spring framework, it is a module of spring framework. It makes spring configuration easier, where the boot provides auto configuration features.
@SpringBootApplication annotated with the main class of the application tells that this is a spring boot application. It encapsulate @Configuration, @EnableAutoConfiguration and @ComponentScan with their default values.

@EnableAutoConfiguration
As the name says, that it enables auto configuration. The spring boot looks for the auto configuration beans on the classpath and automatically applies it. We have to use this annotation in combination with @Configuration

@ConditionalOnClass and @ConditionalOnMissingClass
These annotations are used to write custom auto configurations, If we want to use a bean of a specific class, then that class needed to be passed as an argument to the @ConditionalOnClass("").

@ConditionalOnBean and @ConditionalOnMissingBean
We can use these annotations when we want to define conditions based on the presence or absence of the Bean. We have to use this annotation in combination with @Bean.

@ConditionalOnProperty
We can make the conditions on the values of the properties.

@ConditionalOnResource
We can make spring use specific things only when the specified resource is present.

@ConditionalOnWebApplication and @ConditionalOnNotWebApplication
With these annotations we can makes conditions based on whether the application is web application or not web application

@Conditional
We can create a class with custom conditions and can tell spring by passing the name of the class as a parameter to @Conditional annotation.

@ConditionalOnExpression
Spring can use the marked definitions when SpEL is evaluated to be true.

@ModelAttribute
This annotation is invoked before the controller methods that are annotated with @RequestMapping annotation, the idea behind this sequence is that the model object needs to be created before any processing is started in controller

@RequestBody
When @RequestBody annotation is used with method parameter, spring framework knows that it has to bind the incoming HTTP request body to that parameter.

@Repository
This annotation is used to indicate that this class provides the mechanism for storage, retrival, update or delete operations on objects.

model.attribute is used to inject a model object before the jsp page is loaded, It can also be used with method parameters to read the existing model data

```Java
Annotations
@Aspect
@Autowired
@Bean
@Component/@ComponenScan
@Controller
@Configuration
@Conditional
Http method annotations(get, put, post, delete)
@Lazy
@ModelAttribute
@Qualifier
@Primary
@PathVariable
@RequestMapping
@ResponseBody
@Repository
@RequestBody
@RequestParam
@RestController
@Required
@RequestHeader
@ResponseHeader
@Service
@Value
```

@EnableAutoConfiguration
This annotation is used to enable the auto configuration feature, where the it tries to automatically configure the spring boot application based on the jar dependencies we have added to the pom file.
To use auto configuration we have to use either @EnableAutoConfiguration or @springbootApplication annotation in the configuration class

@Configuration
This annotation indicates that the class contains @Bean definition methods and needs to be processed by the spring container for processing the class and generating beans

What is spring boot?
Spring boot is a separate module of spring framework which provides pre configured set of frameworks, which reduces the boiler plate code for configuration, so that we can have the application up and running with small amount of code, and spring boot is a stand alone and production ready application because it has an embeded tomcat server.

> Go through aop proxies, what is the need of lazy and eager instantiation, scope of beans.

### Spring security

- When ever there is a request the request passes through different types of filters, filters are the one which provides security like authentication and authorization,  the different types of filters are basicauthenticationfilter, usernamepasswordfilter.
- If the appropriate filter is loaded then an authentication object is created and it is passed to the authentication manager as an input, the authentication has an interface called authentication provider with an authentication method, which has various implementations based on the use case, like DaoAuthenticationProvider, ldapAuthenticationProvider etc.

- Then using user details service it fetches the user object from the database or from the in memory sources, after fetching from the data base it compared with the incoming request credentials object if the authentication is successful an user principal authentication object will be created.
- User details service has only one method called loadByUsername which verifies the details from the data base, it responsible for fetching the user object with user name and password which will be compared with incomming user object.
