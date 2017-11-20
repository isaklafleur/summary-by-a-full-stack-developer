# JavaScript Operators

---

## [this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

The \`this\` keyword behaves differently in JavaScript compared to other language. In Object Oriented languages, the \`this\` keyword refers to the current instance of the class. In JavaScript the value of \`this\` is determined mostly by the invocation context of function \(\*\`context.function\(\)\`\*\) and where it is called.

* In JavaScript, the thing called **this**, is the object that "owns" the JavaScript code.
* The value of **this**, when used in a function, is the object that "owns" the function.
* The value of **this**, when used in an object, is the object itself.
* The **this **keyword in an object constructor does not have a value. It is only a substitute for the new object.
* The value of **this **will become the new object when the constructor is used to create an object.

###### Note that **this **is not a variable. It is a keyword. You cannot change the value of **this**.

### **1. When used in global context**

When you use \`this\` in global context, it is bound to global object \(\`window\` in browser\)

```js
document.write(this);  //[object Window]
```

When you use \`this\` inside a function defined in the global context, \`this\` is still bound to global object since the function is actually made a method of global context.

### **2. When used inside object method**

When you use \`this\` keyword inside an object method, \`this\` is bound to the "immediate" enclosing object.

```js
var obj = {
    name: "obj",
    f: function () {
        return this + ":" + this.name;
    }
};
document.write(obj.f());  //[object Object]:obj
```

Above we have put the word immediate in double quotes. It is to make the point that if you nest the object inside another object, then \`this\` is bound to the immediate parent.

```js
var obj = {
    name: "obj1",
    nestedobj: {
        name:"nestedobj",
        f: function () {
            return this + ":" + this.name;
        }
    }            
}

document.write(obj.nestedobj.f()); //[object Object]:nestedobj
```

Even if you add function explicitly to the object as a method, it still follows above rules, that is \`this\` still points to the immediate parent object.

```js
var obj1 = {
    name: "obj1",
}

function returnName() {
    return this + ":" + this.name;
}

obj1.f = returnName; //add method to object
document.write(obj1.f()); //[object Object]:obj1
```

### **3. When invoking context-less function**

When you use \`this\` inside function that is invoked without any context \(i.e. not on any object\), it is bound to the global object \(\`window\` in browser\) \(even if the function is defined inside the object\) .

```js
var context = "global";

var obj = {  
    context: "object",
    method: function () {                  
        function f() {
            var context = "function";
            return this + ":" +this.context; 
        };
        return f(); //invoked without context
    }
};

document.write(obj.method()); //[object Window]:global
```

**Trying it all with functions**

We can try above points with functions too. However there are some differences.

* Above we added members to objects using object literal notation. We can add members to functions by using \`this\`. to specify them.
* Object literal notation creates an instance of object which we can use immediately. With function we may need to first create its instance using \`new\` operator.
* Also in an object literal approach, we can explicitly add members to already defined object using dot operator. This gets added to the specific instance only. However we have added variable to the function prototype so that it gets reflected in all instances of the function.



