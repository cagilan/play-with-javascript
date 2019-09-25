https://medium.com/@bolajiayodeji/the-differences-between-object-freeze-vs-const-in-javascript-4eacea534d7c

ES6 has brought several features to JS

    1. Object.freeze ()
    2. const

Object.freeze() and const work differently.

Overview:
----------

* const behaves like let. The difference is, its defines a variable that cant be reassigned. 
Variables declared by const are block scoped and not function scoped like variables declared by var.

* Object.freeze() takes an object as an argument and returns the same object as an immutable object. It means no properties of the object can be added, removed or changed. 

Mutable objects have properties that can be changed. Immutable objects have no properties that can be changed after the object is created. 

const user = 'test'

user = 'test1'

This would throw an Uncaught TypeError because we are trying to reassign the variable user.

This would work for var or let but not for const.

The problem with const:
_________________________

Const prevents reassignnment but its mutuable.

Object.freeze:
--------------------

To disable any changes to the object we need Object.freeze()

Object with nested properties are not actually frozen. 

const user = {
    first_name: 'chan'
    contact: {
        last_name: 'chan123'
    }
}

Object.freeze(user);

user.first_name = 'chan2' // immutable 

user.contact.last_name = 'chan2' //mutuable







