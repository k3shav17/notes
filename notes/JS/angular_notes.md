# ANGULAR

- **Angular** is a single page application development platform to develop a front-end or UI things for an application. It separates the business logic from the view.

- **Decorators**: Decorators in angular are a design pattern which allows us to separate the modification and decoration of a class without changing source code.

- Dependency Injection or DI is a design pattern in which a class requests dependencies from external sources rather than creating on its own.

- **Angular application flow**

 1. The angular project builder will look into the angular.json file for the paths and configurations to check which is the main file, the builder then starts the app from 'main.ts'.
 2. This is the entry point of the application and this file sets the browser environment for the application to run[platformBrowserDynamic is an import which is responsible for this].
 3. The main.ts file will call a function 'bootstrapModule(AppModule) which tells the builder to bootstrap the app, then app.module.ts file will gets loaded, this file contains the declarations of all the components we are creating in the app module, so angular is aware of them.
 4. From here the control goes to app.component.ts file, this is the file that will interact with html file. And the index.html file will call the app.component.html file because the selector of app component html is present in index.html

 Simply
 > angular.json(for configuration) -> main.ts -> app.module.ts -> app.component.ts -> index.html -> app.component.html

## Observable and promise difference

- Both *Promises* and *Observables* provide us abstractions that help us to deal with the asynchronous nature of application.

- **Promise** => It handles single event when an asynchronous operation completes or fails

- **Observable** => It is like stream in java, which allows us to pass 0 or more events. Observable is preferred over promise, because it does not matter if we want to handle 0 or multiple events. Observables has advantage over promise, that is observables are cancellable.

- Promise is for eager initiation, which starts immediately and where as Observables is for Lazy initiation, it only starts if we subscribe to it.

- Observables provides operators like 'map, forEach, reduce etc'

 > @NgModule, @Component, @Injectable, @Pipe

 **@NgModule** => NgModule is a class which is marked by @NgModule decorator, which takes the metadata object that describes how to compile a template and how to inject the dependencies at the runtime. (It identifies modules own components, directives and Pipes and makes some of them as public using export property, so that external component can use them).

 **@Component** => Components are the main building block for angular application. Each component consist of html, css, ts and a test file. A class can be declared as a component with @Component decorator.

 **@Injectable** => This decorator specifies that angular can use this class in the DI system, and the providedIn attribute of this decorator means that class is visible throughout the application.

 **@Pipe** => It is a class that is decorated with @Pipe decorator, which defines a function that transforms the input vaiues to output values to display them in the view.

### app.module.ts four properties usage

 **Declaration**: This section is used to declare a newly created component that needs to be visible to entire application.
 Imports: This section is used to import external resources that is used by the application to perform some tasks.
 Providers: This section is to provide the services that is used by the application.
 Bootstrap: This is section is to specify which component needs to be bootstraped to run the application.

:exclamation: EcmaScript vs JavaScript

 ECMAScript is a standard for scripting languages like javascript, jScript etc. Simply, ECMAScript is a language and Javascript, jscript, actionscript are dialects. Is ES and JS equivalent? The answer is no. Eventhough the core principles of JS are based on ES, there are features that are present in JS and not in ES

**ES6 features**
 Arrows, classes, enhanced object literals, template strings, destructuring, default + rest + spread, iterators + for of, generators unicode, modules, module loaders, proxies, symbols, promises, binary and octal literals

### let, const and var difference

- let: The scope of a variable that is declared using let is in the method or the function itself.
- const: Variable which is declared using const is a constant and can't be changed.
- var: Variable which is declared using var will be having a scope of global, and the methods or functions that are declared using this keyword will be attached to the window object of the browser.

### JavaScript vs TypeScript

 Typescript is the statically typed version of Javascript and TS is the superset of JS

- Angular component Life cycle hooks
- Routing concepts
- Angular component communication
- Angular services like HttpClient
- User defined services
- Different kinds of forms

### Two way data binding

- Angular supports two way data binding use Forms module, which is a in-built module provides this feature.

- *()* is data flowing from view to the component and *[]* is data flowing from component to view.

- **[(ngModel)]** provides data to be flown from both sides.

### Life-cycle of angular component

- When we use a selector to call a component, angular creates an instance of that component, which is basically object creation.

- **ngOnInit()** will be called on object initialization.
