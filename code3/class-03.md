# Class-03 reading Summary

## Passing Functions as Props

### Lists and Keys
Given the code below, we use the `map()` function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it:

```
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);
```

This code logs [2, 4, 6, 8, 10] to the console.

In React, transforming arrays into lists of elements is nearly identical.

### Rendering Multiple Components

```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
```

## Keys
Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.

----

## The Spread Operator

JavaScript, spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.
The spread operator was added to JavaScript in ES6 (ES2015), just like the rest parameters, which have the same syntax: three magic dots ….

The spread operator is useful for many different routine tasks in JavaScript, including the following:
* Copying an array
* Concatenating or combining arrays
* Using Math functions
* Using an array as arguments
* Adding an item to a list
* Adding to state in React
* Combining objects
* Converting NodeList to an array

----

## Passing Functions to Components

Pass event handlers and other functions as props to child components:

`<button onClick={this.handleClick}>`

If you need to have access to the parent component in the handler, you also need to bind the function to the component instance (see below).

There are several ways to make sure functions have access to component attributes like this.props and this.state, depending on which syntax and build steps you are using.