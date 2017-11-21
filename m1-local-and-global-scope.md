# JavaScript Scope \(Local & Global\) & "use strict"

---

**Scope determines the accessibility \(visibility\) of variables.**

In JavaScript there are two types of scope:

* Local scope
* Global scope

JavaScript has function scope: Each function creates a new scope. Scope determines the accessibility \(visibility\) of these variables. Variables defined inside a function are not accessible \(visible\) from outside the function.

## [Local](https://developer.mozilla.org/en-US/docs/Glossary/Local_scope) JavaScript Variables

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

## [Global](https://developer.mozilla.org/en-US/docs/Glossary/Global_scope) JavaScript Variables

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

# Variable shadowing {#firstHeading}

In computer programming, variable shadowing occurs when a variable declared within a certain scope \(decision block, method, or inner class\) has the same name as a variable declared in an outer scope. At the level of identifiers \(names, rather than variables\), this is known as name masking. This outer variable is said to be shadowed by the inner variable, while the inner identifier is said to mask the outer identifier. This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language.

```
// variable a is declared both in global and local scope.
// This a bad practice and should be avoided.

var a = 3;
function b() {
    var a = 10;
}
```

To avoid this, you can add "no-shadow": "error" in the ES Lint rules so you get an error if this is done. Or use "use strict" on top of every file, which will generate an error if you do shadow variables by mistake in future.



