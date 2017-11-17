# JavaScript Functions

[Read more at MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

---

Functions are one of the fundamental building blocks in JavaScript. A function is a JavaScript procedure—a set of statements that performs a task or calculates a value. To use a function, you must define it somewhere in the scope from which you wish to call it.

* **A JavaScript function is a block of code designed to perform a particular task.**

* **A JavaScript function is executed when "something" invokes it \(calls it\). **

### Function declarations {#Function_declarations}

A **function definition **\(also called a **function declaration**, or **function statement**\) consists of the[`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)keyword, followed by:

* The name of the function.
* A list of parameters to the function, enclosed in parentheses and separated by commas.
* The JavaScript statements that define the function, enclosed in curly brackets,`{ }`

For example, the following code defines a simple function named `square`:

```js
function square (number) {
 return number * number;
}
```

The function`square`takes one parameter, called`number`. The function consists of one statement that says to return the parameter of the function \(that is,`number`\) multiplied by itself. The[`return`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return)statement specifies the value returned by the function.

```js
return number * number;
```

### Function expressions {#Function_expressions}

While the function declaration above is syntactically a statement, functions can also be created by a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). Such a function can be **anonymous**; it does not have to have a name. For example, the function`square`could have been defined as:

```js
var square = function (number) {
  return number * number;
};

var x = square(4);
// x gets the value 16
```

### Calling functions

Defining a function does not execute it. Defining the function simply names the function and specifies what to do when the function is called.**Calling**the function actually performs the specified actions with the indicated parameters. For example, if you define the function`square`, you could call it as follows:

```js
square(5);
```

The preceding statement calls the function with an argument of 5. The function executes its statements and returns the value 25.

Functions must be in scope when they are called, but the function declaration can be hoisted \(appear below the call in the code\), as in this example:

```js
console.log(square(5));
/* ... */
function square(n) { return n * n; }
```

The scope of a function is the function in which it is declared, or the entire program if it is declared at the top level.

###### **Note: **This works only when defining the function using the above syntax \(i.e.`function funcName(){}`\). The code below will not work. That means, function hoisting only works with function declaration and not with function expression.

```js
console.log(square); // square is hoisted with an initial value undefined.
console.log(square(5)); // TypeError: square is not a function
var square = function(n) { 
  return n * n; 
}
```

The arguments of a function are not limited to strings and numbers. You can pass whole objects to a function. The`show_props()`function \(defined in[Working with objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#Objects_and_Properties)\) is an example of a function that takes an object as an argument.

## JavaScript built-in Methods\* \(Methods of the global constructors\)

* [Math Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) ex. Math.floor\(\), Math.random\(\), Math.max\(\), Math.min\(\)
* [Number Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) ex isNaN\(\), parseFloat\(\), parseInt\(\), toFixed\(\), toString\(\)
* [Date Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) ex. Date.now\(\), Date.parse\(\), 
* [String Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) ex. length, includes\(\), indexOf\(\), slice\(\), substr\(\), substring\(\), toUpperCase\(\), toLowerCase\(\), trim\(\), split\(\)
* [Array Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) ex. length, pop\(\), push\(\), shift\(\), unshift\(\), reverse\(\), sort\(\), slice\(\), includes\(\), indexOf\(\), join\(\)
* [Object Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
* [RegEX Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
* [JSON Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)
* [Promise Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

###### \* A function defined inside an Object is called a Method.



