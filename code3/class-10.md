# Class-10 reading Summary

### JS Call stack


Go through code line by line and execute each seperately - synchronous. LIFO method.

when the call stack starts on a frame, it will create a temp execution context - new memory frame that takes in the params are automatically funneled in and set as local storage within.

Overflow is when you have an recursive (or uncontrolled) element that continues running without endpoint. It will exceed the max call stack and crash.

### Errors

Reference error - tries to call a variable or function that is not stored locally. Easiest fix is to pre set the variables you need empty so if they haven’t been populated it won’t stop the program.

Syntax error - parsing an invalid object. JSON.parse is a good example: {‘foo’: ‘bar’} (wrong syntax) vs {‘{“foo”, “bar”}’} (correct syntax)

Range errors - calling a variable looking for something outside it’s set range of number values. ex.length can’t be negative (and will affact the arr by mutation by shortening/enlonging the array)

Type Errors - When you call for a param and the type (string, array, obj, etc) is not a valid type to use on the function you are calling.

Validation built in is a good idea on larger projects. Also name functions when possible to keep the stack easy to navigate durring dev. hello try catch