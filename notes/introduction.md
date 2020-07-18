# JS Introduction

[TOC]



## Introduction

* WHAT is Javascript:
    - JavaScript is the __programming language__ of HTML and the Web.
* JavaScript is easy to learn.
* WHY LEARN JAVASCRIPT
    - JavaScript is one of the 3 languages all web developers must learn:
      1. __HTML__ to define the content of web pages
      2. __CSS__ to specify the layout of web pages
      3. __JavaScript__ to program the behavior of web pages


> __Java vs. JavaScript__
>
> * They are completely different languages, both in concept and design.
> * JavaScript was invented by Brendan Eich in 1995.
> * JavaScript became an ECMA standard in 1997. 
> * ECMA-262 is the official name, also known as **ECMAScript**).

-----

## A Simple Example

````html
<!DOCTYPE html>
<html>
<body>
<h1>My First JavaScript</h1>
<button type="button" onclick="document.getElementById('our_demo_id').innerHTML = new Date() ">
	Click me to display Date and Time.
</button>
<p id="our_demo_id"></p>
</body>
</html>
<script>
alert('Welcome!');
</script>
````

----

