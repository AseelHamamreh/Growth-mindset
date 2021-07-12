## Read: 11 - Spring

Spring MVC framework enables separation of modules namely Model, View and Controller and seamlessly handles the application integration. This enables the developer to create complex applications also using plain java classes. The model object can be passed between view and controller using maps. In this article, we will see how to set up a Spring MVC application in the Eclipse IDE and understand how to make applications.

The Spring MVC framework is comprised of the following components:

* Model: A model can be an object or collection of objects which basically contains the data of the application.
* View: A view is used for displaying the information to the user in a specific format. Spring supports various technologies like freemarker, velocity and thymeleaf.
* Controller: It contains the logical part of the application. @Controller annotation is used to mark that class as controller.
* Front Controller: It remains responsible for managing the flow of the web application. DispatcherServelet acts as a front controller in spring MVC.

***

to build an web application with spring we:
1. we will accept http Get requests at: ```http://localhost:8080/greeting```
2. if we have query string we will customize the greeting with an optional name parameter and the URL will be something like this: ```http://localhost:8080/greeting?name=User```.
3. we need firstly to generate a new project from [Spring Initializr](https://start.spring.io/) with the required dependencies. 
and inside the gradle build file we will see this in the dependencies sextion:
```
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
	implementation 'org.springframework.boot:spring-boot-starter-web'
	developmentOnly 'org.springframework.boot:spring-boot-devtools'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```
* we can create the project manually from intellij 

* To create a new controller: 
we can define controllers by ```@controller``` annotation
```@GetMapping``` annotation ensures that HTTP GET requests to **spacific path** are mapped to the ```greeting()``` method.
```@RequestParam``` binds the value of the query string parameter ```name``` into the ```name``` parameter of the ````greeting()``` method.
The value of the ```name``` parameter is added to a ```Model``` object, ultimately making it accessible to the view template.

* controller class example:

```
package com.example.servingwebcontent;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class GreetingController {

	@GetMapping("/greeting")
	public String greeting(@RequestParam(name="name", required=false, defaultValue="World") String name, Model model) {
		model.addAttribute("name", name);
		return "greeting";
	}

}
```

The implementation of the method body relies on Thymeleaf technoloyg to perform server-side rendering of the HTML. 
```Thymeleaf``` parses the ```greeting.html``` template and evaluates the ```th:text``` expression to render the value of the ${name} parameter that was set in the controller.

```greeting.html``` file example:

```
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head> 
    <title>Getting Started: Serving Web Content</title> 
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
    <p th:text="'Hello, ' + ${name} + '!'" />
</body>
</html>
```

***

- spring-boot-devtools : a model used To speed up this refresh cycle.

- To Run the application:

when we Initializ our project this calss will be ready:

```
package com.example.servingwebcontent;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ServingWebContentApplication {

    public static void main(String[] args) {
        SpringApplication.run(ServingWebContentApplication.class, args);
    }

}
```

to run the priject we just press on ```SpringApplication.run()``` from Intellij or by ``` /gradlew bootRun``` from the terminal.

we can build the ```JAR file``` by using ```./gradlew build``` and then run the JAR file, as follows:

```java -jar build/libs/gs-serving-web-content-0.1.0.jar```

- if we want to add a home page we need to create ```index.html``` inside the tamplates folder and we can see it at ```http://localhost:8080/```