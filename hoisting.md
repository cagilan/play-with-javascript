#https://medium.com/javascript-in-plain-english/https-medium-com-javascript-in-plain-english-what-is-hoisting-in-javascript-a63c1b2267a1

When Javascript compiles all of your code, all variable declarations using var are hoisted/lifted to the top of their functional/local scope (if declared inside a function) or to the top of their global scope (if declared outside of a function) regardless of where the actual declaration has been made. This is what we mean by “hoisting”.

Functions declarations are also hoisted, but these go to the very top, so will sit above all of the variable declarations.

The key thing to note is that the only thing that gets moved to the top is the variable declarations , not the actual value given to the variable

For Ex:
------------

console.log(myName);
var myName = ‘Sunil’;

The answer is undefined. 

Just to clarify what we mean, if we had a chunk of code and let’s say that on Line 10, we had var myName = 'Sunil', when the Javascript gets compiled, var myName would get moved to the top of its scope, whilst myName = 'Sunil' would stay on Line 10 (or possibly now Line 11 if var myName were hoisted up onto Line 1).

Hoisting in function declaration:
----------------------------------

function hey() {
console.log('hey ' + myName);
};
hey();
var myName = 'Sunil';

Compiling:
___________

function hey() {
console.log('hey ' + myName);
};
var myName;
hey();
myName = 'Sunil';

Hoisting for Lets and Const:
-----------------------------

var, let, const, function and class declarations are hoisted.

The difference between var, let and const declarations is their initialisation — in plain terms this simply means the value they are given to begin with.

var and let can be initialised without a value (and if you try to call it, it will return undefined) while const will throw a Reference error if you try to declare one without assigning it a value at the same time. So const myName = 'Sunil' would work, but const myName; myName = 'Sunil'; would not.

Declarations made with var can be accessed from outside of their initial scope, whereas declarations made with let and const are not.
As we can see in the below example, declarations made with var return undefined whereas those made with let and const return errors (credit to gvlachos for raising and writing the following):

console.log(‘1a’, myName1); // undefined
if (1) {
 console.log(‘1b’, myName1); // undefined
 var myName1 = ‘Sunil’;
}

console.log('2a', myName2); // error: myName2 is not defined
if (1) {
    console.log('2b', myName2); // undefined
    let myName2 = 'Sunil';
}

console.log('3a', myName3); // error: myName3 is not defined
if (1) {
    console.log('3b', myName3); // undefined
    const myName3 = 'Sunil';
}
