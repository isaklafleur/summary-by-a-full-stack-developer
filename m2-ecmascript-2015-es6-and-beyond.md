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
	console.log( a );	// undefined
	console.log( b );	// ReferenceError!

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



