/*
https://medium.com/free-code-camp/when-to-use-a-function-declarations-vs-a-function-expression-70f15152a0a0

We write function in 2 ways.

function fn_name() {}

() => {}

Ist difference: a name
-----------------------
We create the function with name for function declartion: function fn_name() {}

The name may be omitted in function expression, making that function as ananymous: const var_name = function() {}

The ananmyous function in ES6: const var_name = () => {}

II nd difference: hoisting
--------------------------
Functions declaraitons are hoisted but function expression are not.

For Ex:
--------

doStuff();
function doStuff() {} - This works

doStuff();
const var_name = () => {} - This throws error

Hoisting:
---------
Hoisting refers to the availability of functions and variables at the top of your code, after they are created.
Objects are initialized at compile time and available anywhere in your file.

When and where we needed functional declaraton and functional expression:
--------------------------------------------------------------------------

Function expressions are invoked to avoid polluting global scope.

By using function declaration program being aware of many different functions. But in Functon expression is ananmyous, they are used and forgotten immediately.

IIFE: Immediate invoke function expression
-------------------------------------------
When a function is created at the same time it is called.

(function() {}) ()

(() => {}) ()

Callbacks: A function passed to another function
-------------------------------------------------

function map_fn() {}
array.map(map_fn)

Here the problem is map_fn function declaraton is available throughout the application when there is no need for that. But that callback is funciton expression, it will not be available outside of the function that uses it.

array.map(item => {//do the stuff here})

or

const var_name = function(item) {}

array.map(var_name); // though var_name will be available only to code below its initialization.

Summary:
---------

Function declaration - when you want to create a function on the global scope and make it available throughout your code

Function expression - to limit where the function is available, keep your global scope light, and maintain clean syntax.

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function
https://developer.mozilla.org/en-US/docs/Glossary/Hoisting
