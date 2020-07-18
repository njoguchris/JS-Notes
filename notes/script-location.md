# JS Script Location
> * By Chris Njogu

 [Back to JS Version ](./version.md) | [Next to JS Output](./output.md)


## Introduction

In HTML, JavaScript statements are "instructions" to be "executed" by the web browser.



## In HTML

* Must be inserted between `<script>` and `</script>` tags.
* `<script type="text/javascript">`: This type attribute is not required.
  * (JavaScript is the default scripting language in HTML).
  * EX:

```html
<script>
function greetings() {
	alert('Hi, how are you?');
}
</script>
<button type="button" onclick="greetings()">Click to Say Hi</button>
```
* JavaScript HTML `<body>` `<head>` sections 
	*  `<html>` work (on Chrome)

* Keeping all code in one place, is always a good habit.
  * It is a good idea to __place scripts at the bottom of the `<body>` element. This can improve page load__, because script compilation can slow down the display.
  * You can place __an external script reference in `<head>` or `<body>`__ as you like. The script will behave as if it was located exactly where the `<script>` tag is located.


## External JavaScript 


````html
<script src="myScript.js"></script>
````
* External scripts (e.g. "myScript.js") `<script>`
* JS Script Location
  1. It separates HTML and code
  2. It makes HTML and JavaScript easier to read and maintain
  3. Cached JavaScript files can speed up page loads

-----
[Back to JS Version](./version.md) | [Next to JS Output](./output.md)
