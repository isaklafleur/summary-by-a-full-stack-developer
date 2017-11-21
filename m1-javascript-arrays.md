# JavaScript Arrays

[Read more at MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

JavaScript arrays are used to store multiple values in a single variable.

```js
// Example

var cars = ["Saab", "Volvo", "BMW"];
```

## What is an Array?

An array is a special variable, which can hold more than one value at a time.

If you have a list of items \(a list of car names, for example\), storing the cars in single variables could look like this:

```js
var car1 = "Saab";
var car2 = "Volvo";
var car3 = "BMW";
```

However, what if you want to loop through the cars and find a specific one? And what if you had not 3 cars, but 300?

The solution is an array!

An array can hold many values under a single name, and you can access the values by referring to an index number.

---

**Create an Array**

```js
var fruits = ['Apple', 'Banana'];

console.log(fruits.length);
// 2
```

**Access \(index into\) an Array item**

```js
var first = fruits[0];
// Apple

var last = fruits[fruits.length - 1];
// Banana
```

**Loop over an Array \(in this case a **[**forEach method**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).** A **[**for loop**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)** can also be used\)**

```js
fruits.forEach(function(item, index, array) {
  console.log(item, index);
});
// Apple 0
// Banana 1
```

**Add to the end of an Array**

```js
var newLength = fruits.push('Orange');
// ["Apple", "Banana", "Orange"]
```

**Remove from the end of an Array**

```js
var last = fruits.pop(); // remove Orange (from the end)
// ["Apple", "Banana"];
```

**Remove from the front of an Array**

```js
var first = fruits.shift(); // remove Apple from the front
// ["Banana"];
```

**Add to the front of an Array**

```js
var newLength = fruits.unshift('Strawberry') // add to the front
// ["Strawberry", "Banana"];
```

**Find the index of an item in the Array**

```js
fruits.push('Mango');
// ["Strawberry", "Banana", "Mango"]

var pos = fruits.indexOf('Banana');
// 1
```

**Remove an item by index position**

```js
var removedItem = fruits.splice(pos, 1); // this is how to remove an item

// ["Strawberry", "Mango"]
```

**Remove items from an index position**

```js
var vegetables = ['Cabbage', 'Turnip', 'Radish', 'Carrot'];
console.log(vegetables); 
// ["Cabbage", "Turnip", "Radish", "Carrot"]

var pos = 1, n = 2;

var removedItems = vegetables.splice(pos, n); 
// this is how to remove items, n defines the number of items to be removed,
// from that position(pos) onward to the end of array.

console.log(vegetables); 
// ["Cabbage", "Carrot"] (the original array is changed)

console.log(removedItems); 
// ["Turnip", "Radish"]
```

**Copy an Array**

```js
var shallowCopy = fruits.slice(); // this is how to make a copy
// ["Strawberry", "Mango"]
```

---

### Accessing array elements {#Accessing_array_elements}

JavaScript arrays are zero-indexed: **the first element of an array is at index**`0`, and the last element is at the index equal to the value of the array's[`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)property minus 1. Using an invalid index number returns`undefined`.

```js
var arr = ['this is the first element', 'this is the second element'];
console.log(arr[0]);              // logs 'this is the first element'
console.log(arr[1]);              // logs 'this is the second element'
console.log(arr[arr.length - 1]); // logs 'this is the last element'
```

### A JavaScript array's [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length) property

```js
var fruits = [];
fruits.push('banana', 'apple', 'peach');

console.log(fruits.length); // 3
```

![](https://i.imgur.com/BG4RUNt.png)

---

## forEach\(\) method

`forEach()` executes the provided `callback` once for each element present in the array in ascending order. It is not invoked for index properties that have been deleted or are uninitialized \(i.e. on sparse arrays\).

```js
// syntax

arr.forEach(function callback(currentValue, index, array) {
    //your iterator
}[, thisArg]);



// example

const arr = ['a', 'b', 'c'];

arr.forEach(function(element) {
    console.log(element);
});

// a
// b
// c
```

### Parameters {#Parameters}

`callback`: Function to execute for each element, taking three arguments:

`currentValue` : The value of the current element being processed in the array.

`index`: The index of the current element being processed in the array.

`array`: The array that `forEach()`is being applied to



### Converting from for to forEach {#Converting_from_for_to_forEach}

before

```js
const items = ['item1', 'item2', 'item3'];
const copy = [];

for (let i=0; i<items.length; i++) {
  copy.push(items[i])
}
```

after

```js
const items = ['item1', 'item2', 'item3'];
const copy = [];

items.forEach(function(item){
  copy.push(item)
});
```



