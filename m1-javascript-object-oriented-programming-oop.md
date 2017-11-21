# [JavaScript Object Oriented Programming \(OOP\)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)

---

Object Oriented Programming \(OOP\) refers to using self-contained pieces of code to develop applications. We call these self-contained pieces of code **objects**, better known as Classes in most OOP programming languages and Functions in JavaScript. We use objects as building blocks for our applications. Building applications with objects allows us to adopt some valuable techniques, namely, **Inheritance **\(objects can inherit features from other objects\), **Polymorphism **\(objects can share the same interface—how they are accessed and used — while their underlying implementation of the interface may differ\), and **Encapsulation **\(each object is responsible for specific tasks\).

```js
function Person(name) {
  this.name = name;
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name + '.');
  };
}
// Note: A constructor function name usually starts with a capital letter — this convention
// is used to make constructor functions easier to recognize in code.
```

The constructor function is JavaScript's version of a class. You'll notice that it has all the features you'd expect in a function, although it doesn't return anything or explicitly create an object — it basically just defines properties and methods. You'll see the `this` keyword being used here as well — it is basically saying that whenever one of these object instances is created, the object's `name` property will be equal to the name value passed to the constructor call, and the `greeting()` method will use the name value passed to the constructor call too.

```js
// So how do we call a constructor to create some objects?
// Add the following lines below your previous code addition:

var person1 = new Person('Bob');
var person2 = new Person('Sarah');
```

Save your code and reload it in the browser, and try entering the following lines into your text input:

```js
person1.name
person1.greeting()
person2.name
person2.greeting()
```

```js
// a fairly common pattern for more object definitions is to define
// the properties inside the constructor, and the methods on the prototype.
// This makes the code easier to read, as the constructor only contains the
// property definitions, and the methods are split off into separate blocks.
// For example:

// Constructor with property definitions

function Test(a, b, c, d) {
  // property definitions
};

// First method definition

Test.prototype.x = function() { ... }

// Second method definition

Test.prototype.y = function() { ... }

// etc.
```

## [Prototypal inheritance](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance) {#Prototypal_inheritance}

In "classic OO" languages, you tend to define class objects of some kind, and you can then simply define which classes inherit from which other classes \(see [C++ inheritance](http://www.tutorialspoint.com/cplusplus/cpp_inheritance.htm) for some simple examples\). JavaScript uses a different system — "inheriting" objects do not have functionality copied over to them, instead the functionality they inherit is linked to via the prototype chain \(often referred to as **prototypal inheritance**\).

```js
// We define only the properties inside the constructor

function Person(first, last, age, gender, interests) {
  this.name = {
    first,
    last
  };
  this.age = age;
  this.gender = gender;
  this.interests = interests;
};
```

```js
// The methods are all defined on the constructor's prototype. For example:
Person.prototype.greeting = function() {
  alert('Hi! I\'m ' + this.name.first + '.');
};
```

```js
// Say we wanted to create a Teacher class, like the one we described in
// our initial object-oriented definition, which inherits all the members
// from Person, but also includes:
// 1. A new property, subject — this will contain the subject the teacher teaches.
// 2. An updated greeting() method, which sounds a bit more formal than the
// standard greeting() method — more suitable for a teacher addressing some
// students at school.

function Teacher(first, last, age, gender, interests, subject) {
  Person.call(this, first, last, age, gender, interests);
  this.subject = subject;
}
// This function basically allows you to call a function defined somewhere else,
// but in the current context. The first parameter specifies the value of this
// that you want to use when running the function, and the other parameters are
// those that should be passed to the function when it is invoked.
```

### Setting Teacher\(\)'s prototype and constructor reference

```js
// We need to get Teacher() to inherit the methods defined on
// Person()'s prototype. So how do we do that?

Teacher.prototype = Object.create(Person.prototype);

// Here our friend create() comes to the rescue again. In this case we
// are using it to create a new object and make it the value of Teacher.prototype.

// We need to do one more thing before we move on. After adding the last line,
// Teacher.prototype's constructor property is now equal to Person(),
// because we just set Teacher.prototype to reference an object that
// inherits its properties.

Teacher.prototype.constructor = Teacher;
```

```js
// To finish off our code, we need to define a new greeting() function on
// the Teacher() constructor.

// The easiest way to do this is to define it on Teacher()'s prototype

Teacher.prototype.greeting = function() {
  var prefix;

  if (this.gender === 'male' || this.gender === 'Male' || this.gender === 'm' || this.gender === 'M') {
    prefix = 'Mr.';
  } else if (this.gender === 'female' || this.gender === 'Female' || this.gender === 'f' || this.gender === 'F') {
    prefix = 'Mrs.';
  } else {
    prefix = 'Mx.';
  }

  alert('Hello. My name is ' + prefix + ' ' + this.name.last + ', and I teach ' + this.subject + '.');
};
```

```js
// Try creating an object instance from Teacher() by putting the following
// at the bottom of your JavaScript.

var teacher1 = new Teacher('Dave', 'Griffiths', 31, 'male', ['football', 'cookery'], 'mathematics');
```

[Recommended read of OOP in JavaScript](http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/)

