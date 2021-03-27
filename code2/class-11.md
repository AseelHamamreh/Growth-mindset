# Class-11 reading Summary

## Duckett HTML book Chapter 16 : Images

### Controling sizes of image in CSS 

You can control the size of an
image using the width and
height properties in CSS, just
like you can for any other box.
Specifying image sizes helps
pages to load more smoothly
because the HTML and CSS
code will often load before the
images, and telling the browser
how much space to leave for an
image allows it to render the rest
of the page without waiting for
the image to download.

### Aligning images Using CSS

Rather than using the <img>
element's align attribute, web
page authors are increasingly
using the float property to align
images. There are two ways that
this is commonly achieved:
1. The float property is added
to the class that was created to
represent the size of the image
(such as the small class in our
example).
2. New classes are created with
names such as align-left or
align-right to align the images
to the left or right of the page.
These class names are used in
addition to classes that indicate
the size of the image.

### Centering images Using CSS

By default, images are inline
elements. This means that they
flow within the surrounding text.
In order to center an image, it
should be turned into a blocklevel
element using the display
property with a value of block.
Once it has been made into a
block-level element, there are
two common ways in which you
can horizontally center an image:
1. On the containing element,
you can use the text-align
property with a value of center.
2. On the image itself, you can
use the use the margin property
and set the values of the left and
right margins to auto.

```
img.align-center {
display: block;
margin: 0px auto;}
img.medium {
width: 250px;
height: 250px;}
```
----

### Background Images

The background-image
property allows you to place
an image behind any HTML
element. This could be the entire
page or just part of the page. By
default, a background image will
repeat to fill the entire box.

### Repeating Images

The background-repeat
property can have four values:

* repeat
The background image is
repeated both horizontally and
vertically (the default way it
is shown if the backgroundrepeat
property isn't used).

* repeat-x
The image is repeated
horizontally only.
* repeat-y
The image is repeated vertically
only.
* no-repeat
The image is only shown once.
The background-attachment
property specifies whether a
background image should stay in
one position or move as the user
scrolls up and down the page. It
can have one of two values:
1. fixed
   The background image stays in the same position on the page.
2. scroll
  The background image moves up and down as the user scrolls up and down the page.


### Image rollovers and Sprites

Using CSS, it is possible to create
a link or button that changes to a
second style when a user moves
their mouse over it (known as a
rollover) and a third style when
they click on it.

This is achieved by setting a
background image for the link or
button that has three different
styles of the same button (but
only allows enough space to
show one of them at a time).

----

## Duckett HTML book Chapter 19 : Practical Information

* Search engine optimization h XX elps visitors find your
sites when using search engines.
* Analytics tools such as Google Analytics allow you to
see how many people visit your site, how they find it,
and what they do when they get there.
* To put your site on the web, you will need to obtain a
domain name and web hosting.
* FTP programs allow you to transfer files from your
local computer to your web server.
* Many companies provide platforms for blogging, email
newsletters, e-commerce and other popular website
tools (to save you writing them from scratch).
