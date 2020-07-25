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

---

---

## Numbers

### 1. Number

JavaScript 64 bit (integers, short, long, floating-point, etc.)

> JavaScript has only one type of numbers.
> Numbers can be written with, or without decimals.

````js
var x = 15.00; // Written with decimals
var y = 9; // Written without decimals
console.log( x / y ); //1.6666666666666667
console.log( x % y ); //6
````



### 2. NaN (Not a Number)

* `NaN` JavaScript reserved word
* `number`  (type `number`)

````js
console.log( NaN ); //NaN
console.log( typeof NaN ); //"number"
console.log( 100 / "Apple" ); //NaN
console.log( 100 + NaN );//NaN
console.log( "100" + NaN );//"100NaN"
console.log( isNaN( 100 / "Apple" ) ); //true
console.log( isNaN( 100 / "10" ) );  //false
````



### 3.Infinity

> *   If you calculate a number outside the largest possible number.
> *  type `number`, (`Infinity` / `-Infinity`)
> *  `Infinity`, `NaN` 

````js
console.log( Infinity ); //Infinity
console.log( -Infinity ); //-Infinity
console.log( typeof Infinity ); //"number"
console.log( 2 / "Apple" ); //NaN
````

> Division by 0 (zero) also generates `Infinity`:

````js
console.log( 2 / 0 ); //Infinity
console.log( -2 / 0 ); //-Infinity
````



Example:


````js
var num = 2;
while(num != Infinity){
	console.log("now num=" + num);
	num *= num;
}
console.log("final num=" + num);
````

Result:

````
now num=2
now num=4
now num=16
now num=256
now num=65536
now num=4294967296
now num=18446744073709552000
now num=3.402823669209385e+38
now num=1.157920892373162e+77
now num=1.3407807929942597e+154
final num=Infinity
````



### 4.(e)

> * Extra large or extra small numbers can be written with scientific (exponential) notation.)

EX:

````js
var y = 123e5; // 12300000
var z = 123e-5; // 0.00123
````



### 5. Numeric operations of Numeric Strings

> JavaScript will try to convert strings to numbers in all numeric operations ( `+` operator)


````js
console.log( "100" * "10" ); //1000
console.log( "100" / "10" ); //10
console.log( "100" - "10" ); //90
console.log( "100" + "10" ); //"10010" (here "+" is used to concatenate strings, instead of add numbers)
````



### 6. Hexadecimal / octal / binary / decimals

> 1. By default, JavaScript displays numbers as base 10 decimals.
> 2. But you can use the toString() method to output numbers as base 16 (hex), base 8 (octal), or base 2 (binary).
> 3. **Never write a number with a leading zero (like 07)**


````js
var myNumber = 165;
console.log( myNumber.toString(16) );  // "a5"
console.log( myNumber.toString(8) );   // "245"
console.log( myNumber.toString(2) );   // "10100101"
````


> Hex:
> JavaScript interprets numeric constants as hexadecimal if they are preceded by __0x__.

````js
console.log(0xFF); //255
````



### 7. Precision


````js
//Integers (numbers without a period or exponent notation) are accurate up to 15 digits.
console.log( "d9_15=", 999999999999999 );    //d9_15= 999999999999999
console.log( "d9_16=", 9999999999999999 );   //d9_16= 10000000000000000
console.log( "d9_17=", 99999999999999999 );  //d9_17= 100000000000000000
console.log( "d9_18=", 999999999999999999 ); //d9_18= 1000000000000000000
````


````js
//floating point arithmetic is not always 100% accurate
console.log( 0.2 + 0.1 );                  //0.30000000000000004
console.log( 0.2 + 0.3 );                  //0.5
console.log( (0.2 * 10 + 0.1 * 10) / 10 ); //0.3
````





### 8. More: JavaScript Numbers 64-bit 

> * JavaScript numbers are always stored as double precision floating point numbers, following the international IEEE 754 standard.
> * 

|              | Value (aka Fraction/Mantissa) | Exponent | Sign  |
| ------------ | ----------------------------- | -------- | ----- |
| bit position | 0~51                          | 52~63    | 63    |
| bit legnth   | 52 bits                       | 11 bits  | 1 bit |




---

## Strings

1. A string (or a text string) is a series of characters like "John Doe".

2. 

Example:

````js
var carName = "Volvo XC60"; // Using double quotes
var carName = 'Volvo XC60'; // Using single quotes
var answer = "It's alright"; // Single quote inside double quotes
var answer = "He is called 'Johnny'"; // Single quotes inside double quotes
var answer = 'He is called "Johnny"'; // Double quotes inside single quotes
var x = 'It\'s alright'; // Using the escape character
````


3. 

````js
console.log("ab\"c");
console.log('ab\'c');
````


4. Break up a long string

Example:

````js
// 1. safer way
var txt = "ABCD EFGH IJK LMN " +
"OPQR STUV WXYZ";

// 2. workable but not preferred
var txt = "ABCD EFGH IJK LMN \
OPQR STUV WXYZ";

// 3. cannot work (not allow spaces behind the \ character.)
var txt = "ABCD EFGH IJK LMN \ 
OPQR STUV WXYZ";

// 4. cannot work
var txt = "ABCD EFGH IJK LMN
OPQR STUV WXYZ";
````



---

## Booleans

* Booleans can only have two values: `true` or `false`.


* 0 false、1 true 

````js
0==false //true
0===false //false

1==true //true
1===true //false

2==true //false
````





------

## Date

1. A JavaScript date can be written as:
   - string: `Tue Dec 05 2017 17:44:20 GMT+0800 `
   - number: `1512467060522` (milliseconds since January 1, 1970, 00:00:00.)



2. Time zone：3 
  - Local time (browser's time zone)
  - UTC (Universal Time Coordinated)
  - GMT (Greenwich Mean Time)
  > UTC is the same as GMT


---

## Arrays

Example:

````js
var cars = ["Saab", "Volvo", "BMW", 46];
document.getElementById("demo").innerHTML = cars[0]; //Saab
document.getElementById("demo").innerHTML = cars; // Saab,Volvo,BMW
document.getElementById("demo").innerHTML = cars[3]; //46
document.getElementById("demo").innerHTML = cars[10]; //undefined
````


1.
  > * In JavaScript, **arrays** always use **numbered indexes**.
  > * Arrays use **numbers** to access its "**elements**"
  > * Objects use **names** to access its "**members**"



4. **Avoid using `new Array()`!! Use `[]` instead.**


There are 2 ways to create arrays:
  * Way 1: using the array literal method (`[]`)
  * Way 2: using the keyword `new` (`new Array()`)

  > Way 1 & 2 do exactly the same.

```js
var cars = ["Saab", "Volvo", "BMW"]; // way1: array literal method.
var cars = new Array("Saab", "Volvo", "BMW"); // way2: using keyword **new**
```


> *Note: Why not using new Array()?*
>
> 1. There is no need to use new Array(). For simplicity, readability and execution speed.
> 2. **It can also produce some unexpected results:**

````js
var ary1 = new Array(10, 100);
console.log(ary1);             // [10, 100]
console.log(ary1.length);      // 2

var ary2 = new Array(10);
console.log(ary2);             // [empty × 10]
console.log(ary2.length);      // 10
````

---
