(tutorial)[https://www.tektutorialshub.com/angular-tutorial/]

Angular HTTP Client:
----------------------

Frontend application communicated with BE usig REST API (which is based on HTTP protocol) using either XMLHttpRequest or fetch() API.

Angular HttpClient uses XMLHttpRequest interfaces.

HttpClient is available from @angular/common/http package and has a simplied API interface and powerful features such as easy testability, typed request and response object, request and response interceptors, reactive APIs with RxJS Observables and streamed error handling.

Why Angular HTTP:
--------------------
* Its easy to send and process HTTP request and responses
* Builtin features for testing
* It uses RxJS observables for ~~handling~~ asynchronous **operations** instead of Promises which simplify the common web development tasks such as 
   ** Listening of progress of download and *upload* options
   ** Easy error handling
   ** Retrying failed HTTP requests
   
Prerequisites: (Typescript classes and Decorators)
---------------------------------------------------

Node 10+ and NPM 6+

NVM: POSIX-complaint bash script to manage multiple node versions. (POSIX - Portable Operating System Interface for UNIX. Developers have some assurance their software can be easily ported to POSIX-complaint OS)

STACKBLITZ online tool to develop and learn angular
------------

Angular 9:
____________

Ivy compiler and runtime by default. Ivy brings smaller bundle sizes, faster and better testing debugging, improved type checking, build times etc.


# Components:

* The component is the main building block
* Its plain JS class and defined using `@COMPONENT Decrotor`
* This decorator provides the component with the View to display and Metadata (Selector, Template, StyleUrl) about the class.

* It contains the data and `user interaction logic`. 
* It provides the data to the View using `DATA BINDING`. This is done by binding DOM elements to component properties. (special HTML markups called `ANGULAR TEMPLATE SYNTAX`). 
* Component also get notified when View changes
* Binding can be used to display component class property values to user, changle element styles and respond to user events. 

## 3 Building Blocks:

1. TEMPLATE 
2. CLASS 
3. METADATA


![Angular component architecture](https://www.tektutorialshub.com/wp-content/uploads/2016/09/Angular-Component.png)

### 1. Template ###

The templates are created with HTML. It defines the layout of the View and defines what to rendered on the page. 

**2 ways** 

1. Template inline
2. External template

### 2. Class ###

* The class is created with the Typescript or using JS
* Class contains Properties and Methods

The properties of the class can be bind to View using *Data Finding*

Simple class:

```
export class AppComponent 
{
  title: string = "app"
}
```

### 3. MetaData ###

* It provides additional information about the component to angular
* Angular uses this information to process the class. 
* The metadata is defined with a **Decorator**

Decorator is a function that adds metadata to class, method and properties.

* The components are defined with a `@Component class decorator`. The @Component decorator defines the `class as component to Angular`

The decorator must be positioned before to class definition. 

#### Meta Data Properties ####

1. Selectors: Simple css selector where our View represent the component.

** Several options to use component selector **

**1. Class Name:**

```
@Component({     
  selector: '.app-root' 
})
```
<div class="app-root"></div>

**2. Attribute Name:**

```
 @Component({ selector: '[app-root]' })
```

```
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
```
<div app-root></div>

**3. Attribute Name & Value:**

```
 @Component({     
   selector: 'div[app=components]' 
}) 
```
<div app="components"></div>


2. Providers: Providers are the services, that our component going to use. The services provide service to the component.

3. Styles/styleUrls: CSS styles or stylesheets for component. Either inline styles / external styleurls

4. Template/templateUrls: HTML Template that defines our View. Either be inline template / external template url.

### Creating the component ###

Angular CLI created the root component called **AppComponent.ts**

#### Steps to create component file: ####

1. Create the Component file
2. Import the required external Classes/Functions

**Angular core library:**

```
import { Component } from '@angular/core';
```

**3. Create the Component class and export it**

```
export class AppComponent {
  title = 'app';
}
```
 
**4. Add @Component decorator**

```
@Component({
})
export class AppComponent {
  title = 'app';
}
```
**5. Add metadata to @Component decorator**

```
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
```

**6. Create the Template**
**7. Create the CSS Styles**
**8. Register the Component in Angular Module**

The Angular Module organizes the components, directives, pipes, and services that are related and arrange them into cohesive blocks of functionality.

It is a class that is adorned with @ngModule decorator

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
 
import { AppComponent } from './app.component';
 
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

We use @NgModule class decorator to define a Module and provide metadata about the Modules.

We add all the components, pipes and directives that are part of this module to the **declarations array.** 
We add all the other modules that are used by this module to **imports array**. 
We include the services in the **providers’ array.**

The Component that angular should load, when the **app.module** is loaded is assigned to the **bootstrap property.**


# Data Binding in Angular 

* It kees the Component and View in sync wit each other
* Interpolation, Property Binding, Event Binding and Two way binding(ngModel)

## From view to component 

**1. Interpolation:**

```
export class AppComponent {
  firstName= 'XXX';
  lastName=”XXX";
 ```
 Welcome,  {{firstName}} {{lastName}} . - The content inside the double braces is called *Template Expression*

**2. Property Binding: (class, href, src, textContent)**

```
export class AppComponent {
  title="Angular Property Binding Example" // Binding to innerText
  isDisabled= true;
 
}
```
<h1 [innerText]="title"></h1>
<button [disabled]="isDisabled">I am disabled</button>

**3. Class Binding:**

ClassName Property binding
Set the Class attribute with class binding
ngClass directive

**4. Style Binding: Style Binding / ngStyle Directive**

**5. Attribute Binding: **

Sometimes there is no HTML element property to bind to. The examples are **aria (accessibility) Attributes & SVG**
```
<button [attr.aria-label]="closeLabel" (onclick)="closeMe()">X</button>
```

## From Components to View:

1. Event Binding:

```
 <button (click)="onSave()">Save</button>
```

**Two way Binding:**  *banana in a box [()]*

```
import { FormsModule } from '@angular/forms';
<input type="text" name="value" [(ngModel)]="value">
```

ngModel directive is not part of the Angular Core library. It is part of the @angular/forms.

ngModel, behind the scene it sets up *property binding & event binding*. It binds to the *value property of the element using property binding*. It then uses the *ngModelChange event to sets up the event binding to listen to the changes to the value*.















