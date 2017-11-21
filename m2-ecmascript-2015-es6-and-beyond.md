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

## Classes

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



