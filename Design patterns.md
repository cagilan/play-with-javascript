https://medium.com/better-programming/javascript-design-patterns-25f0faaaa15

Design patterns - Write better, maintainable JS code.

DP - reusable solution to commonly occuring problem in software.

Its an approach to solve the problem.

3 categories:

1. Creational - Object creational mechanisms. Constructor, Factory, Protype, Singleton
2. Structural - Class & Object composition. Help to restructure without affecting the entire system. Adapter, Composite, Decorator, Fascade, Flyweight, Proxy
3. Behavior - Improving communication between dissimilar objects. Command, Iterator, Mediator, Observer, State, Strategy, Template, Chain of Responsibility

Prototype Pattern:
-------------------

This pattern is object-based creational DP. It used prototypal inheritance instead of object oriented inheritance.

In this example, we have a car object that we use as prototype to create another object myCar with Javascript Object.create feature.

const car = {
    noOfWheels: 4,
    start() {
        return 'started'
    }
    stop() {
        return 'stop'
    }
}

//Object.create()

const myCar = Object.create(car, {owner: {value: 'John'}})

console.log(myCar.__proto__ === car)

Singleton Pattern:
-------------------

Object creational pattern in which only one instance of a class can exist. 

If no instance of the singleton class exists then new instance is created and returned, but if instance alredy exists, then the reference to the existing instance is returned.

In this ex, we have database class that is singleton. 

First we create object mongo by using new operator to invoe the DB class constructor. This time an object is instantiated because none already exists. 

Second time, when we create the mysql object, no new object is instantiated but instead, the reference to the object that was instantiated earlier. 


class DB {
    constructor(data) {
        if(DB.exists) {
            retrun DB.instance;
        }
        this._data = data;
        DB.instance = this;
        DB.exists = true;
        return this;
    }

    getData() {
        return this._data;
    }

    setData() {
        this._data = data;
    }
}

//usage 

const mongo = new DB('mongo');
console.log(mongo.getData()); // mongo

const mysql = new DB('mysql);
console.log(mysql.getData()); //mongo

Facade pattern:
-----------------

Structural design pattern. It provides simpler, public facing interface for ease of use that shields away from the complexities of systems.

Most common pattern in libraries like JQuery.

All the complexities are hidden away using the facade pattern. 

Ex: we create a public facing API with the class ComplaintRegistry. It exposes only one method to be used by the client. 

i'e registerComplaint. It internally handles either ProductComplaint or ServiceComplaint. It handles other complexes functionalities. 

class ComplaintRegistry {
    registerComplaint() {

    }
}

class Complaints {

}

class SeriveComplaint extends Complaints {

}

class ProductComplaint extends Complaints {

}

const registry = new ComplaintRegistry();

const reportService = registry.registerComplaint('Martha', 'service', '')

const reportProduct = registry.registerComplaint('Jane', 'product', '')