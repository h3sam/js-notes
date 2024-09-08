#js/basics [js.info 1](https://javascript.info/array) [js.info 2](https://javascript.info/array-methods)

- [*]  You can loop through the items of an array by using **`let item in array`** in the for loop (it is pretty modern though). You can also loop as usual with array.length, which is the fastest as well.
- [*] when you create an array, the name is just a reference to the array itself; so if you update an array by any means, it will change for all the other references.
- You can have functions as items of an array, since they are in essence an object.
```js
let fruits = ["Apples", "Pear", "Orange"];

let shoppingCart = fruits;

shoppingCart.push("Banana");

alert( fruits.length ); // 4
```
# Methods for Arrays
- [*] In general for array methods, you can use negative indexes in here.

## Adding & Deleting items
 - `arr.push(...items)` adds items to the end
 - `arr.pop()` extracts an item from the end
 - `arr.shift()` extracts an item from the beginning
 - `arr.unshift(...items)` adds items to the beginning
 - `splice(start[, deleteCount, elem1, ..., elemN])`
	pretty self explanatory. The difference with deleting an element is that deleting a value in a key keeps it empty, but splice reorders the thing.
	- [*] You can also insert elements without getting rid of anything with `deleteCount` being set to zero
- `slice([start], [end])`
	You can use this to get a specific part of an array.
- `concat(args*)`
	This can be used to join multiple arrays and values with the original array.
	- [*] If an object has the property `Symbol.isConcatSpreadable` set to true, then it recognizes the object as an array, and will print the values that have the keys like an array (e.g. 0,1,2,...)

- `forEach(function(item, index, array) { //stuff }`
	- Used for iterating over elements in an array. pretty much works like `let item in array`.
	- The return value of the function is not used anywhere.
## Finding items 
- `arr.indexOf(item, from)` 
	- looks for `item` starting from index `from`, and returns the index where it was found, otherwise `-1`.
- `arr.includes(item, from)`
	- looks for `item` starting from index `from`, returns `true` if found.
- **`let result = arr.find(function(item, index, array) {}`**
	- if true is returned, item is returned and iteration is stopped for falsy scenario returns undefined.
	- item is each item in the array, index is where it starts from, and array is the array itself.
	- **`findIndex`, `findLastIndex` & `filter`** have the exact same syntax, but each return different values:
		- `findIndex` and `findLastIndex` return **the index of the found item.**
		- `filter` returns **an array of matching items.**
## Transforming items
- `map(function(item, index, array) { //stuff })`
	- returns an array of returned results from the function.
	- THIS is the most used function for arrays.
- `sort(function)`
	- sorts the items of an array.
	- [!] the default function for this method will take items as arrays. it also sorts items descending.
	- [*] The use of the function is as follows:
		- if the returned value of the function is greater than zero, then it is "greater", thus moving towards the start of the array
		- if it is negative however, the reverse is applied.
	```javascript
	function compareNumeric(a, b) {
	  if (a > b) return 1;
	  if (a == b) return 0;
	  if (a < b) return -1;
	}
	
	let arr = [ 1, 2, 15 ];
	
	arr.sort(compareNumeric);
	
	alert(arr);  // 1, 2, 15
	
	// a shorter function would be something like this
	// this is the best way to sort numbers in an array
	arr.sort(function(a, b) { return a - b; });
	
	// for comparing strings in other langs, we can use this
	countries.sort( (a, b) => a.localeCompare(b) )
	```
- `reverse`
	- reverses the order of the array, just that.
- `split` and `join`
	- used for making arrays from and into strings, with a specified delimiter.
- `reduce`
	- I don't have the ass to go through this =)




