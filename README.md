# what-i-learned-week-6

## Ternary - The ?

The conditional (ternary) operator is the only JavaScript operator that takes three operands: a condition followed by a question mark ( ? ), then an expression to execute if the condition is truthy followed by a colon ( : ), and finally the expression to execute if the condition is falsy.

When you want to execute a block of code if a particular test evaluates to true, you often use the if-else statement. For example, if age is greater than 16, then allow the person to drive can be coded as follows:

````javascript
let age = 19;
let canDrive;
if (age > 16) {
    canDrive = 'yes'
} else {
    canDrive = 'no';
}
````
In this example, you can use the ternary operator as the shortcut for the if-else statement as follows:

````javascript
let age = 19;
let canDrive = age > 16 ? 'yes' : 'no';
````

In general, the syntax of the ternary operator is as follows:

````javascript
condition ? expression_1 : expression_2;
````
----------

## .require()

require function is the easiest way to include modules that exist in separate files. The basic functionality of require is that it reads a JavaScript file, executes the file, and then proceeds to return the exports object. An example module:

````javascript
console.log("evaluating example.js");

let invisible = function () {
  console.log("invisible");
}

exports.message = "hi";

exports.say = function () {
  console.log(exports.message);
}
````
So if you run let example = require('./example.js'), then example.js will get evaluated and then example be an object equal to:

````javascript
{
  message: "hi",
  say: [Function]
}
````

If you want to set the exports object to a function or a new object, you have to use the module.exports object. So for an example:

````javascript
module.exports = function () {
  console.log("hello world")
}

require('./example2.js')() //require itself and run the exports object
````