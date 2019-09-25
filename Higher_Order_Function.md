#https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad

What makes JavaScript suitable for functional programming is that it accepts Higher-Order Functions.

To fully understand this concept, you first have to understand what Functional Programming is and the concept of First-Class Functions.

Functional Program:
_____________________

Functional Programming is a form of programming in which you can pass functions as parameters to other functions and also return them as values. In functional programming, we think and code in terms of functions.
JavaScript, Haskell, Clojure, Scala, and Erlang are some of the languages that implement functional programming.

First-Class Functions
-----------------------

JavaScript or any other functional programming languages functions are objects.

 JavaScript functions are a special type of objects. They are Function objects. 
 
For example:
-------------

function greeting() {
  console.log('Hello World');
}

// Invoking the function
greeting();  // prints 'Hello World'

To prove functions are objects in JavaScript, we could do something like this:

// We can add properties to functions like we do with objects

greeting.lang = 'English';

// Prints 'English'
console.log(greeting.lang);

High order function:
_____________________

High order function is one which either takes a function as an argument or returns a function.

If a functin doesnot, it is a first order function.

