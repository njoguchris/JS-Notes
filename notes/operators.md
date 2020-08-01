# JS Operators

---

[ << Previous Lesson - JS Data Types ](./data-types.md) 


## Arithmetic Operators 

### Overview

| Operator | Description      |
| -------- | ---------------- |
| +        | Addition         |
| -        | Subtraction      |
| *        | Multiplication    |
| /        | Division          |
| %        | Modulus        |
| ++       | Increment       |
| --       | Decrement       |
| **       | Exponentiation   |




### Numeric Strings 

Example:

````js
//Numeric Strings
//JavaScript will try to convert strings to numbers in all numeric operations:
console.log( "100" * "10" ); //1000
console.log( "100" / "10" ); //10
console.log( "100" - "10" ); //90
console.log( "100" + "10" ); //"10010" (here "+" is used to concatenate strings, instead of add numbers)

console.log( "Hello" - "Dolly" );   // NaN
````



### Confused case for ++/--

> `cnt++`: postfix ++
>
> `++cnt`: prefix ++

Example:

```js
var cnt = 0;
function inc(){
	return cnt++;
}

for(i=0 ; i< 5 ; i++){
	console.log(inc());
}
```

result:

```
0
1
2
3
4
```



---

## Assignment Operators 

Assign values to JavaScript variables. 

| Operator           | Description         |
| ------------------ | ------------------- |
| =                  |                     |
| +=                 |                     |
| -=                 |                     |
| *=                 |                     |
| /=                 |                     |
| %=                 | same as "x = x % y" |
| <<=, &=, **=, etc. |                     |


> The **= operator is an experimental part of the ECMAScript 2016 proposal (ES7). It is not stable across browsers. Do not use it.


---

## Comparison Operators 

### Overview


| Operator | Description                       |
| -------- | --------------------------------- |
| ==       | equal value                       |
| ===      | equal value and equal type        |
| !=       | not equal                         |
| !==      | not equal value or not equal type |
| >        | greater than                      |
| <        | less than                         |
| >=       | greater than or equal to          |
| <=       | less than or equal to             |


> **Best Practice: Use === Comparison**
> * The `==` comparison operator always converts (to matching types) before comparison.
> * The `===` operator forces comparison of values and type.




### Comparing Different Types

E.g
````js
console.log( 2 < 12 );      // true
console.log( 2 < "12" );    // true  (2 < 12)
console.log( 2 < "" );      // false (2 < 0)
console.log( 2 < "John" );  // false (2 < NaN)
console.log( 2 > "John" );  // false (2 > NaN)
console.log( 2 == "John" ); // false (2 == NaN)

console.log( Boolean( false == 0 ) );   // true
console.log( Boolean( false === 0 ) );  // false
console.log( Boolean( true == 1 ) );    // true
console.log( Boolean( true === 1 ) );   // false
console.log( Boolean( true == 2) );     // false

console.log( Boolean( null == 0) );            // false
console.log( Boolean( undefined == 0 ) );      // false
console.log( Boolean( null == undefined ) );   // true
console.log( Boolean( null === undefined ) );  // false

console.log( Boolean( 'John' > null ) );       // false
console.log( Boolean( 1 > null ) );            // true
console.log( Boolean( 0 > null ) );            // false
console.log( Boolean( 1 > NaN ) );             // false
````



### Comparing Strings

When comparing two strings, "2" will be greater than "12", because (alphabetically) 1 is less than 2.

```js
console.log( "2" < "12" );	// false ("2" < "1")
console.log( "2" > "12" );	// true  ("2" > "1")
console.log( "2" == "12" );	// false ("2" == "12")
```





----

## Ternary Operator

| Operator | Description      |
| -------- | ---------------- |
| ?        | ternary operator |

Example:

````js
var x = ( 10 > 9 ) ? 'Good' : 'Wow';
console.log(x);		// 'Good'
````



---

## Logical Operators

### Overview

| Operator | Description |
| -------- | ----------- |
| &&       | and         |
| \|\|     | or          |
| !        | not         |


### Comparison Operators VS. Logical Operators

* condition Value is either true or false, `Booelan()` 
  * In JS, `0`, `false`, `NaN`, `undefined`, `null`, `''` evaluate to false

* Example:

````js
false && 1 && 'hello'        // false
1 && false && 2 && 'hello'   // false
1 && 2 && 'hello'            // "hello"
1 && 2 && 'hello' && 0       // 0

false || NaN || '' || undefined || null || 0  // 0
false || 1 || 2 || 'hello'                    // 1

false || 1 || 'hello' && undefined || 2 && 0  // 1
// Evaluation Process:
// step 1: false || 1 || 'hello' && undefined || 2 && 0
// step 2: false || 1 || undefined || 0
// step 3: 1
````
---

## Concatenation Operators

### Overview

* Adding Strings using `+` and `+=`

````js
var name = "John" + " " + "Smith";
var text = "How are you?";
text += "Fine, thanks.";
````


### Concating Numbers and Strings

EX:

````js
var x = 5 + 2 + 3; //10 (numeric)
var y = 5 + 2 + "3"; //"73"(string data type)
var z = "5" + 2 + 3; //"523"
var x = 16 + "Volvo"; //(equal to) var x = "16" + "Volvo";
var x = 16 + 4 + "Volvo"; // "20Volvo"
var x = "Volvo" + 16 + 4; // Volvo164
var x = "Volvo" + (16 + 4); // Volvo20
````
---

## Type Operators

### Overview

| Operator   | Description                              |
| ---------- | ---------------------------------------- |
| typeof     | Returns the type of a variable           |
| instanceof | Returns true if an object is an instance of an object type |



### Example for typeof:

````js
typeof "John"                 // "string"
typeof 3.14                   // "number"
typeof false                  // "boolean"
typeof {name:'John', age:34}  // "object"
typeof [1,2,3,4]              // "object" (not "array", The typeof operator returns "object" for arrays because in JavaScript arrays are objects.)
typeof NaN                    // "number"
typeof new Date()             // "object"
typeof new String()           // "object"
typeof new Number()           // "object"
typeof new Boolean()          // "object"
typeof function () {}         // "function"
typeof myCar                  // "undefined" *
typeof null                   // "object"
````



### Example for instanceof:

> NOTE: **(Primitive) string, number `instanceof`**

````js
var s = 'abc';
console.log( typeof s );              // "string"
console.log( s instanceof String );   // false

var s2 = new String('abc');
console.log( typeof s2 );             // "object"
console.log( s2 instanceof String );  // true

var x = 1;
console.log( typeof x );              // "number"
console.log( x instanceof Number );	  // false
console.log( x instanceof Array );    // false

var ary = ['Apple', 'Banana', 'Cake'];
console.log( ary instanceof Array );  // true
````



---

## Bitwise Operators

*  __32 bit__ Out of our scope



---

## Operator Precedence 


````js
var x = 100 + 50 * 3;    // 250
var x = (100 + 50) * 3;  // 450
````



* JavaScript Operator Precedence Values

[Read More Operator Precedence ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
