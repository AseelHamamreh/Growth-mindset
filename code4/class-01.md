# Class-01 reading Summary

### The Java programming language defines the following kinds of variables:

1. Instance Variables
2. Class Variables
3. Local Variables
4. Parameters 

#### Primitive Data Types:

* byte: 
- 8-bit 
- signed two's complement integer
- has a minimum value of -128 and a maximum value of 127
- useful for saving memory in large arrays
- They can also be used in place of int where their limits help to clarify your code

* short: 
- 16-bit 
- signed two's complement integer
- Has a minimum value of -32,768 and a maximum value of 32,767
- you can use a short to save memory in large arrays

* int: 
- 32-bit 
- signed two's complement integer
- has a minimum value of -231 and a maximum value of 231-1
- Use the Integer class to use int data type as an unsigned integer

* long: - 64-bit 
- two's complement integer. 
- has a minimum value of -263 and a maximum value of 263-1
- Use this data type when you need a range of values wider than those provided by int

* float: 
- single-precision 
- 32-bit IEEE 754 floating point
- use a float (instead of double) if you need to save memory in large arrays of floating point numbers
- should never be used for precise values, such as currency

* double: 
- a double-precision 
- 64-bit IEEE 754 floating point
- should never be used for precise values, such as currency.

* boolean: 
- The boolean data type has only two possible values: true and false.

* char:
- single-precision 
 - 16-bit Unicode character
 - It has a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535 inclusive).


 ### Arrays:

 Arrays need to be declared and then created. In order to declare a variable that will hold an array of integers, we use the following syntax:

 ```int[] arr;```

 and to create array with for example a size = 5:

 ```arr = new int[5];```

 