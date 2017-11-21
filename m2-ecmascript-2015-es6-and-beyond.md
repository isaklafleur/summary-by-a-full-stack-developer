# [ECMAScript 2015](http://www.ecma-international.org/ecma-262/6.0/) \(ES6\) and beyond

---

![](https://3.bp.blogspot.com/-HVJ8K4-fLT8/VyMo2yICM9I/AAAAAAAABKw/uhbcz1Br3-cMCrt4XamQjsmuEyD9pBYtgCLcB/s1600/shippedESFeatures.png)

## Block-Scoped Declarations

### `let`Declarations

can now create declarations that are bound to any block, called \(unsurprisingly\) _block scoping_

```js
var a = 2;

function test() {
  let a = 3;
  console.log( a ); // 3
}

console.log( a ); // 2
```

Accessing a `let`- declared variable earlier than its `let ..` declaration/initialisation causes an error, whereas with `var` declarations the ordering doesn't matter \(except stylistically\).

```js
{
    console.log( a );    // undefined
    console.log( b );    // ReferenceError!

    var a;
    let b;
}
```

### `const`Declarations

There's one other form of block-scoped declaration to consider: the`const`, which creates_constants_.

What exactly is a constant? It's a variable that's read-only after its initial value is set.

```js
{
  const a = 2;
  console.log( a ); // 2
  a = 3; // TypeError!
}
```

You are not allowed to change the value the variable holds once it's been set, at declaration time. A `const` declaration must have an explicit initialisation. If you wanted a \_constant \_with the `undefined` value, you'd have to declare `const a = undefined` to get it.

Constants are not a restriction on the value itself, but on the variable's assignment of that value. In other words, the value is not frozen or immutable because of `const` , just the assignment of it. If the value is complex, such as an object or array, the contents of the value can still be modified.

```js
{
  const a = [1,2,3];
  a.push( 4 );
  console.log( a ); // [1,2,3,4]

  a = 42; // TypeError!
}
```

---

## [Spread](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)/[Rest](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)

### Spread in function calls {#Spread_in_function_calls}

```js
function myFunction(x, y, z) { }
var args = [0, 1, 2];
myFunction.apply(null, args);

// to ->

function myFunction(x, y, z) { }
var args = [0, 1, 2];
myFunction(...args);
```

### Spread in array literals {#Spread_in_array_literals}

```js
var parts = ['shoulders', 'knees']; 
var lyrics = ['head', ...parts, 'and', 'toes']; 
// ["head", "shoulders", "knees", "and", "toes"]
```

```js
var arr = [1, 2, 3];
var arr2 = [...arr]; // like arr.slice()
arr2.push(4); 

// arr2 becomes [1, 2, 3, 4]
// arr remains unaffected
```

```js
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
// Append all items from arr2 onto arr1
arr1 = arr1.concat(arr2);

// to ->

var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
arr1 = [...arr1, ...arr2];
```

```js
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
// Prepend all items from arr2 onto arr1
Array.prototype.unshift.apply(arr1, arr2) // arr1 is now [3, 4, 5, 0, 1, 2]

// to ->

var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
arr1 = [...arr2, ...arr1]; // arr1 is now [3, 4, 5, 0, 1, 2]
```

```
// instead of using Object.assign()

var clonedObj = { ...obj1 };
// Object { foo: "bar", x: 42 }
```

---

## [Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

In ES5 and earlier, constructor functions defined “classes” like this:

```js
function MyClass() { }

var myClass = new MyClass();
```

ES2015 introduces a new syntax using the class keyword:

```js
class MyClass {
  constructor() {  }
}
var myClass = new MyClass();
```

ES2015 did not redefine the role and purpose of the constructor function; it simply cleaned up the syntax.

```js
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}
```

The equivalent constructor function with ES2015 syntax looks like this:

```js
// the name of the ES5 constructor
// function is name of the ES2015 class
class Person {

  // observe there is no "function" keyword
  // also, the word "constructor" is used, not "Person"
  constructor(firstName, lastName) {

    // this represents the new object being
    // created and initialized
    this.firstName = firstName;
    this.lastName = lastName;

  }
}
```

To instantiate objects with either syntax, the code is the same.

```js
var person = new Person("Bob", "Smith");

// outputs "Bob"
console.log(person.firstName);

// outputs "Smith"
console.log(person.lastName);
```

### [**Extending Classes**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#Sub_classing_with_extends)

Prior to ES2015, most developers who coded JavaScript did not understand how to setup an inheritance relationship between objects. A quick conversation with a C++, Java, or C\# developer would quickly reveal the ease with which they could setup one class to inherit from another, and then instantiate an object from the subclass. Ask a typical JavaScript developer to demonstrate how to setup inheritance between two objects, and the result is usually a blank stare. The reason for this great difference is that configuring prototype inheritance is not straightforward, and the concept of prototype inheritance is foreign to most JavaScript developers. Here is some example code with comments to explain the process of configuring inheritance.

```js
// Person constructor function
// when called with the "new" operator,
// a new Person object is created

function Person(firstName, lastName) {
  // the "new" operator sets the reference of
  // "this" to a new object
  this.firstName = firstName;
  this.lastName = lastName;
}

// this property referencing the function will
// be configured on person's prototype object,
// and will be inherited by students
Person.prototype.getFullName = function() {
  return this.firstName + " " + this.lastName;
};

// Student constructor function
// when called with the "new" operator,
// a new Student object is created

function Student(studentId, firstName, lastName) {
  // the "new" operator sets the reference of "this" to
  // a new object, the new object is then passed to the
  // Person constructor function through the use of call,
  // so the first name and last name properties can be set
  this._super.call(this, firstName, lastName);
  this.studentId = studentId;
}

// students will inherit from a new object
// which inherits from the parent
Student.prototype = Object.create(Person.prototype);

// set the constructor property back to the Student
// constructor function
Student.prototype.constructor = Student;

// "_super" is NOT part of ES5, its a convention
// defined by the developer
// set the "_super" to the Person constructor function
Student.prototype._super = Person;

// this will exist on the student's prototype object
Student.prototype.getStudentInfo = function() {
  return this.studentId + " " + this.lastName + ", " + this.firstName;
};

// instantiate a new Student object
var student = new Student(1, "Bob", "Smith");

// invoking function on parent prototype
// outputs "Bob Smith"
console.log(student.getFullName());

// invoking function on child prototype
// output "1 Smith, Bob"
console.log(student.getStudentInfo());
```

The above code is hard to follow, and it takes a lot of work just for one object to inherit from another while supporting constructor functions. Most JavaScript developers cannot create this code from memory, and many have never seen or considered anything like this when working with JavaScript.

To solve this problem and bring prototype inheritance into greater usage, ES2015 has introduced the **extends **keyword to the syntax of its new class structure. The following code demonstrates the same inheritance as the first code sample, but uses ES2015 syntax.

```js
"use strict";

class Person {

  constructor(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }

  getFullName() {
    return this.firstName + " " + this.lastName;
  }
}

class Student extends Person {
  constructor(studentId, firstName, lastName) {
    super(firstName, lastName);
    this.studentId = studentId;
  }

  getStudentInfo() {
    return this.studentId + " " + this.lastName + ", " + this.firstName;
  }

}

var student = new Student(1, "Bob", "Smith");
console.log(student.getFullName());
console.log(student.getStudentInfo());
```

---

## [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

ES6 fat arrow functions have a shorter syntax compared to function expressions and lexically bind the `this` value. Arrow functions are always anonymous and effectively turn `function (arguments) { expression }` into `arguments => expression`. If using an expression after an arrow, the return is implicit, so no `return` is required.

```js
'use strict';
// Filter an array for only odd numbers
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];

// Before...
let es5OddNumbers = numbers.filter(function(number) {
  return number % 2;
});
ChromeSamples.log(es5OddNumbers);

// After...
let es6OddNumbers = numbers.filter(number => number % 2);
ChromeSamples.log(es6OddNumbers);

// Parens are optional depending on the number of arguments:
let square = x => x * x;
ChromeSamples.log(square(10));

let add = (a, b) => a + b;
ChromeSamples.log(add(3, 4));

// `return` is implied if using an expression after an arrow.
let developers = [{name: 'Rob'}, {name: 'Jake'}];
// Before...
let es5Output = developers.map(function(developer) {
  return developer.name;
});
ChromeSamples.log(es5Output);

// After...
let es6Output = developers.map(developer => developer.name);
ChromeSamples.log(es6Output);

// Fat arrows change how `this` is handled.

// Before...
// In ES5, `bind()` or var that = this; are necessary as functions
// create their own `this`. We need to store the parent `this` in
// a variable that can be referenced in the callback or take care
// of binding ourselves.
function CounterES5() {
  this.seconds = 0;
  window.setInterval(function() {
    this.seconds++;
  }.bind(this), 1000); // or }.bind(this), 1000) and skip that = this
}

var counterA = new CounterES5();
window.setTimeout(function() {
  ChromeSamples.log(counterA.seconds);
}, 1200);

// After...
// ES6 Arrows instead bind `this` to the immediate enclosing
// lexical scope:
function CounterES6() {
  this.seconds = 0;
  window.setInterval(() => this.seconds++, 1000);
}

let counterB = new CounterES6();
window.setTimeout(() => ChromeSamples.log(counterB.seconds), 1200);
```

---

## [Template Literals \(String Literals\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

In JavaScript, when you want to put a variable inside of a string, it’s a pain in the ass because you have to stop your string, concatenate on the variable, and then open your string again and keep going. What ends up happening is you forget one of your closing quotes, and you get an error and it tells you it’s on line 3. You say “Of course it’s on line 3, but I don’t know where it is!”

We can fix all of that with what’s called **template strings**, or **template literals **in ES6. In JavaScript we have double quotes and single quotes to make a string. Now we have a third way to make a string, and that is with back-ticks.

```js
// Simple string substitution
var name = "Brendan";
console.log(`Yo, ${name}!`);

// => "Yo, Brendan!"
```

```js
var a = 10;
var b = 10;
console.log(`JavaScript first appeared ${a+b} years ago. Crazy!`);

//=> JavaScript first appeared 20 years ago. Crazy!

console.log(`The number of JS MVC frameworks is ${2 * (a + b)} and not ${10 * (a + b)}.`);
//=> The number of JS frameworks is 40 and not 200.
```

## Promises

A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved \(e.g., a network error occurred\). A promise may be in one of 3 possible states: fulfilled, rejected, or pending. Promise users can attach callbacks to handle the fulfilled value or the reason for rejection.

Promises are eager, meaning that a promise will start doing whatever task you give it as soon as the promise constructor is invoked.

### How Promises Work? {#443c}

A promise is an object which can be returned synchronously from an asynchronous function. It will be in one of 3 possible states:

* **Fulfilled: **`onFulfilled()` will be called \(e.g., `resolve()` was called\)
* **Rejected: **`onRejected()` will be called \(e.g., `reject()` was called\)
* **Pending: **not yet fulfilled or rejected

A promise is **settled **if it’s not pending \(it has been resolved or rejected\). Sometimes people use _resolved _and _settled _to mean the same thing: _not pending_.

Once settled, a promise can not be resettled. Calling `resolve()` or `reject()` again will have no effect. The immutability of a settled promise is an important feature.

### Promise Chaining {#a7ba}

```js
save()
  .then(handleSuccess)
  .catch(handleErrors);
```

![](https://cdn-images-1.medium.com/max/800/1*vRaV9sYpYKdxBj3Ld7KM1Q.png)

In the above example/image, `.catch()` will handle rejections from either `save()`, or `handleSuccess()`.

When then invokes the specified function, that function receives as a parameter the resolved value of the promise. So, for example, when getCollection is called, a handle to the database will be passed to it.

### Promise.all



