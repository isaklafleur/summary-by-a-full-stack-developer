# JavaScript Objects

---

An object is a collection of related data and/or functionality \(which usually consists of several variables and functions — which are called properties and methods when they are inside objects.\) Let's work through an example to show us what they look like.

As with many things in JavaScript, creating an object often begins with defining and initializing a variable. Try entering the following below the JavaScript code that's already in your file, then saving and refreshing:

```js
var person = {};
```

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

person.name[0] // 'Bob'
person.age // 32
person.interests[1] // 'skiing
person.bio() // function() {...}
person.greeting() // function() {...}
```

So what is going on here? Well, an object is made up of multiple members, each of which has a name \(e.g.`name`and `age`above\), and a value \(e.g.`['Bob', 'Smith']`and `32`\). Each name/value pair must be separated by a comma, and the name and value in each case are separated by a colon. The syntax always follows this pattern:

```js
var objectName = {
  member1Name: member1Value,
  member2Name: member2Value,
  member3Name: member3Value
}
```

## Accessing data from an object {#Dot_notation}

### Dot notation

accessing the object's properties and methods using **dot notation**

```js
person.age
person.interests[1]
person.bio()
```

### Bracket notation

There is another way to access object properties — using bracket notation.

```js
person['age']
person['interests'][1]
```

## Setting object members {#Setting_object_members}

```js
person.age = 45;
person['name'] = 'Cratchit';
```

Setting members doesn't just stop at updating the values of existing properties and methods; you can also create completely new members. Try these:

```js
person['eyes'] = 'hazel';
person.farewell = function() { alert("Bye everybody!"); }
```

## A few Object Methods

### Object.entries\(\)

```js
const obj = { foo: 'bar', baz: 42 };
console.log(Object.entries(obj)); // [ ['foo', 'bar'], ['baz', 42] ]

// array like object
const obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.entries(obj)); // [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ]

// array like object with random key ordering
const anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.entries(anObj)); // [ ['2', 'b'], ['7', 'c'], ['100', 'a']
```

### Object.values\(\)

```js
var obj = { foo: 'bar', baz: 42 };
console.log(Object.values(obj)); // ['bar', 42]

// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.values(obj)); // ['a', 'b', 'c']

// array like object with random key ordering
var an_obj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.values(an_obj)); // ['b', 'c', 'a']
```

### Object.keys\(\)

```js
var arr = ['a', 'b', 'c'];
console.log(Object.keys(arr)); // console: ['0', '1', '2']

// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.keys(obj)); // console: ['0', '1', '2']

// array like object with random key ordering
var anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.keys(anObj)); // ['2', '7', '100']
```





