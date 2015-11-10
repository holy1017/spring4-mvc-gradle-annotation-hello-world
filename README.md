실행 순서
=============================== 
1. com.mkyong.helloworld.servlet3
  - MyWebInitializer
    - getRootConfigClasses
      - SpringRootConfig.java
        - @Configuration
        - @ComponentScan({ "com.mkyong.helloworld.service" })
          - HelloWorldService.java
            - @Service
    - getServletConfigClasses
      - SpringWebConfig.java
        - @EnableWebMvc
        - @Configuration
        - @ComponentScan({ "com.mkyong.helloworld.web" })
          - WelcomeController.java
            - @RequestMapping(value = "/", method = RequestMethod.GET)
            - @RequestMapping(value = "/hello/{name:.+}", method = RequestMethod.GET)
            - return "index"
        - addResourceHandlers
          - "/resources/**" -> "/resources/"
        - viewResolver
          - InternalResourceViewResolver
          - "/WEB-INF/views/jsp/"
          - ".jsp"
    - getServletMappings
      - "/"

4. com.mkyong.helloworld.web



Gradle - Spring 4 MVC Hello World
===============================
Template for Spring 4 MVC + JSP view + Annotation configuration, using Gradle build tool.

###1. Technologies used
* Required Servlet 3.0+ container, like Tomcat 7 or Jetty 8
* Gradle 2.0
* Spring Spring 4.1.6.RELEASE
* JSTL 1.2
* Logback 1.1.3
* Boostrap 3

###2. To Run this project locally
```shell
$ git clone https://github.com/mkyong/spring4-mvc-gradle-annotation-hello-world
$ gradle jettyRun
```
Access ```http://localhost:8080/spring4```

###3. To import this project into Eclipse IDE
1. ```$ gradle eclipse```
2. Import into Eclipse via **existing projects into workspace** option.
3. Done.

###4. Project Demo
Please refer to this article [Gradle - Spring 4 MVC Hello World + Annotation ](http://www.mkyong.com/spring-mvc/gradle-spring-4-mvc-hello-world-example-annotation/)

