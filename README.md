# AngularInterviewQuestions
angular interview questions

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
