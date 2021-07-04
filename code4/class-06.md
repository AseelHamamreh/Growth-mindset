## Inheritance and Interfaces

### Interfaces: 

- blueprint of a class. It has static constants and abstract methods.
- can be only abstract methods in the Java interface, not method body.
- can contain only constants, method signatures, default methods, static methods, and nested types.
- can only be implemented by classes or extended by other interfaces.
- once the interface is defined; any number of classes can be implemented and the class can implement any number of interfaces unlike the inheritance.

###### benefits of Interfaces:
1. It is used to achieve abstraction.
2. By interface, we can support the functionality of multiple inheritance.
3. It can be used to achieve loose coupling.

###### Syntax:

```
interface <interface_name>{  
      
    // declare constant fields  
    // declare methods that abstract   
    // by default.  
}  
```

*************


### Inheritance:

- one object acquires all the properties and behaviors of a parent object.

- we can create new classes that are built upon existing classes: 
* reuse methods and fields of the parent class.
* add new methods and fields in your current class.

###### benefits of inheritance: 
1.  Method Overriding.
2. Code Reusability.

###### syntax :

```
class Subclass-name extends Superclass-name  
{  
   //methods and fields  
}  
```
