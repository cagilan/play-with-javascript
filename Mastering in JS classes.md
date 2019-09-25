https://itnext.io/javascript-fundamentals-mastering-classes-38e7668023be

JS classes introduced in ES5. Described as existing structure of prototype inheritance.

Classes are like Functions:
----------------------------

Classes as like function having 2 components.

1. Class declaration
2. Class expression

Class Declaration:
-------------------

class car {
    constructor() {

    }
}

Hoisting:
----------

D/F: Function declaration are hoisted but class declaration not. 

You first need to declare your class and then access it otherwise referencerror.

const p = new Image() // referencerror

class Image(){}

Class expression:
------------------

Class expression is other way to define the class. It can be named or unnamed. 

// unnamed class expression

let Image = class {
    constructor(name) {
        this.name = name;
    }
}

console.log(Image.name)

// Named class expression

let Image = class myImage {
    constructor(name) {
        this.name = name;
    }
}

console.log(Image.name)

Constructors:
______________

The constructor method is used to create and initialize an object created with a class.

We can use only one method with the name constructor within a class.

Our constructor can use the super keyword to call the constructor of the super class.

Instance properties:
-----------------------

Instance properties must be defined inside of our class method.

class Image {
    constructor(name) {
        this.name = name;
    }
}

If we wish to use static class-side properties and prototype data properties, these must be defined outside of
the classes body declaration.

Image.staticWidth = 50;

Field Declaration:
--------------------

Babel which will transpile the syntax for you.. Many browsers not yet adopted.

Public:
--------

The difference is our fields have been declared upfront.

class Image {
    height = 0;
    width;
    constructor(height, width) {
        this.height = height;
        this.width = width;
    }
}

Private:
--------

class Image {
    #height = 0;
    #width;
    constructor(height, width) {
        this.#height = height;
        this.#width = width;
    }
}

Private fields declared with (#) cant be referenced outside of the class only within
class body.

Child classes using extends:
------------------------------

We use extends keyword with either class declaration or expression to create class as child or another class.

class Vehicle {
    constructor(name) {
        this.name = name;
    }

    sound() {

    }
}

class Car extends Vehicle {
    constructor(name) {
        super(name); // call the super class constructor and pass in the name parameter
    }

    sound() {

    }
}

let c = new Car('Benz')
c.sound()

