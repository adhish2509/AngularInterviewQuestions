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


How do Observable handle errors?
Observables handle errors by setting an error callback on the observer rather than depending on try/catch, which is worthless in an asynchronous environment.


