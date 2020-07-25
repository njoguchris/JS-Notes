# JS Functions (Code Blocks)

[ << Previous Lesson - JS Variables](./variables.md) | [Next Lesson >> JS Data Types](./data-types.md)


## Function Basic Examples

```js
// Example 1
function myFunction() {
  console.log('Hello!');
}

// Example 2 (with paramters)
function myMath(p1, p2) {
  return p1 * p2; // The function returns the product of p1 and p2
}
console.log( myMath(4, 3) );

// Example 3 (another ways to declare function)
function func1(){ console.log("111"); }
var func2 = function(){ console.log("222"); }
var func4 = function func3(){ console.log("333"); } // invalid syntax
var func5 = func2;
func1(); //111
func2(); //222
func3(); //ReferenceError: func3 is not defined
func4(); //333
func5(); //222
```



----

## Function 


```js
// declaration function
function toCelsius(f) {
  return (5/9) * (f-32);
}

console.log( toCelsius ); // "ƒ toCelsius(f) { return (5/9) * (f-32); }" (return the function definition)
console.log( toCelsius(77) ); //25
console.log( typeof toCelsius ); //"function"
console.log( typeof toCelsius(77) ); //"number"
```



----

## Function Definition


> ES6  —— Arrow Function

#### 1. ** (function declarations)**

````js
//syntax 1: Function Declarations (Hoisting)
console.log(myFunc1); // ƒ myFunc1(a, b) {return a * b;}
function myFunc1(a, b) {
    return a * b;
}
````


#### 2. ** (function expressions without function name)**

*  function  anonymous function (a function without a name)
*  function body  function 

````js
//syntax 2: Function Expressions w/o function name
var myFunc2 = function (a, b) {return a * b};
console.log(myFunc2); // ƒ (a, b) {return a * b}
````


#### 3. ** (function expressions w/ function name)** *()*

*  function name ()
* **function name **
* ( function scope，scope name，function name)

````js
//syntax 3: Function Expressions w/ function name
var myFunc2 = function aaa(a, b) {return a * b};
console.log(myFunc2); // ƒ aaa(a, b) {return a * b}
console.log(aaa); // Uncaught ReferenceError: aaa is not defined
````


#### 4. **  (function constructor)** *()*

* with a built-in JavaScript function constructor called `Function()`
* **it's unnecessary to use this way**

````js
//syntax 4: Function Constructor
var myFunc3 = new Function("a", "b", "return a * b");
console.log(myFunc3); // ƒ anonymous(a,b /*``*/) { return a * b }
````



### 

1.  Hoisting，expression, constructor 
  > ES6 Arrow Function 

2. Function 
  * expression w/o name  function
  * constructor


----


## Functions 

> A Function is much the same as a Procedure or a Subroutine, in other programming languages.

* __Function names__ :
* 
  * __Function parameters__ : (are the names listed in the function definition.)
  * __Function arguments__ : (are the real values received by the function when it is invoked.)
  * arguements paramters  local  (Inside the function, the arguments (the parameters) behave as local variables.)
* __Function Return__ : When JavaScript reaches a return statement, the function will stop executing.
* **Function Signature**:
*  **Function overloadding **

Example 1:

````js
myFunc();

function myFunc(){
  console.log('111');
}
function myFunc(p1){
  console.log('222');
}

//***** result *****
//222
````

Example 2:

````js
myFunc();

function myFunc(){
  console.log('111');
}
var myFunc = function(p1){
  console.log('222');
}

myFunc();

//***** result *****
//111 (because of Hosting)
//222
````



----

## Function Parameters & Arguments

### Parameters v.s. Arguments

mynote:

1. **arguments** 
2. **parameters**  type `undefined`



Example:

```js
function myFunc(a1, a2, a3){
  console.log("typeof a1=", typeof a1);
  console.log("a1=", a1);

  console.log("typeof arguments=", typeof arguments);
  console.log("arguments=", arguments);

  console.log("typeof arguments[0]=", typeof arguments[0]);
  console.log("arguments[0]=", arguments[0]);
}

console.log("====trial 1");
myFunc();
console.log("====trial 2");
myFunc("apple", "banana", "cookie", "egg");
```

Result:

```
====trial 1
typeof a1= undefined
a1= undefined
typeof arguments= object
arguments= [callee: ƒ, Symbol(Symbol.iterator): ƒ]
typeof arguments[0]= undefined
arguments[0]= undefined

====trial 2
typeof a1= string
a1= apple
typeof arguments= object
arguments= (4) ["apple", "banana", "cookie", "egg", callee: ƒ, Symbol(Symbol.iterator): ƒ]
typeof arguments[0]= string
arguments[0]= apple
```



### Function Parameter Defaults

 (called with a missing argument)

```js
myFunction(5);
function myFunction(x, y) {
    if (y === undefined) {
        y = 99;
    }
    console.log(y);
}

//**********result*********
//99
```

ES6 

```js
myFunction(5);
function myFunction(x, y=99) {
    console.log(y);
}

//**********result*********
//99
```



### Function Arguments Object

* JavaScript functions have a built-in object called the **arguments object**.
*  arguments

```js
x = findMax(1, 123, 500, 115, 44, 88);
x = sumAll(1, 123, 500, 115, 44, 88);

function findMax() {
    var i;
    var max = -Infinity;
    for (i = 0; i < arguments.length; i++) {
        if (arguments[i] > max) {
            max = arguments[i];
        }
    }
    return max;
}
function sumAll() {
    var i;
    var sum = 0;
    for (i = 0; i < arguments.length; i++) {
        sum += arguments[i];
    }
    return sum;
}
```

> Note: ES6  Arrow Function  arguments, function


---

## Function Invocation

### 

1. When an event occurs (e.g. when an user clicks a button)
2. When it is invoked (called) from JavaScript code
3. Automatically (self invoked)




### Self-Invoking Functions

#### Intro

* `Function expressions` can be made " **self-invoking** ".
  * A self-invoking expression 
 
* You **cannot** self-invoke a function declaration.



#### Examples

````js
// syntax 1: an anonymous self-invoking function
(function () {
    var x = "Hello!!";      // I will invoke myself
    console.log('222');
})();

// syntax 2: a self-invoking function with naming
(function abc () {
    var x = "Hello!!";      // I will invoke myself
    console.log('222');
})();
abc(); // ReferenceError: abc is not defined
````



#### 1 :  local scope


Before:

````js
var x = "Hello";
console.log(x);
console.log('Do something.....');
console.log(x); // x is still alive

//******** reuslt **********
// "Hello"
// "Do something....."
// "Hello"
````


After:

````js
(function () {
    var x = "Hello";      // I will invoke myself
    console.log(x);
})();

console.log('Do something.....');
console.log(x);

//******** reuslt **********
// "Hello"
// "Do something....."
// ReferenceError: x is not defined
````



#### 2 : 

 local scope 

````js
var add = (function () {
    var counter = 0;
    return function () {return counter += 1;}
})();
console.log(add);
console.log(add());
console.log(add());

// *****result*****
// ƒ () {return counter += 1;}
// 1
// 2
````

 `add`

````js
var add = function() {
    var counter = 0;
    return function () {return counter += 1;}
};
console.log(add);
console.log(add());
console.log(add());

// *****result*****
// ƒ () {
//     var counter = 0;
//     return function () {return counter += 1;}
// }
// ƒ () {return counter += 1;}
// ƒ () {return counter += 1;}
````



#### 3 : 

````js
var person = {
	age: (function (){ return 18; })()
};
console.log(person.age); //18
````



#### 4 :  function

 function ( JSON  function )

````js
var text = '{ "name":"John", "age":"function () {return 30;}", "city":"New York"}';
var obj = JSON.parse(text);
console.log(typeof obj.age); //"string"
console.log(obj.age); //"function () {return 30;}"
var ageFunc = eval("(" + obj.age + ")");
console.log(ageFunc); //ƒ () {return 30;}
console.log(ageFunc()); //30
````


----

## Functions are Objects

* JavaScript functions  **objects**
  - `typeof` "function"
  -  properties, methods,objects methods，function (e.g. `toString()`)


```js
function myFunc(a, b) { return a * b; }
console.log(myFunc.toString()); // "function myFunc(a, b) { return a * b; }"
```

> * function  object property **method** to the object.
>
>
> * function  new objects，object **constructor**.



## Function Constructors

> The `this` keyword in the constructor does not have a value.    
> The value of `this` will be the new object created when the function is invoked.



```js
// This is a function constructor:
function Person(arg1, arg2) {
    this.firstName = arg1;
    this.lastName  = arg2;
    this.sayHi = function(){
    	return "Hi, I'm " + this.firstName + " " + this.lastName;
    }
}

// This creates a new object
var x = new Person("John", "Doe");
console.log(x);
console.log(x.firstName);
console.log(x.sayHi());

//====== result:
//Person {firstName: "John", lastName: "Doe", sayHi: ƒ}
//John
//Hi, I'm John Doe
```



----

## Functions are Object Methods

- JavaScript functions object method

````js
var myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
        return this.firstName + " " + this.lastName;
    }
}
myObject.fullName();         // Will return "John Doe"
````



-  function object method，global object method

```js
function myFunction(a, b) {
    return a * b;
}
//myFunction() and window.myFunction() is the same function
myFunction(10, 2);
window.myFunction(10, 2);
```

> Using the window object as a variable can easily crash your program.



----

## Nested Functions  (Function)

inner function

```js
function add() {
    var counter = 0;
    function plus() {counter += 1;}
    plus();
    return counter;
}

console.log(add);
console.log(add());
console.log(add());
console.log(add());

// *****result*****
// ƒ add() {
//    var counter = 0;
//    function plus() {counter += 1;}
//    plus();
//    return counter;
// }
// 1
// 1
// 1
```



----

## Callback

A callback function is a function passed as a parameter to another function.



----


