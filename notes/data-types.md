# JS Data Types

[ << Previous Lesson - JS Functions ](./functions.md) 


## JS Data Types are Dynamic

This means that the same variable can be used as different types.

Example:

````js
var x; // Now x is undefined
var x = 5; // Now x is a Number
var x = "John"; // Now x is a String
````

---

## JS Primitive Data & Complex Data

* 一 __primitive data__ value, properties, methods
* `typeof` operator, primitive types :
   * `string`
   * `number`
   * `boolean`
   * `undefined`
   * (note:  `null`, JavaScript bug)
* `typeof` operator, complex types :
   * `function`
   * `object`

---

## JS Data Type Overview

JavaScript variables can hold many data types: numbers, strings, arrays, objects and more:


`*`: Primitive types

| Data Type                          | Example                                  | Value of Example <br/> (console.log(x))  | Type of Example <br/> (Return of typeof x) |
| ---------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| Number *                               | var length = 16;                         |                                          | "number"                                 |
| String        *                        | var lastName = "Johnson";                |                                          | "string"                                 |
| Boolean  *                             | var bool = true;                         |                                          | "boolean"                                |
| Undefined *                            | var person; <br/>var person = undefined; | undefined                                | "undefined"                              |
| Null   (Object)                        | var person = null;                       | null                                     | "object"                                 |
| Array                                  | var cars = ["Saab", "Volvo", "BMW"];     | (3) ["Saab", "Volvo", "BMW"]             | "object" <br/>(because in JavaScript arrays are objects.) |
| Date                                   | var d = Date()                           | "Wed Mar 25 2015 11:13:00 GMT+0800     " | "object"                                 |
| Object                                 | var x = {firstName:"John", lastName:"Doe"}; |                                          | "object"                                 |
| Function                               | function toCelsius(f) {<br/> return (5/9) * (f-32); <br/>} | "function toCelsius(f) { return (5/9) * (f-32); }" | "function"                               |
| String, Number, Boolean                | var x = new String();<br/>var y = new Number();<br/>var z = new Boolean();             
| typeof x= String {length: 0, 

[[PrimitiveValue]]: ""}<br/>typeof y= Number {[[PrimitiveValue]]: 0}<br/>typeof z= Boolean {[[PrimitiveValue]]: false} | "object"                                 |

---
