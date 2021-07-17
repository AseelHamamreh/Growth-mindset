# Read: 13 - Related Resources and Integration Testing

#### Relationship:

A one-to-many relationship is defined using the @OneToMany and @ManyToOne annotations and can have the optional @RestResource annotation to customize the association resource.

if we want to add One To One relationShip between Two classes we need to declare the method in each class we will add ```@OneToMany``` annotation in both classes and declare an instance of both classes in each class, then we will create two repositories for each classes, after that and if we want to use this relationShip we will call call the two repositories inside the **Many class** and work with it.

all other relationShips have different using but with same implementation with little differences.

***

### Integration Testing in Spring:

Integration testing plays an important role in the application development cycle by verifying the end-to-end behavior of a system.
we will need to add the following depencendies:
```junit-jupiter-engine, junit-jupiter-api```
and 
```Spring test dependency```

##### Enable Spring in Tests with JUnit 5

JUnit 5 defines an extension interface through which classes can integrate with the JUnit test.
We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.
We also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.

##### The WebApplicationContext Object

WebApplicationContext provides a web application configuration. It loads all the application beans and controllers into the context.

#####  Mocking Web Context Beans

MockMvc provides support for Spring MVC testing. It encapsulates all web application beans and makes them available for testing.

##### Verify Test Configuration

example:

```
@Test
public void givenWac_whenServletContext_thenItProvidesGreetController() {
    ServletContext servletContext = webApplicationContext.getServletContext();
    
    Assert.assertNotNull(servletContext);
    Assert.assertTrue(servletContext instanceof MockServletContext);
    Assert.assertNotNull(webApplicationContext.getBean("greetController"));
}
```

***

### Writing Integration Tests

1. Verify View Name
2. Verify Response Body
3. Send GET Request With Path Variable
4. Send GET Request With Query Parameters
5. Send POST Request








