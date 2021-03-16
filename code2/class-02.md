# Class-02 reading

## Duckett HTML book Chapter 2 : Text


### HTML elements are used to describe the structure of the page.


### Headings

HTML has six "levels" of headings:
**<h1>** is used for main headings

**<h2>** is used for subheadings

If there are further sections under the subheadings then the **<h3>** element is used, and so on...

<img src="/img/class2.png" alt="headers" />

### Paragraphs

To create a paragraph, surround the words that make up the paragraph with an opening **<p>** tag and closing **</p>** tag.
By default, a browser will show each paragraph on a new line with some space between it and any subsequent paragraphs.

<img src="/img/class22.png" alt="headers" />

### Bold & Italic

By enclosing words in the tags **<b>** and **</b>** we can make characters appear bold.

By enclosing words in the tags **<i>** and **</i>** we can make characters appear italic.

### Line Breaks & Horizontal Rules

If you want to add a line break inside the middle of a paragraph you can use the line break tag **<br />**.

<img src="/img/class23.png" alt="headers" />


To create a break between themes — such as a change of topic in a book or a new scene in a play — you can add a horizontal rule between sections using the **<hr />** tag

<img src="/img/class24.png" alt="headers" />

----

## Duckett HTML book Chapter 10 : Introducing CSS

CSS allows you to create rules that specify how the content of an element should appear. For example, you can specify that the background of the page is cream, all paragraphs should appear in gray using the Arial typeface, or that all level one headings should be in a blue, italic, Times typeface.


CSS works by associating rules with HTML elements. These rules govern how the content of specified elements should be displayed. A CSS rule contains two parts: a selector and a declaration.

<img src="/img/class26.PNG" alt="headers" />

CSS declarations sit inside curly brackets and each is made up of two parts: a property and a value, separated by a colon. You can specify several properties in one declaration, each separated by a semi-colon.

<img src="/img/class27.PNG" alt="headers2" />

We can use css features in HTML structure by three ways:

1. **Using External CSS**; by linking the HTML file in the head session using the following code:
`<link href="css/styles.css" type="text/css"rel="stylesheet" />`.

1. **Using Internal CSS**; by adding `<style>` tags inside the head session and writing **css** code in it.

2. **Inline CSS**; by writing the style feature in the same line of HTML code.

----

## Duckett JavaScript book Chapter 2 : Basic JavaScript Instructions

A script is a series of instructions that a computer can follow one-by-one. Each individual instruction or step is known as a statement. Statements should end with a semicolon.

You should write **comments** to explain what your code does. They help make your code easier to read and understand. This can help you and others who read your code.

A script will have to temporarily store the bits of information it needs to do its job. It can store this data in **variables**.
Variables are used to temporarily store pieces of information used in the script.

We can declare variables by:

<img src="/img/class28.PNG" alt="headers2" />

We can assign a value for the variable by:

<img src="/img/class29.PNG" alt="headers2" />

Data types:
* Numerical Data type.
* Strings Data type.
* Boolean Data type.

----

## Duckett JavaScript book Chapter 4 : Decisions and Loops

### Comparison operators: Evaluation conditions

`===` Equal to
`!=` Not Equal to
`===` Strict equal to
`!==` Strict not Equal to
`>` Greater than
`<` Less than
`>=` Greater than or equal to
`<=` less than or equal to

### Logical operators:

`&&` Logical and
`||` Logical or
`!` Logical not

### Logical statements:

* Use **if** to specify a block of code to be executed, if a specified condition is true.
* Use **else** to specify a block of code to be executed, if the same condition is false.
* Use **else if** to specify a new condition to test, if the first condition is false.
* Use **switch** to specify many alternative blocks of code to be executed.

----














