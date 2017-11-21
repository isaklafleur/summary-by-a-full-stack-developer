# Node.js

---

Node.js® is a JavaScript runtime built on [Chrome's V8 JavaScript engine](https://developers.google.com/v8/). Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js' package ecosystem, [npm](https://www.npmjs.com/), is the largest ecosystem of open source libraries in the world.

## Installation

1. Go to [nodejs](https://nodejs.org/en/) and download and install the LTS version.
2. After installation, make sure you can run both `npm -v` and `node -v` command in your terminal.

## Use Node

1. Create a file hello.js
2. Add a console.log\("Hello World"\) and save it.
3. In the terminal in the folder where the file is located, run: `node hello.js`
4. If you can see "Hello World" printed out in the terminal, node is working.
5. FYI... Node is always running in the background when you start your computer.

---

# npm \(node package manager\)

### What is [npm](https://www.npmjs.com/)?

npm is the package manager for JavaScript and the world’s largest software registry. Discover packages of reusable code — and assemble them in powerful new ways.

Use npm to install, share, and distribute code; manage dependencies in your projects; and share & receive feedback with others.

If you have any problems using npm, their [documentation](https://docs.npmjs.com/) is very good. Start there!

## Use npm

1. Create a new folder
2. run `npm init` inside the folder. This will ask you a bunch of questions, and then write a package.json for you. Just answer yes on all of them for this project.
3. run `npm install --save beer-names` to install the npm package called beer-names. Using the flag --save will save also the npm package into your package.json file.
4. Create a new file `beerName.js` and add the below code
5. Run the script with: `node beerName.js` and a random beer name should be printed out in the console. :-\)

```js
var beer = require('beer-names')

beer.random();
//=> 'Retro Knight Imperial Stout'
```



