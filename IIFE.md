#https://medium.com/javascript-in-plain-english/https-medium-com-javascript-in-plain-english-stop-feeling-iffy-about-using-an-iife-7b0292aba174

Immediately Invoked Function Expression is a good way at protecting the scope of your function and the variables within it

Ex:

function addTogether() {
 var x = 20;
 var y = 20;
 var answer = x + y;
 console.log(answer);
 }

addTogether();

we simply want to call a function in order to get an output, but that’s it — we’ll never want to use it again and don’t want our program to ever be able to accidentally access it.

our variables are safe — safe insofar that they are immutable (which is just a fancy, technical term for saying that they cannot be changed in the future).

our variables cannot be accessed, but how do we make it so that our function also cannot be accessed.

That’s where IIFE’s come in.
------------------------------

So the first thing we do is wrap our entire addTogether function in brackets, like so:
(function addTogether() {
 var x = 20;
 var y = 20;
 var answer = x + y;
 console.log(answer);
 }) ();

  we need a way to be able to call this function, but how do we do that now given that we don’t have a name to refer to? Well, we simply add a pair of brackets at the end of the function (but just before the semi-colon), like so:

  An Immediately Invoked Function Expression is a good way at protecting the scope of your function and the variables within it.