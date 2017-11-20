# JavaScript Iteration Methods

---

Several methods take as arguments functions to be called back while processing the array. When these methods are called, the `length`of the array is sampled, and any element added beyond this length from within the callback is not visited. Other changes to the array \(setting the value of or deleting an element\) may affect the results of the operation if the method visits the changed element afterwards. While the specific behavior of these methods in such cases is well-defined, you should not rely upon it so as not to confuse others who might read your code. If you must mutate the array, copy into a new array instead.

| Iteration method | Description |
| :--- | :--- |
| [Array.prototype.filter\(\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) | Creates a new array with all of the elements of this array for which the provided filtering function returns true. |
| [Array.prototype.forEach\(\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) | Calls a function for each element in the array. |
| [Array.prototype.map\(\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) | Creates a new array with the results of calling a provided function on every element in this array. |
| [Array.prototype.reduce\(\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) | Apply a function against an accumulator and each value of the array \(from left-to-right\) as to reduce it to a single value. |
|  |  |
|  |  |
|  |  |



