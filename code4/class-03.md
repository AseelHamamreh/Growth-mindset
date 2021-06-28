# Class-03 reading Summary

## Primitives vs. Objects

Java has two type system:
1. Primitives (int,char..etc)
2. reference  (Integer, Boolean..etc)

Every object contains a single value of the corresponding primitive type.

Autoboxing: a process of converting a primitive type to a reference one.

Reference type takes much memory than primitives.

The performance of a Java code is quite a subtle issue, it depends on:
1. the hardware on which the code runs.
2. the compiler that might perform certain optimizations.
3. the state of the virtual machine.
4. the activity of other processes in the operating system.

##### Default values 
###### primitive types:
- 0 for numeric types.
- false for the boolean types. 

###### wrapper classes:
- null 

it is better to use primitive type than Reference type because it is much faster and takes less memory.

***

## Exceptions in Java

**Exception** is an event that occurs during the execution of a program that disrupts the normal flow of instructions.
When an error occurs within a method, the method creates an object and hands it off to the runtime system. The object, called an exception object, contains information about the error, including its type and the state of the program when the error occurred. Creating an exception object and handing it to the runtime system is called throwing an exception.

Valid Java programming language code must honor the Catch or Specify Requirement. 

##### The Three Kinds of Exceptions:
1. checked exception (exceptional conditions that a well-written application should anticipate and recover from).
2. error (not subject to the Catch or Specify Requirement).
3. runtime exception Such as logic errors (not subject to the Catch or Specify Requirement).

***

## Scanning

Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.


