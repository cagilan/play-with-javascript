Angular is framework for building client application in HTML.
Typescript that compiles to Javascript

Why Angular:

1. develop across all platform
2. speed and performance
3. incredible tooling
5. testing modular. do unit testing for separate modules
6. community development - support from google

Modules:
------------

Angular apps are modular. angular app has atleast one ngModule class called root module or appMoule
Application consists of multiple modules.

Its building block to build the application.

Its JS class. ngModule is a decrotor function.

decrotor how the class behaves and works. 4 key components.

Declarations: view classes
----------------

components / directives / pipes

exports:
----------

imports:
------------

provider: service function. (accessible all parts of app)
-----------

bootstrap:
------------

main application view called the root component.


Example:

-------------

import {NgModule} from '@angular/core';
import {BrowserModule} from '@angular/platform-browser';

@NgModule({
    imports: [BrowserModule],
    providers: [Logger],
    declarations: [AppComponent],
    exports: [AppComponent],
    bootstrap: [AppComponent]
})

export class AppModule {}

Angular libraries: starts with @
--------------------

Components: patch  of screens or block of views. 
------------

Ex:
------

export class FruitListComponent implements OnInit {
    Fruits: Fruit[];
    selectedFruit: Fruit;

    constructor(private service: FruitService) {

    }

    ngOnInit() {
        this.Fruits = this.servie.getFruits();
    }

    selectedFruit(fruit: fruit) {
        this.selectedFruit = fruit;
    }    
}

Template:
__________

HTML template that angular to tells how to render the component. 

Ex:

<h2>xxx</h2>
<li *ngFor="let fruit of fruits" (click)="selectFruit(fruit)"></li>

<app-fruit-detail *ngIf="selectFruit"></app-fruit-detail>

Metadata:  Tells angular how to process a class.
------------ 

@component({
    selector: 'app-fruit-list',
    templateUrl: './Fruit-list.component.html',
    providers: [FruitService]
})

export class FruitListComponent implements OnInit {
    /* .... */
}

Data Binding:
---------------

two way binding. 

4 forms of data binding. 

data bining to the DOM, from the DOM or in both 

{{value}} // display the value in view interpolation

[property] = 'value' // get the value property binding

(event) = 'handler'  // event binding 

[(ng-model)] = 'property' // click direct store the value 

Directive:
-------------
Angular templates are dynamic. When agular renders them, it transforms the DOM.

Directive is a class with @Directive decrotor, @Component decrotor

Services:
--------------

export class FruitService {
    private fruits: Fruit[] =  [];
    constructor(private backend: BackendService,
        private logger: Logger) {
            get fruits() {
                /*.........*/
            }
    }
}

Dependency Injection:
-----------------------



