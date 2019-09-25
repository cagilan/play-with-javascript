https://medium.com/better-programming/is-javascript-synchronous-or-asynchronous-what-the-hell-is-a-promise-7aa9dd8f3bfb

Javascript is synchronous, blocking, single threaded laungage which means one operation can be progress at a time. 

But its possible to manipulate JS to behave in asynchronous way.

Asynchronous callback:
----------------------

The simplest solution for synchronous is use asynchronous callbacks (seTimeout())

For Ex: DB request

Asynchronous callback allow you to invoke callback function which sends a DB request, wait for the response and freeing up the rest of your code to continue running.

Once DB request complets, the results are sent to the queue and then processed.

Promise coming into the picture:

Since you cant predict when function will resolve, you have to nest all dependent functions within it. It was this environment that inspired the promise. 

Note: Asynchronous functions runs in parallel so you cant predict which order they will be sent queue in. 

.next() allows us to control the order of operations with async.

Promise:
---------

Instead of bundling all dependencies into one block code we are able to separate. 

.then() hold all other dependicies aside, running them only once function returns and runs. 

This allows code in more modular, readable and gaining the benefits of A.programming.

Async/Await:








