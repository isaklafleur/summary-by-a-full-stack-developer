# Asynchronous Code & Callbacks

---

## What are callbacks?

Callbacks are just the name of a convention for using JavaScript functions. There isn't a special thing called a 'callback' in the JavaScript language, it's just a convention. Instead of immediately returning some result like most functions, functions that use callbacks take some time to produce a result. The word 'asynchronous', aka 'async' just means 'takes some time' or 'happens in the future, not right now'. Usually callbacks are only used when doing I/O, e.g. downloading things, reading files, talking to databases, etc.

When you call a normal function you can use its return value:

```js
var result = multiplyTwoNumbers(5, 10)
console.log(result)
// 50 gets printed out
```

However, functions that are async and use callbacks don't return anything right away.

```js
var photo = downloadPhoto('http://coolcats.com/cat.gif')
// photo is 'undefined'!
```

In this case the gif might take a very long time to download, and you don't want your program to pause \(aka 'block'\) while waiting for the download to finish.

Instead, you store the code that should run after the download is complete in a function. This is the callback! You give it to the `downloadPhoto` function and it will run your callback \(e.g. 'call you back later'\) when the download is complete, and pass in the photo \(or an error if something went wrong\).

```js
downloadPhoto('http://coolcats.com/cat.gif', handlePhoto)

function handlePhoto (error, photo) {
  if (error) console.error('Download error!', error)
  else console.log('Download finished', photo)
}

console.log('Download started')
```

The biggest hurdle people have when trying to understand callbacks is understanding the order that things execute as a program runs. In this example three major things happen. First the `handlePhoto` function is declared, then the `downloadPhoto` function is invoked and passed the `handlePhoto` as its callback, and finally `'Download started'` is printed out.

Note that the `handlePhoto` is not invoked yet, it is just created and passed as a callback into `downloadPhoto`. But it won't run until `downloadPhoto` finishes doing its task, which could take a long time depending on how fast the Internet connection is.

This example is meant to illustrate two important concepts:

* The `handlePhoto` callback is just a way to store some things to do at a later time

* The order in which things happen does not read top-to-bottom, it jumps around based on when things complete

## [setTimeout\(\)](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) method

The setTimeout\(\) method calls a function or evaluates an expression after a specified number of milliseconds.

**Tip: **1000 ms = 1 second.

**Tip: **The function is only executed once. If you need to repeat execution, use the [setInterval\(\)](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) method.

**Tip: **Use the [clearTimeout\(\)](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout) method to prevent the function from running.

```js
// Display an alert box after 3 seconds (3000 milliseconds)
setTimeout(function(){ alert("Hello"); }, 3000);
```

## [setInterval\(\)](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) method

The setInterval\(\) method calls a function or evaluates an expression at specified intervals \(in milliseconds\).

The setInterval\(\) method will continue calling the function until [clearInterval\(\)](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval) is called, or the window is closed.

The ID value returned by setInterval\(\) is used as the parameter for the clearInterval\(\) method.

**Tip: **1000 ms = 1 second.

**Tip: **To execute a function only once, after a specified number of milliseconds, use the [setTimeout\(\)](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) method.

```js
// Alert "Hello" every 3 seconds (3000 milliseconds):
setInterval(function(){ alert("Hello"); }, 3000);
```

```js
// Example using both methods setInterval and clearInterval.

// Display the current time (the setInterval() method will execute the
// function once every 1 second, just like a digital watch).
// Use clearInterval() to stop the timer.

// The clearInterval() method clears a timer set with the setInterval() method.
// The ID value returned by setInterval() is used as the parameter for the
// clearInterval() method.

var myVar = setInterval(function(){ myTimer() }, 1000);

function myTimer() {
    var d = new Date();
    var t = d.toLocaleTimeString();
    document.getElementById("demo").innerHTML = t;
}

function myStopFunction() {
    clearInterval(myVar);
}
```



