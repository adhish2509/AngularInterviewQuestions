# AngularInterviewQuestions
angular interview questions

How do you define Angular Framework?
Angular is an open-source front-end framework built on TypeScript. Angular makes it simple to create desktop, mobile, and web applications. Dependency injection, declarative templates, and e2e tooling are some of the key characteristics Angular framework's key characteristics which facilitate application development.
->bind model to the ui, implements M V Vm inside browser

What is the primary purpose of Angular?
The primary purpose of Angular is to help in creating Single Page Applications (SPAs). A collection of built-in modules from Angular make the creation of single page applications much easier. Additionally, Angular is also recognized as a complete web framework because of the features like modular CLI, type safety and built-in data streaming.

What exactly do Single Page Applications (SPA) do?
Single Page Applications are web-based programs that just require a single page load when minor adjustments to the UI are provided to add the new functionalities. The new page content is generated dynamically instead of loading/reloading the HTML pages. It is possible because of the ability of JavaScript to modify the DOM elements on the active page. The user experience is more consistent while using a single page application because it is faster.

What advantages does Angular give in comparison to other legacy technologies?
The following is a list of some of the main benefits of using the Angular framework:

It features two-way data binding, MVC pattern architecture, support for static and Angular templates, the ability to create custom directives, and RESTful services.
Incorporates important features including event handlers and animation, supports validations, supports dependency injection, communication between server and client and many more.

What is the default module that is used to bootstrap an Angular application?
Every application developed using Angular will have atleast one module called as bootstrapping module. The most frequently used module is the root module - AppModule

What does an Angular provider do?
In Angular, a provider is a service that may be customized. To facilitate loose coupling, maintainability, and reusability in Angular applications, the Angular provider is responsible for controlling the instantiation and configuration of objects that can be injected into components.

What distinguishes AngularJS from the Angular framework?

| AngularJS | Angular |
|-----------|---------|
| Programming language used is JavaScript | Programming language used is TypeScript |
| It uses MVC architecture | It uses a component-based approach |
| Uses bi-directional data flow | Uses uni-directional data flow |
| Mobile platforms are not supported | Mobile platforms are supported |
| Lazy Loading not supported | Lazy Loading is supported |

What are the core elements of Angular?
The core elements of Angular are as follows:

Components
Modules
Templates
Services
Metadata and Decorators


What motivated the development of client-side frameworks like Angular?
The need for client-side frameworks like Angular was driven by a variety of issues that programmers encountered when creating complex web apps. The following are some major issues behind the creation of such frameworks:

Richer User Interfaces:Since the traditional web applications were mainly server-rendered, the user interfaces were static and less interactive. There was a demand for frameworks that could manage these needs on the client-side with interactive and complicated user interfaces, similar to desktop apps.

Separation of Concerns: As web applications became complex, developers faced difficulties in maintaining a distinct separation of concerns and managing the codebase. For a clear separation of data, display, and application logic, client-side frameworks established architectural patterns as MVC (Model-View-Controller) and later MVVM (Model-View-ViewModel).

Single-Page Applications (SPAs): As SPAs became more popular, where the entire application is loaded only once and subsequent interactions are handled dynamically on the client-side without page reloads, frameworks were needed that could manage the application state and efficiently handle routing, data fetching, and UI updates.

Ecosystem and Tooling: Frameworks like Angular included a large ecosystem of tools, packages, and libraries that made the development, testing, debugging, and deployment processes easier. They supplied integrated development environments (IDEs) designed for effective web application development, build systems, automated testing, and tools for dependency management.

Collaboration and Code Reusability: Client-side frameworks promoted developer collaboration by defining standards and best practices. They encouraged code reuse through the use of components and modules, enabling developers to create applications more quickly and keep the codebase consistent.


For its apps, Angular uses client-side rendering by default. Can one create an application on Angular which also renders on the server side?
Yes, Angular uses Angular Universal module which is used for server-side rendering of Angular applications.
Using Angular Universal has the following benefits:

Users will instantaneously be able to see the application view which provides better experience for the new users
Since most of the search engines accept pages that are using HTML, Universal can guarantee that the content will be accessible to all search engines, improving SEO.

There are three components to the MVVM architecture:

Model
View
ViewModel
Model : Model contains an entity's structure. It essentially includes information about an object.
View : The application's visual layer is called the view. It presents the information that is included in the Model. This will be a component's HTML template, to use angular terminology.
ViewModel : The abstract layer of the application is called as ViewModel. A viewmodel manages the application's logic. It controls a model's data and presents it in the view.
Data-binding links the view and viewmodel together. All the changes which are updated in the view are recorded by the viewmodel and updates the relevant data accordingly inside the model

What is Just-in-Time (JIT) Compilation?
JIT compilation in Angular describes the dynamic conversion of Typescript and Angular Templates into JavaScript at runtime during the development phase. As you make changes to the code, the application can be updated right away. This enables quick development iterations.

How does Angular gets started when you serve the application? Mention the steps.
Each and every Angular application consists of a file called “angular.json”. The entire configurations related to the application will be contained in this file. The app developer checks this file to know the entry point of the application while creating the app.
The property “main” inside the options object within the build section mention’s the entry point of the Angular application, in most of the case it is “main.ts” file.
Next, in-order to bootstrap the Angular application the “main.ts” calls the function called as bootstrapModule. Furthermore, building a browser environment for the Angular application to run in.
The app.module.ts file contains a declaration for the AppModule. All of the component declarations are included in this module.
In the file app.component.ts, the component is specified. The webpage and this file communicate with one other and exchange data.
There are three properties declared for each component:

template/templateURL includes the component's HTML.
Accessing the component is done via a selector.
Component-specific stylesheets can be found at stylesURL.
Angular then calls the file index.html. As a result, this file invokes the app-root which is the root component.
app.component.ts contains a definition of the root component.
The <app-root> tag is used to display the HTML template for the root component.
This is how an Angular application works.

What does Angular declarable mean?
In Angular, declarable refers to a class, component, directive or pipe that can be declared and used within an Angular module. Declarables are a part of the declarations array in an Angular module's metadata.
Declarations would use the following format:
declarations: [
Component,
Pipe,
Directive
],

What limitations apply to declarable classes in Angular?
Below are few limitations that apply to declarable classes in Angular such as:

Module scope
Unique naming
Unique selector names
Directive selector restrictions
Template encapsulation


What is to be used to transform the data inside the template?
Pipes are used for transforming data inside templates. The primary function of the pipe is to display transformed data. The original data, however, will not be modified. Only the display will be impacted with the use of Angular pipes.

What types of pipes are available broadly in Angular?
Two types of pipes are broadly available in Angular:

Built-in pipes – provided by the Angular
Custom pipes – user can design their pipe as per requirement

List out some built-in pipes in Angular and their usage.

Uppercase:Uppercase pipe is used to convert the expression into uppercase.
Lowercase:Lowercase pipe is used to convert the expression into lowercase.
Titlecase:Titlecase pipe is used to convert the first character in each word of the given expression into a capital letter.
Currency:A currency pipe is used to display a currency symbol.
Date:Date pipe is used to display the date in the expected format
Percent:Percent pipe is used to display the number in a percentage
Slice:A slice pipe is used to extract a subset of elements or characters from an array or string, respectively.


How can pipes be chained?
Pipes can be accessed with the pipe symbol "|" and can be chained together using multiple | symbols, which come one after another pipe. The syntax for chaining pipes in Angular is shown below:
Today is {{ currentDate | date:’fullDate’ | uppercase}}

How to add multiple parameters in the pipes?
Parameterized Pipes are pipes that contain one or more parameters.
It uses a colon (:) in the command to pass multiple parameters.

What is the default value for minIntegerDigits, minFractionDigits, and maxFractionDigits?
minIntegerDigits: The default value is 1
minFractionDigits: The default value is 0
maxFractionDigits: The default value is 3

In which format will the date display if ‘fullDate’ parameter is used in the date pipe?
'fullDate' will display the date equivalent to 'EEEE, MMMM d, y'
(e.g., Monday, April 17, 2023)

If you have created a custom pipe called 'MyPipe' and you want to use it within a module. In which property of module metadata should you declare 'MyPipe'?
'MyPipe' should be declared in the declarations metadata of the module.

What is the use of the PipeTransform interface in custom pipes?
The PipeTransform interface needs to be inherited to create the custom pipe.
The PipeTransform interface includes a transform method for writing custom pipe functionality.

@Pipe({
name: 'pipename'
})
export class classname implements PipeTransform {
transform(value: any, ...args:any[]): any {
}}
**
How many arguments does the transform method include?
The transform method takes two arguments:
The value of the expression passed to the pipe that needs to be transformed and the parameter to pipe. Depending on the number of parameters passed to the pipe, the pipe can have multiple arguments. The final value should be returned by the transform method.

Q) Explain Angular Service
A) In Angular, a service is a class that includes functionality that may be reused throughout the application.
Angular services are a technique for abstracting common code and functionality across an application.
Angular Services come as objects which are wired together using dependency injection.
Angular provides a few inbuilt services and also can create custom services.

Q) What is dependecy Injection DI?
A) Dependency injection (DI) is a popular application design technique. It is used to ensure reusability. In the dependency injection technique, a class requests dependencies from outside sources rather than constructing them from scratch. Angular provides its own technique for dependency injection. Services are based on such a technique.
As a result, services can rely on other services throughout your application.


Q) Advantages of HttpClient
A) It has testability features.
Typed request and response objects are provided.
Request and response interception
Aids in the reduction of errors


Q) What is RxJs
Reactive Extensions for JavaScript (RxJS) is a third-party library
RxJS is a reactive stream library for working with asynchronous data streams .
In RxJS, observables are used to represent asynchronous data streams. In JavaScript, observables are a more complex version of promises.
Many APIs, including HttpClient, generate and consume RxJS Observables and utilize operators to handle observables
You can, for example, import observables and operators for use with HttpClient, as seen below.
import { throwError, Observable } from 'rxjs';

What is subscribing?
When someone subscribes to an Observable instance, it begins publishing values.
One must subscribe by calling the instance's subscribe() function and supplying an observer object to get notifications

What is the importance of a handler for the observer?
An observer object consists of next, error, and complete handlers.
These handlers used to get respective notifications and may use with any combination.
If the handler has not been provided with a notification type, the observer ignores it.


What is Obesrvable?
1.An Observable, like a Promise, is a distinct Object that can aid in managing async programming.
2.Because observables are not built into JavaScript, one must rely on RxJS, a popular Observable library.

The new keyword is used to generate the observables.

e.g.
import { Observable } from 'rxjs';
const ob = new Observable(observer => {
setTimeout(() => {
ob.next(‘It is a Observable!');
}, 1000);
})

An Observer is a consumer interface for push-based alerts supplied by an Observable. It has the following structure:

interface Observer {
next: (value: T) => void;
error: (err: any) => void;
complete: () => void;
}

There is a handler that implements the Observer interface and receives observable notifications. These observable notifications will be passed as a parameter for observable as given below,
myObservable.subscribe(myObserver);
Note: if a handler is not provided for any notification type, the observer will not consider the respective notifications

Enlist some HTTP requests performed by HttpClient.

GET method – get()
POST method – post()
PUT method – put()
DELETE method – delete()
HEAD method – head()
JSONP method – jsonp()
OPTIONS method – options(

How many parameters do the ‘get’ request take?
Http ‘get’ request takes one parameter, i.e., URL, from where one wants to fetch data.

How many parameters do a ‘post’ request take?
The httpClient.post() method posts data to the server.

It takes two parameters.

Data - data to be sent to the server
HttpOptions - to specify the required headers to be sent along with the request


What is the primary objective of using the Service in Angular?
The main purpose of Services can be:

Share the code/data across components of an application.
Have proper separation of concerns between component and service, as service can provide a space for making HTTP requests and component can take care of consuming the data shared back by the service


How to create a custom Service?
To create a custom service class, use the following command:
ng generate service

e.g., after execution of ,ng generate service data command, the following service class is created :

@Injectable({
providedIn:'root'
})
export class DataService
{
}


How are Observables in Angular superior to Promises in JS?
Due to following reasons, Angular recommended Observables for asynchronous calls, over Promises:
Promises only transmit one value, but observables (streams) emit many
Observables can be canceled, whereas Promises cannot. If an HTTP response is not required, we can cancel the subscription with observables, while the promise has to execute a success or failure callback even if the results are not required.
Observables can be used with functional operators such as filter, map, and reduce.


How do you make an HTTP service available to the entire module in Angular?
HttpClientModule must be imported from @angular/common/http in the module class to make HTTP service available to the entire module.
In the constructor of a component, import the HttpClient service class.
For communication, a few HTTP methods are available, like get, post, put, and delete.


What is the use of the HttpClient ‘put’ request?
HttpClient.put() method completely replaces the resource with the updated data.
It is like POST requests except for updating an existing resource.



How can service be provided in the application?
There are several ways to provide service in the application

Option 1: Register service in the providedIn property using @Injectable decorator.
e.g. import { Injectable } from '@angular/core';
@Injectable({
providedIn: 'root'
})
export class DataService {}

Option 2: Provide service across the application by registering it using the providers property in the @Ngmodule decorator of any module.
@NgModule({
imports: [BrowserModule],
declarations: [AppComponent, DataComponent],
providers: [DataService],
bootstrap: [AppComponent]
})

Option 3:Register the service in the providers' property inside the @Component decorator. Providing a service class inside a component creates a separate instance for that component and its nested components.
import { DataService } from './data/data.service';
@Component({
selector: 'app-root',
styleUrls: ['./app.component.css'],
templateUrl: './app.component.html',
providers:[DataService]
})


How does the subscribe method work?
Subscribe() accepts the callback function, which consists of next, error, and complete handlers.

For example, subscribe method is shown below,

myObservable.subscribe(
data => console.log('Observer has received a next value: ' + data),
err => console.error('Error has occurred: ' + err),
() => console.log('Observer completed’)
);



After configuring the routes, the next step is to decide how to navigate. Navigation will happen based on user actions like clicking a hyperlink, clicking on a button, etc. Hence, there is hyperlink based navigation and programmatical navigation.

Hyperlink based navigation
RouterLink directive can be used with the anchor tag for using hyperlink based navigation in Angular. Have a look at code shown below:

app.component.ts
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  styleUrls: ['./app.component.css'],
  templateUrl: './app.component.html'
})
export class AppComponent {
  title = 'Tour of Books';
}
 

app.component.html
<h1>{{title}}</h1>
<nav>
    <a [routerLink]='["/dashboard"]' routerLinkActive="active">Dashboard</a>
    <a [routerLink]='["/books"]' routerLinkActive="active">Books</a>
</nav>
<router-outlet></router-outlet>
Line 3-4: Create hyperlinks and a routerLink directive and specify the paths to navigate. Here, if a user clicks on the Dashboard, it will navigate to /dashboard. routerLinkActive applies the given CSS class to the link when it is clicked to make it look like an active link(active is a CSS class defined in app.component.css which changes the link color to blue in this case)

Line 6: <router-outlet> is the place where the output of the component associated with the given path will be displayed. For example, if the user click on Books, it will navigate to /books which will execute BooksComponent class as mentioned in the configuration details and the output will be displayed in the router-outlet class.

 

Programmatical navigation
To navigate programmatically, use the navigate() method of the Router class. Inject the router class into the component and invoke the navigate method as shown below.

this.router.navigate([url, parameters]) 
URL is the route path to which we want to navigate.

Parameters are the route values passed along with the URL.


How do Observable handle errors?
Observables handle errors by setting an error callback on the observer rather than depending on try/catch, which is worthless in an asynchronous environment.


What exactly is the Angular Router?
With the help of Angular Router, users can switch between views.
It allows programmers to create Single Page Applications (SPAs) with numerous views and enable navigating between them.

What is the purpose of the base href tag?
All relative URLs on a page must have a base URL specified by the href attribute.
The Angular router employs the base href tag to determine the base path to the component, template, and module files during navigation


What is the use of a router outlet directive?
The router outlet directive is available from the @angular/router package and used to mark where the component is inserted.
It is the primary tag for the angular application and the program's shell. Only the area the router outlet indicates will change no matter what we add to the shell.

As an illustration, using the login in the application will stay constant, while other things vary depending on the components.
< app-login > </app-login>
<router-outlet> </router-outlet>


How do you specify routes in Angular applications?
A router must have a list of route definitions specified.
Using the RouterModule.forRoot() method, you configure the router with routes and add the resulting value to the AppRoutingModule’s imports array.

const routes: Routes = [
{path:'login', component: LoginComponent},
{path:'signup', component: SignupComponent}
]
@NgModule({
imports: [RouterModule.forRoot(routes)]
})


How and when do you define a Child route?
When some routes can only be accessed and viewed from other routes, they should be created as child routes.
For example, from the product route, have an individual id, and one want to navigate to other routes to view the product’s details or specification.
The routes accept an array of child routes in the children property to achieve such a scenario.
The <router-outlet> directive is used to hold the child component.
export const routes: Routes = [
..
{ path: 'product-details/:id', component: ProductDetailsComponent,
children: [
{ path: '', redirectTo: 'home', pathMatch: 'full' },
{ path: 'home', component: HomeComponent }


How does the angular handle a wild route?
When A wild route is helpful when a URL doesn't match any specified routes.
Two asterisks (**) make up the path of the wildcard route, which can be used to match any URL.
e.g., if no route is mentioned in Routes, the application may produce error. The wild card route will render the respective component in such a case.

In the following example, if no route matches, PageNotFoundComponent will render.


What is the function of the RouterLink directive?
The RouterLink directive decides the navigation path. It is used on the anchor tags, giving the router control over those elements


How does the RouterLinkActive work?
The RouterLinkActive directive switches between CSS classes for active RouterLink bindings based on the RouterState.
The router will specifically apply CSS classes while this link is active and remove them when it is idle.
<h1>Angular Router</h1>
<nav>
<a routerLink="/login" routerLinkActive="active">Login</a>
<a routerLink="/signup" routerLinkActive="active">Signup</a>
</nav>


What are Angular Guards?
The Angular Guards are interfaces that tell the router whether or not the user can access a specific URL. Angular relies on a class that implements the Guards interface and returns true or false to make that decision. Guards are classified into five types:

CanActivate: This Guard is called for each access request and allows or denies the user access.
CanActivateChild: The same as before, but for child routes.
CanDeactivate: This Guard is invoked whenever a user wishes to depart from the current route (for saving form data when a user leaves early).
CanLoad: This Guard determines whether or not a user can access a lazily loaded module route.
canMatch: This Guard determines if a route can be matched


How to enhance application load speed in Angular?
Angular uses the ‘Lazy loading’ technique. The Angular application loads components, modules, or other assets as needed using lazy loading.
As Angular is majorly used to create a SPA (Single Page Application), all of its components are loaded at the same time. Due to this, libraries or modules that are not required may also be loaded.
This would suffice for a minor application. But if everything loads at once, load times will grow longer as the application expands.
Lazy loading facilitates asynchronous loading, i.e., load only modules whenever they are required. It uses the loadChildren property.
For example,
const routes: Routes = [
{
path: 'products',
loadChildren: () => import('./products/ products.module').then(module => module.ProductsModule)
}

Explain the difference between Eager and Lazy Loading.
Before the application starts, the application module, AppModule, is eagerly loaded. In contrast, feature modules contain all of the features of each module and can be loaded in two ways: eagerly or lazily or even preloaded in some cases.

Eager Loading: To eagerly load a feature module, we must import it into an application module using the import metadata of the @NgModule decorator. In small-scale applications, eager loading is widely used. All feature modules are loaded before the application starts when eager loading is enabled. This is why subsequent requests to the application are always faster.
Lazy Loading: To load a feature module lazily, use the loadChildren property in route configuration and ensure that the feature module is not imported into the application module. Lazy loading is generally beneficial when the application's size grows. Lazy loading allows feature modules to be loaded on demand, making application startup faster.



How do we access the Route parameters in Angular?
The router provides two different ways to access the route parameters. They are:

The Snapshot Way: The ActivatedRoute service is used to get a snapshot of the current route.
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';
@Component({
..
})
export class SampleComponent implements OnInit {
constructor(private myRoute: ActivatedRoute) {}
ngOnInit() {
this.params = this.myRoute.snapshot.params.params;
}
This is simple to use. However, as Angular reuses the components for performance, this method sometimes does not work.
For example, if we navigate from /products/1 to /products/2. In that case, we need to use another way which is The Observable/Stream Way. }


The Observable/Stream Way: This method uses observables. The Observable will pass along the new data when we navigate from one route to another.
The Angular router provides us with ParamMap, an Observable we can use.
ngOnInit() {
this.route.paramMap.subscribe(params => {
console.log(params.get('params'));
this.params = params.get('params');
});
}


-----------------------------------------------------------------------------------------------------------------
synechron Angular Interview Questions

semantics in html5
responsive ui
position
media query
iife
higher order function
hoisting
narrowing

