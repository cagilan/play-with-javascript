https://medium.com/@aravishack/es6-features-a-walk-through-1ffd8eb82f6

ES6 features:
--------------

1. Template literals: (Backticks (`) and expressions(${}))
------------------------------------------------------------

In ES5:

var name = 'Hello';
var message = 'Hey' + name + ',';

In ES6:

let name = 'Hello';
let message = `Hey ${name},`;

Benefit expand multi lines.

2. Let and Const: 
-------------------

In ES5:

var keyword used - the scope is entire enclosing function.

function x() {
    for() {
        var x = 1;
    }
    console.log(x); // x scope available for entire enclosing function
}

Note: Var keyword use at top level outside function, it creates the property on the global object. 

In ES6:

Let and Const - Block scope not function

Note: It dont create property on global object if use at top level

3. Arrow Function:
-------------------

ES5:

const add = function(num)  {
    return num + num;
}

With Arrow function, we get rid of function keyword and put fat arrow (=>)

const add = (num) => {
    return num + num;
}

* If our function is one-linear and returns a value, we can drop the return keyword as well as curly braces

const add = (num) => num + num;

* If includes only single parameter, drop parenthesis

const add = num => num + num;

* If no parameter

const add = () => {}

Note:

Arrow function is useful when pass callback function as arguments.


ES5: 

var activeJobs = fruitsArray.filter(function(fruit)) {
    return fruit;
}

ES6:

const activeJobs = fruitsArray.filter(fruit => fruit)

* Arrow function, dont rebind this.

ES5:

function onSubmit() {
    var that = this; // Keep a reference to 'this'    

    orderService() {
        //In JS every function defines its own 'this' value. 'This' in this inner function different then 'this'
        in onSubmit function

    }
}

ES6:

Arrow function use the this value of enclosing execution context. It dont redefine 'this'.

function onSubmit() {
    orderService.store(order, result => {

    }); 
}

Destructuring:
--------------

It an expression that allows us to extract properties from object or array.

ES5:

var address = {
    name: '',
    age: ''
}

var name = address.name;

ES6:

const { name, age } = address;

Destructuring Array:

var values = ['one', 'Two']

ES5:

var value1 = values[0]

ES6:

const [value1] = values;

Default parameter:
--------------------

If any of function parameter dont have value we will check whether undefined and assign some value.

ES5:

typeof year !== 'undefined' ? '2018': ''

ES6:

function getuser(name, y = 2018)

Import and Export:
-------------------

* Export allows you to export module to be used in another JS component. Import that module
to use in our component.

* Use 'Default' export a single value or to have callback value for our module

Ex:

MyClass.JS

class MyClass{
    constructor() {

    }
}
export default MyClass;

// Main.JS

import MyClass from 'MyClass'

Note: In case of named export:

//lib.JS

export const sqrt = Math.sqrt;
export function square(x) {
    return x * x;
}
export function diag() {

}

//main.JS

import {square, diag} from 'lib';

// you can call with '*' but prefix the module name with export

import * as lib from 'lib';

Promises:
-----------

New features of ES6.

1. Method to write asynchronous code
2. Fetch date from the API
3. when function takes time to executed

let p = new Promise(function(resolve, reject)) {
    if() {
        resolve() // successful
    }else {
        reject() //error
    }
}

2 parameters resolve and reject. 

.then() handler 

const url = 'xxx'

const getData = (url) => {
    return fetch(url)
}

getData(url).then(data => data.json())


Rest paramter and speard operator:
-----------------------------------

* spread operator speard the elements of array into individual values.

function getSum(x, y) {
    return x+y;
}

let sumArray = [10,20,30];
getSum(...sumArray);

We have three dots (...) in front of array, so its spread the elements of array into individual values. 

* it allow array to spit single argument and passed to funciton as separate argument. 

Ex: Concate 2 arrays

var a = [1, 2]
var b = [2, 3]

var c = [...a,...b]

output: [1,2,3,4]

Rest Operator:
---------------

Rest operator will take care of rest of parameters. 

function numbers(x, y, ...z) {
    console.log(x, y, z)
}
numbers(1, 2, 3, 4, 5, 6)

Ouput: 1 2 [3,4,5,6]

As you see x and y have been assigned the value 1,2 respectively whereas the rest of parameters got assigned to z. 

Rest parameter are indicated by 3 dots.

Classes:
---------

Core concept in OOPS.

It makes our code secure and encapsulate.

class myClass{
    constructor(name, age) {
        this.name = name;
    }
}

const Home = new myClass('chan', 20)