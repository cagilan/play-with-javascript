
Angular HTTP Client:
----------------------

Frontend application communicated with BE usig REST API (which is based on HTTP protocol) using either XMLHttpRequest or fetch() API.

Angular HttpClient uses XMLHttpRequest interfaces.

HttpClient is available from @angular/common/http package and has a simplied API interface and powerful features such as easy testability, typed request and response object, request and response interceptors, reactive APIs with RxJS Observables and streamed error handling.

Why Angular HTTP:
--------------------
* Its easy to send and process HTTP request and responses
* Builtin features for testing
* It uses RxJS observables for handling asynchronous operations instead of Promises which simplify the common web development tasks such as 
   ** Listening of progress of download and upload options
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
