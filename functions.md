#js/basics
There are multiple ways you can create functions:

# 1. function name( ){ }
This is the most common way of creating them. a typical format is like this:
```javascript
function login(user, pass){
	if (user=="h3sam" && pass=="secsece") {
		//some random stuff
		return true;
		}
	else {
		console.log("incorrect combo of user and pass");
		return false;
	}
}

let func = login;    // Copies the function into another variable
alert (login);       // This just prints out how the function works

// In order for the function to work, you need to put parentheses in front of it

func("wut", "duheeeeeelll"); // false + console log
login("h3sam", "secsece"); // true

```
- [*] if the function is declared without any kind of name assigned to it, then you can run it from any place of the code, with no problem. However if you pass it as a function expression (`let sayHi = function(name)`) then it should be referenced after the expression only.
---
# 2. Arrow functions
```javascript
let summer = (arg1, arg2, ...) => arg1+arg2+...;
let multiplier = (n1, n2, ...) => {
	result = n1*n2*...;
	return result
}
```
- This type of function is really good combined with the ? : if pair.
```javascript
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  () => alert('Hello!') :
  () => alert("Greetings!");

welcome();
```
- [*] arrow functions don't have a this variable, so they reference from outside the function.
---
# 3. new Functions
The point of this function is that it is very dynamic, and you pass both the inputs and script as strings to the args of the `Function()`. This is useful when you don't know what is the script of the function going to be.
- [*] if a value gets defined in a separate block of code (e.g. in a function), the new Function can't access it because it is global.
