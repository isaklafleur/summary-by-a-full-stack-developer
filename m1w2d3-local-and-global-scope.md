# JavaScript Scope \(Local & Global\) & "use strict"

---

**Scope determines the accessibility \(visibility\) of variables.**

In JavaScript there are two types of scope:

* Local scope
* Global scope

JavaScript has function scope: Each function creates a new scope. Scope determines the accessibility \(visibility\) of these variables. Variables defined inside a function are not accessible \(visible\) from outside the function.

## Local JavaScript Variables

Variables declared within a JavaScript function, become **LOCAL **to the function.

Local variables have **local scope**: They can only be accessed within the function.

```js
// code here can not use carName

function myFunction() {
    var carName = "Volvo";
    // code here can use carName
}
```

Since local variables are only recognised inside their functions, variables with the same name can be used in different functions. Local variables are created when a function starts, and deleted when the function is completed.

## Global JavaScript Variables

A variable declared outside a function, becomes **GLOBAL**.

A global variable has **global scope**: All scripts and functions on a web page can access it.

```js
var carName = " Volvo";

// code here can use carName

function myFunction() {
    // code here can use carName
}
```

## JavaScript Variables

In JavaScript, objects and functions are also variables. Scope determines the accessibility of variables, objects, and functions from different parts of the code.

## Automatically Global

If you assign a value to a variable that has not been declared, it will automatically become a **GLOBAL**variable.

This code example will declare a global variable **carName**, even if the value is assigned inside a function.

```js
myFunction();

// code here can use carName 

function myFunction() {
    carName = "Volvo";
}
```

## ["use strict"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) - Strict mode for scripts

To invoke strict mode for an entire script, put the **exact** statement

`"use strict";`\(or`'use strict';`\) before any other statements.

**Global variables are not created automatically in "Strict Mode".**

```js
'use strict';

// Assignment to a non-writable global
var undefined = 5; // throws a TypeError
var Infinity = 5; // throws a TypeError

var dontDoThis = 10; // ReferenceError: dontDoThis is not defined

function helloWorld() {
  test = "world";
  console.log("hello" + test);
}
helloWorld(); // ReferenceError: test is not defined
```



