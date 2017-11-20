# [JavaScript Object Oriented Programming \(OOP\)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)

---

Object Oriented Programming \(OOP\) refers to using self-contained pieces of code to develop applications. We call these self-contained pieces of code **objects**, better known as _Classes _in most OOP programming languages and _Functions _in JavaScript. We use objects as building blocks for our applications. Building applications with objects allows us to adopt some valuable techniques, namely, **Inheritance **\(objects can inherit features from other objects\), **Polymorphism **\(objects can share the same interface—how they are accessed and used—while their underlying implementation of the interface may differ\), and **Encapsulation **\(each object is responsible for specific tasks\).

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

The constructor function is JavaScript's version of a class. You'll notice that it has all the features you'd expect in a function, although it doesn't return anything or explicitly create an object — it basically just defines properties and methods. You'll see the

`this` keyword being used here as well — it is basically saying that whenever one of these object instances is created, the object's `name` property will be equal to the name value passed to the constructor call, and the `greeting()` method will use the name value passed to the constructor call too.

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

[Recommended read of OOP in JavaScript](http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/)

