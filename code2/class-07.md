# Class-07 reading Summary

## Duckett HTML book Chapter 6 : Tables

A table represents information in a grid format.
Examples of tables include financial reports, TV
schedules, and sports results.

* Basic Table St ructure:

```
<table>
<tr>
<td>15</td>
<td>15</td>
<td>30</td>
</tr>
<tr>
<td>45</td>
<td>60</td>
<td>45</td>
</tr>
<tr>
<td>60</td>
<td>90</td>
<td>90</td>
</tr>
</table>
```

* **< table >**
The `<table>` element is used
to create a table. The contents
of the table are written out row
by row.

* **< tr >**
You indicate the start of each
row using the opening `<tr>` tag.
(The tr stands for table row.)
It is followed by one or more
`<td>` elements (one for each cell
in that row).
At the end of the row you use a
closing `</tr>` tag.

* **< td >**
Each cell of a table is
represented using a `<td>`
element. (The td stands for
table data.)
At the end of each cell you use a
closing `</td>` tag.

* **< th >**
The `<th>` element is used just
like the `<td>` element but its
purpose is to represent the
heading for either a column or
a row. (The th stands for table
heading.)


You can make cells of a table span more than one row
or column using the rowspan and colspan attributes.

For long tables you can split the table into a `<thead>` ,
`<tbody>`, and `<tfoot>`.

<hr>

## Duckett JavaScript book Chapter 3 : Functions, Methods, and Objects

**Functions** let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can
reuse the function (rather than repeating the same set of st atements).

A JavaScript function is a block of code designed to perform a particular task.
A JavaScript function is executed when "something" invokes it (calls it).


```
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}
```

* A JavaScript function is defined with the `function` keyword, followed by a name, followed by parentheses ().

* Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

* The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

* The code to be executed, by the function, is placed inside curly brackets: {}

```
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

* Function **parameters** are listed inside the parentheses () in the function definition.

* Function **arguments** are the **values** received by the function when it is invoked.

* Inside the function, the arguments (the parameters) behave as local variables.

<hr>

## Objects:

Objects group together a set of variables and functions to create a model
of a something you would recognize from the real world. In an object,
variables and functions take on new names.

This code assigns many values (Fiat, 500, white) to a variable named car:

`var car = {type:"Fiat", model:"500", color:"white"};`

The values are written as name:value pairs (name and value separated by a colon).





