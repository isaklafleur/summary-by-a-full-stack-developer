# Async & Callbacks

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

Instead, you store the code that should run after the download is complete in a function. This is the callback! You give it to the`downloadPhoto`function and it will run your callback \(e.g. 'call you back later'\) when the download is complete, and pass in the photo \(or an error if something went wrong\).

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



