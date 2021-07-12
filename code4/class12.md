## Read: 12 - Spring RESTful Routing & Static Files

- @RequestMapping — by Path: 
Example:
```
@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
    return "Get some Foos";
}
```

and to test this mapping we run curl command: ```curl -i http://localhost:8080/spring-rest/ex/foos```

- @RequestMapping — the HTTP Method: this method has no default So if we don't specify a value it's going to map to any HTTP request.

example:
```
@RequestMapping(value = "/ex/foos", method = POST)
@ResponseBody
public String postFoos() {
    return "Post some Foos";
}
```
to run it: ```curl -i -X POST http://localhost:8080/spring-rest/ex/foos```

-  @RequestMapping With the headers Attribute:
Example: 
```
@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)
@ResponseBody
public String getFoosWithHeader() {
    return "Get some Foos with Header";
}
```
we can add multiple headers like this: ```headers = { "key1=val1", "key2=val2" }```

- @RequestMapping Consumes and Produces: 

```
@RequestMapping(
  value = "/ex/foos", 
  method = GET, 
  headers = "Accept=application/json")
@ResponseBody
public String getFoosAsJsonFromBrowser() {
    return "Get some Foos with Header Old";
}
```

- RequestMapping With Path Variables:
Single @PathVariable: 
```
@RequestMapping(value = "/ex/foos/{id}", method = GET)
@ResponseBody
public String getFoosBySimplePathWithPathVariable(
  @PathVariable("id") long id) {
    return "Get a specific Foo with id=" + id;
}
```

Multiple @PathVariable:
```
@RequestMapping(value = "/ex/foos/{fooid}/bar/{barid}", method = GET)
@ResponseBody
public String getFoosBySimplePathWithPathVariables
  (@PathVariable long fooid, @PathVariable long barid) {
    return "Get a specific Bar with id=" + barid + 
      " from a Foo with id=" + fooid;
}
```

- RequestMapping With Request Parameters:
```
@RequestMapping(value = "/ex/bars", method = GET)
@ResponseBody
public String getBarBySimplePathWithRequestParam(
  @RequestParam("id") long id) {
    return "Get a specific Bar with id=" + id;
}
```

*** 

### Accessing Data with JPA

#### if we want to store data in the dataBase we need to add (JPA and H2) dependencies.

if we want to store a specific objects:
- we will have 2 constructors: normal and default, The default constructor exists only for the sake of JPA; we do not use it directly, so it is designated as **protected**.
- The class is annotated with ```@Entity``` ; indicating that it is a JPA entity.
- we add object’s id property;it is annotated with ```@Id``` so that JPA recognizes it as the object’s ID.
- The id property is also annotated with ```@GeneratedValue``` to indicate that the ID should be ***generated automatically***.

#### Create Simple Queries
we need to modify the created SpringApplication class to generate output:

in this example: 
```
package com.example.accessingdatajpa;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.annotation.Bean;

@SpringBootApplication
public class AccessingDataJpaApplication {

  private static final Logger log = LoggerFactory.getLogger(AccessingDataJpaApplication.class);

  public static void main(String[] args) {
    SpringApplication.run(AccessingDataJpaApplication.class);
  }

  @Bean
  public CommandLineRunner demo(CustomerRepository repository) {
    return (args) -> {
      // save a few customers
      repository.save(new Customer("Jack", "Bauer"));
      repository.save(new Customer("Chloe", "O'Brian"));
      repository.save(new Customer("Kim", "Bauer"));
      repository.save(new Customer("David", "Palmer"));
      repository.save(new Customer("Michelle", "Dessler"));

      // fetch all customers
      log.info("Customers found with findAll():");
      log.info("-------------------------------");
      for (Customer customer : repository.findAll()) {
        log.info(customer.toString());
      }
      log.info("");

      // fetch an individual customer by ID
      Customer customer = repository.findById(1L);
      log.info("Customer found with findById(1L):");
      log.info("--------------------------------");
      log.info(customer.toString());
      log.info("");

      // fetch customers by last name
      log.info("Customer found with findByLastName('Bauer'):");
      log.info("--------------------------------------------");
      repository.findByLastName("Bauer").forEach(bauer -> {
        log.info(bauer.toString());
      });
      // for (Customer bauer : repository.findByLastName("Bauer")) {
      //  log.info(bauer.toString());
      // }
      log.info("");
    };
  }

}
```

we need to create ```AccessingDataJpaApplication``` that  will inclue a method that puts the ```CustomerRepository``` from the Spring application context.
Then it saves a handful of the created objects, demonstrating the ```save()``` method and setting up some data to work with.
- ```findAll() ``` method to fetch all objects from the database.
- ```findById()``` to find the object by its ID.
- ```findByLastName()``` to fint objects with the same last name.
- ```The demo()``` method returns a CommandLineRunner bean that automatically runs the code when the application launches.