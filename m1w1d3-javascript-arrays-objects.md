# Javascript Data Structures

---

## [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

When you need to depend on the _order _of the elements in the collection, use Arrays.

```js
var fruits = ['Apple', 'Banana']; // Array of Strings
var ages = [10, 11, 32, 1]; // Array of Numbers
var pairs = [[10, 33], [44, 11], [97, 32]]; // Array of Arrays
var people = [
  { name: "Thomas", age: 22 },
  { name: "Anders", age: 24 },
  { name: "Björn", age: 67 },
]; // Array of Objects.
```

## [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

when order is not important, use objects. Order is not guaranteed in objects, but they provide for fast key-value pair lookups.

```js
var person = {
  name: ['Bob', 'Smith'],
  age: 32,
  gender: 'male',
  interests: ['music', 'skiing'],
  bio: function() {
    alert(this.name[0] + ' ' + this.name[1] + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
  },
  greeting: function() {
    alert('Hi! I\'m ' + this.name[0] + '.');
  }
};
```



