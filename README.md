# Angular

install Node.js and npm
1.Node version 4.6.x or greater
2.npm 3.x.x or greater

https://angular.io/guide/quickstart
git clone https://angular.io/guide/quickstart folderName
npm install -g @angular/cli
ng new my-app
cd my-app
ng serve --open

The import statement is used to import functionality from the existing modules.
Each application consists of Components. 
Each component is a logical boundary of functionality for the application.
You need to have layered services, which are used to share the functionality across components.


A component consists of −

Class − This is like a C++ or Java class which consists of properties and methods.

Metadata − This is used to decorate the class and extend the functionality of the class.

Template − This is used to define the HTML view which is displayed in the application.

app.component.ts --->it is main component
app.module.ts ------> it is main module and all component are attach to main module 


******/\*************

angular2 is component based approch 
component are the individual and free peice of logic and view
everything in angular2 is component based 

typescript :- here we code in typescript and typescript is toatlly object oriented programming  it is class base

Component :- it is individual piece of module,
	     which can contain specific view and method of app.
			 
	1.Template :- html viw of the component, can contain data-binding and directive 			 
		      ex: login component when we access login component we will see login form 
	2.class :- clasess can contain the method and properties of the components
				after click on login which functionality  running  

	3.decorator/metadata :-it provide additional informative data about component to the angular app
				like it tells which selector,which template many things like that
				
				
AppModule :- it is root module which boostrap and launches the angular application 



Data Binding 
-==-=-=======---

data-binding			Discription 
--------------------------------------------------
1.one way data-binding		From component to view template 
2.one way data-binding		From View Template to component 
3.two way data-binding		From component to view template  & From View Template to component

1.one way data-binding : deals with binding component class property to its corresponding view template
2.one way data-binding : deals with binding  view template to its corresponding component class property
3.two way data-binding	: its back ianf forth

 # interpolation can also be use with methods
 {{ getFullName() }}
 {{ pageHeader ? pageHeader : "No Haeder"  }}

#interpolation can also be used to bind component class property with html element property
<img src="{{ imagePath }}" />



BOTH interpolation and property binding flows a data value in one direction 
i.e from component class property to an html element property 

interpollation vc  propertybinding
------------------------------------
interpolation is a special syntex that angular converts into property binding 
interpolation is just a convenient alternative way  to property binding
to concatinate string we must use interpolation instead of property binding 
<img src="http://www.dz.com/{{ imagePath }}" />
to set an element property to a non-string data-value ,you must use property binding 
<button [disabled]="isDisable">Click Me </button>

# its not working as expected 
<button disabled="{{ isDisable}}">Click Me </button>  ...Here we must use property  binding

#interpolation and property binding automatically sanitizes the malecius content before rendering it on browser
 
#we can think DOM is an API ,for this html so we can use programming language like javascript ,javascript framwork (angular)
 to access and modified this html elements using their corresponding DOM Objects 
in other DOM contain html element as Object their porperties ,methods and events and it is standard for accessing ,modifying ,
adding or deleting HTML elements

HTML Element Attribute v/s DOM Property 
=>Attribute are defined by HTML ,Where as Property are defined By the DOM 
=>Attribute Initialise the DOM Properties, Once Initialisation Complete ,Attribute JOB is Done 
=>property value can change ,where as attribute value can't
ex: 
<input id="ind" type="text" value="Tom" />
so the job of value Attribute of Input Element is to initialise value property of the inpute Object in the DOM 
onConsol type 
:=>					    
	ind.getAttribute('value') :- this is the value of the  Attribute value 
we know there will be corresponding value property in the inpute Object of DOM
	ind.value   :- here we use value property of the input object in the DOM
After changin value 
ind.getAttribute('value') returns old value 
ind.value  returns new update value 
so property value can change ,where as attribute value can't

NOTE :- 
1.HTML Attribute And DOM Property Are Different Things 
2.Angular Binding Work with properties and Events ,and NOt Attribute 

disabled is DOM Property ,and NOt Attribute 


angular databinding is all about binding to DOM object properties not a html element attribute 
interpolation bind component class property to DOM property not to attribute of html element 
ex:-collspan attribute does not have corresponding property in the DOM 

#interpolation and property binding deal with binding component class properties to html element properties and not atribute

#ngModel :- this directive provide two way data binding i.e it keeps this input property name on html and its corresponding
	property name on component class in synck 	 

following thses binding flow data in one direction i.e from a component class property to an html element property 
1.interpolation 
2.property Binding
3.Attribute Binding 
4.class binding
5.style binding 

#eventBinding :-flow data in opposite  direction i.e from an html element property to a component class property

for property binding we are using pair of square bracket 
for Event binding we are using pair of parenthesis
 
angular databinding is combination of property binding and event binding 
to save several keystroke and simplify angular two way databinding ,angular has provided ngModel directive 
to use ngModule we should import FormsModule in root module i.e app.module

employee : any[]{
}
here 'any' is type of array which allow any type of object to be added to this array  and it is not good practice  

 				
ngFor dirctive is typically use to iterate over list of items 
ngFor : if it is small list we dont have performance issue but if it large list we face performance issue so use ngtrackBy

using trackBy may improve the performs of appliocation 

pipes : transform data before display 
built in pipe provided by angular :-lowercase,uppercase,decimal,date,currency 

#to pass properties from parent component  to the child component
we will have to convert child component properties into input properties for so we have to decorate this properties to input decorator/metadata



A service in angular is generally used when you need to reuse data or logic accross multiple component
in angular service is nothing but class
constructer is not right place to call service 
service call usually issued over a http to remote web server 
what is right place of serviec call ?
:- ngOnInit life cycle hook is the best place of service call 
ngOnInit is executed after the constructer and it is used for component instialisation and making service call
	
Diff Class constructer and NgOnInit
:-


proverder property of component Decorator  to register our EmployeeService with angular Dependancy injection system

 
 HTTP 
 ===========

:-call server side web api services using angular http built in serivice 
  http service present in different angualr module 
 step1: within the root module (AppModule), import angular HTTP module 
        with this change we can now able use angular bilt in http services
		
step 2: modify EmployeeService to issue  a GET request using the built in http services		
		

what is observable ?
:-an observale is asynchronous pattern 
  in this pattern we have observable and observerer
 observable :- emmits data item on notification over a periiod of time 
 observerer(subscriber)	:- can subscribe to  observable 
						  when subscribing to observable specify the callback function 
						  that callback functio of observerer is notified whenever this observable emimit data item 
						  within that function we will write the code to handle the data item emmited by the observable
						  observable can have multiple observerer(subscriber)
 
 
step 3: From EmployeeListComponent ,subscribe to the observable returned by angular EmployeeServices
				


 HTTPModule   reff: https://www.concretepage.com/angular-2/angular-2-http-get-example
 -============
Angular HTTP library provides Http client for server communication. get() is the Http client method that uses HTTP GET method to communicate server using HTTP URL. 
We need to pass HTTP URL to Http.get() and it will return the instance of RxJS Observable. 
To listen values of Observable we need to subscribe it. We can also directly fetch Observable value in our HTML template using async pipe. 
Observable can be converted into Promise using RxJS toPromise() method. 
Http.get() communicates to server only when we fetch values from Observable or Promise.
				
Http.get() performs a request with HTTP GET method. The syntax is as given below.
	get(url: string, options?: RequestOptionsArgs) : Observable<Response> 
get() is the method of angular Http API that interacts with server using HTTP GET method. 
It accepts a HTTP URL and returns Observable instance. RequestOptionsArgs is optional.

We should perform server communication in a service class and not in component.This approach is preferable by design.
In a service class we will use dependency injection to get the instance of angular Http as given below.
constructor(private http:Http) { } 

http.get() returns instance of Observable that can be later subscribed to get result.
We can also fetch Observable directly in HTML template using async pipe.
Observable<Response> ob = this.http.get(this.url); 

Observable and Promise
-------------------------
We can use either Observable or Promise with http.get(). 
Observable: This is a RxJS API. Observable is a representation of any set of values over any amount of time. 
	All angular Http methods return Observable. Observable provides methods such as map(), catch() etc. 
	map() applies a function to each value emitted by source Observable and returns finally an instance of Observable.
	catch() is called when an error is occurred. catch() also returns Observable. 

Promise: This is a JavaScript class. Promise is used for asynchronous computation. 
	 A Promise represents value which may be available now, in the future or never. 
	 Promise is a proxy for a value which is not known when the promise is created. 
	 Promise has methods such as then(), catch() etc. http.get() returns Observable and to convert it into Promise we need to call RxJS toPromise() on the instance of Observable.
	 The then() method of Promise returns a Promise and that can be chained later. 
	 The catch() method of Promise is executed when an error is occurred and it also returns Promise.

In Http.post() method, we need to pass server URL, any object to post and request option that is optional.
In request option we can set request headers such as content type and to handle this angular provides Headers and RequestOptions API. 
Headers class is used to create request header and RequestOptions is used to create request option using headers, credentials etc. 
Http.post() method returns the instance of Observable of Response type. Using angular Response we can access response status, headers etc.


 HttpClient  Module 
 -==========-========
HttpClient has been introduced in Angular 4.3 version.
HttpClient is smaller, easier and more powerful library for making HTTP requests.
To use HttpClient we need to import HttpClientModule in our application module and then we can inject HttpClient in our components or services.
HttpClient has methods such as get, post, delete, put etc.HttpClient.get constructs an Observable with configured GET request 
and when the Observable instance is subscribed,GET request is executed on the server. 

HttpClient serves the purpose to perform HTTP requests. HttpClient is injectable class. 
To perform http GET request, HttpClient provides HttpClient.get method that accepts URL and options for parameter, header etc 
and returns an Observable instance. When we subscribe Observable then GET request is executed on the server.

get(url: string, 
    options: { headers?: HttpHeaders | { [header: string]: string | string[]; };
		    observe?: HttpObserve;
		    params?: HttpParams | { [param: string]: string | string[]; };
		    reportProgress?: boolean;
		    responseType?: 'arraybuffer' | 'blob' | 'json' | 'text';
		    withCredentials?: boolean; 
	      } = {}) : Observable<any> 

The response type of HttpClient.get is Observable i.e. provided by RxJS library. 
Observable is a representation of any set of values over any amount of time.

In HttpClient.post method we need to pass URL, request body and optional http options such as headers, response type etc. 
We need to provide generic return type to HttpClient.post method.
HttpClient.post method performs POST request over HTTP requests. 

post(url: string, body: any | null, options: {
    headers?: HttpHeaders | {
        [header: string]: string | string[];
    };
    observe?: HttpObserve;
    params?: HttpParams | {
        [param: string]: string | string[];
    };
    reportProgress?: boolean;
    responseType?: 'arraybuffer' | 'blob' | 'json' | 'text';
    withCredentials?: boolean;
} = {}): Observable<any> 

HttpClient.post has following arguments. 
1. url: Pass URL as string where we want to post data. 
2. body: Pass data of any type as body to be posted. 
3. options: We can pass options such as headers, parameters etc. This argument is optional. 

The response type of HttpClient.post is RxJS Observable which represents values over any amount of time. 

Find the attributes that can be passed as options argument in HttpClient.post request. 
headers: Defines HttpHeaders for http POST request. 
observe: Defines whether we want complete response or body only or events only. 
params: Defines parameters in URL. 
reportProgress: Defines whether we want progress report or not. 
responseType: Defines response type such as arraybuffer, blob, json and text. 
withCredentials: Defines whether we want to pass credentials or not.

Observable 
-==========
:-Observable belongs to RxJS library. To perform asynchronous programming in Angular application we can use either Observable or Promise.
When we send and receive data over HTTP, we need to deal it asynchronously because fetching data over HTTP may take time.
Observable is subscribed by using async pipe or by using subscribe method. 
Observable is a class of RxJS library. RxJS is ReactiveX library for JavaScript that performs reactive programming.
Observable represents any set of values over any amount of time. Observable plays most basic role in reactive programming with RxJS.
Some methods of Observable class are subscribe, map, mergeMap, switchMap, exhaustMap, debounceTime, of, retry, catch, throw etc. 
To use RxJS library in Angular programming we need to ensure that we have installed RxJS. 
In case we are using Angular CLI, it installs RxJS by default. We can ensure it by checking package.json. 
If RxJS is not there in package.json, we can install it as following.
	npm install rxjs --save 
To use Observable in our Angular application, we need to import it as following.
	import { Observable } from 'rxjs/Observable'; 


Angular HttpClient performs HTTP requests for the given URL. HttpClient works with Observable. Find some of its methods.
get(url: string, options: {...}): Observable<any>
post(url: string, body: any | null, options: {...}): Observable<any>
put(url: string, body: any | null, options: {...}): Observable<any>
delete(url: string, options: {...}): Observable<any> 
Look into return types of the above methods, each and every method of HttpClient returns instance of Observable. 
When we subscribe to the Observable instance, then actual HTTP operation is performed. 
The Observable instances can also be executed using Async Pipe.
Angular async pipe subscribes to Observable and returns its last emitted value.

Observable subscribe
-===================
subscribe is a method of Observable class. subscribe is used to invoke Observable to execute and then it emits the result.
If we have an Observable variable that fetches data over an HTTP then actual hit to server takes place only when we subscribe to Observable using subscribe method or async pipe.




Error Handling
-==============
To handle error, Angular provides HttpErrorResponse class from @angular/common/http library. 
HttpErrorResponse contains useful information regarding error. The second parameter in subscribe() is for error. 
HttpClient.get can face two types of errors. 
a. If backend returns unsuccessful response codes such as 404, 500 etc then HttpClient.get will throw error with backend response code. 
b. If something goes wrong client-side, for example, an exception is thrown by RxJS operators or 
   if network error prevents the request from completing successfully then actual Error object is thrown by HttpClient.get. 

We can check if error is of Error type or not by using HttpErrorResponse and accordingly log the error messages.

Observable Error Handling
-==------------------------
:- To handle error in Observable, it provides methods such as throw, catch, retry. The method throw can throw custom error.
 catch method caches the error thrown by Observable and then it can either return new Observable value or can throw custom error using throw.
 The method retry just retries executing Observable for the given number of times. 
 To handle error in subscribe method, the second argument of subscribe caches the error.

throw creates an Observable that immediately emits error. throw is a static method of Observable. 
It is used to conditionally throw error from map, mergeMap, switchMap etc.

catch is a method of Observable class. catch method catches errors in the Observable to handle it by returning a new Observable or throwing an error







to install bostrap library into node use fallowing commond
1.run node.js commond propmt as run as administrator
2.opon upto project directory through common propmt
3.then type commond :- npm install bootstrap@3 jquery --save 

to  ngx ui framework of angular
:-npm install ngx-bootstrap --save dont use npm install ngx-bootstrap@ --save




to use AngularMultiSelectModule add dependancy to root module
open project dir in cmd and type commond : npm install angular2-multiselect-dropdown
and import in root module 
 -->import { AngularMultiSelectModule } from 'angular2-multiselect-dropdown/angular2-multiselect-dropdown';
 

 

Two way s to create forms in agular
1.Templete Driven form 
2.Model driven Forms(commonly called reactive forms)

Templete Driven form 
-----------------------
create templeteReference variable which will reffer to our form using ngForm Directive 
(ngForm dirctive is present in or provided  FormsModule so import Forsmodule in root module)
this ngForm directive suppliments this form element with additional feutures and properties like 
dirty ,touch,valid , value etc


#component input property are typically used to passed data from parent component 
to child component and to create an input property decorate the property with @input decorator
here child component is responcible for displaying parent component data
import the Import Decorator from core
ex: 
child-compo:- @Input() emp: EmployeeListComponent or employee   
parent-compo:-
	html-->
			 <div *ngFor="let employee of employees">
				<child-compo [emp]="employee" > </child-compo> 
			  <div>
			  
#To detect and react when an input property value changes 
1.property setter
2.ngOnChanges LifeCycle hook

		    

-----======*******-========-------			  
#to pass data from child component to parent component we use Output property 
#using template refference variable we can call public property or method  of child component from parent component


child-compo:- @Output() notify: EventEmitter<string> =new EventEmitter<string>();
			handleClick()
			{
				this.notify.emmit(this.employee.name);
			}

parent compo :- 			
html-->
			<h1 *ngIf="dataFromChild">
				{{dataFromChild?.name +''+dataFromChild?.gender }}
			<h1>	
			 <div *ngFor="let employee of employees">
				<child-compo [emp]="employee" (notify)="handleNotify($event)" > </child-compo> 
			  <div>
at controller :-recieves the emploee name in 
				handleNotify(eventData: string )
				{
				 this.dataFromChild=eventData;		
				}

why  are we setting the type of our output property to an EventEmmiter object 
thats because a  child component usess an event to pass data to an parent component 								
what data we want to pass and when we do we want to pass that data  				
when their is click event on the employee Panel
EventEmmiter object help us to emmit a custom event 
eventData is comonly called as even payload
in the view templete of  parent component we need to bind this custom notify event 
when the child component raised this event it also going to pass employee name as event data
and $event object is going to recevice that event payload 
? safe navigation operator 


				
 how to call child component properties and methods from parent component using templete refference variable?
-->one way to do this by using Output Property 
  another way to this by using templete refference variable
  
  in the view templete of parent component 
  create templete refference variable that point to our child  component
  which is used to call any of the child component public property and methods 
  

href :-   
	 <base href="/" > this means all our navigation url now will be relative
	 to the root of the application
	 since we set base as this all the other url now relative to root of application
	 base href tells the angular router how to compose navigation urls

Passing Data between components
-===-=========================
if component are nested then there is parent child relationship between those component

1.passing data from Parent component to child component 
:- Input property  { part 21 :Angular 2 tutorial ,part 33 angular curd tutorial}

2.passing data from child component to Parent component 
:- Output property {part 22 :Angular 2 tutorial ,part 37 angular curd tutorial},
   Template Refference Variable { part 38 angular curd tutorial }

3.passing data from components to component (Not Parent child relation ) 
:- Angular Service { part 34 :Angular 2 tutorial } 
#we can also use route parameter to pass data between components 
Required Route Parameter { part 40 angular curd tutorial }
optional Route Parameter { part 43 angular curd tutorial }
Query Parameters  { part 51 angular curd tutorial }

Routing
-=-=-------
:we need to to import router module 
routerModule contain all the angular routing feutures that we need 
such as router service ,routing directive like routing links ,routerlink active router outlet etc
import it in app module and then configured the application routes for that we need to import type called Routes
from the same angular router package 
create the const appRouts which as anrray of routing objects 
next we need to let the angular router, know about our configured routes way we do that by using 
forRoot method of RouterModule ,for this method we pass our configured routes as argument
navigate to some link we tell that to the angular router using a Directive called routerLink and routerLink direcive is provided by routerModule
(<a>)ancor tag on html
 roter-outlet directive :-it is provided by RouterModule  
 so dependending on the route that is active that respective route view templete is displayed at the location where we have this router-outlet directive 
 and we routing to the coponent so we no need to have selector in the component

#In angular we have sevaral RouteGuard
RouteGuard are used to get confirmation from user to move from one url to another
1.CanDeactivate :- Guard navigation away from the current route 
2.CanActivate :- Guard navigation to a route 
3.CanActivteChild :-Guard navigation to a child route
4.CanLoad :- Guard navigation to a feuture module loaded asynchronysly
5.Resolve :- Perform Route Data retrieval before route activation

steps to use a RouteGuard
:-
1.Build the route guard
2.Register the Guard with angular dependancy injection system
3.Tie the guard to a route

#we create template reference variable by exporting ngForm directive and ngForm directive has dirty property
which is used to check form is dirty or not , we dont have access to ngForm directive within the component class 
to get access for ngForm directive within the component class we use @viewChild Decorator
@viewChild("template reference variable name")
limitations of canDeactivate Guard :-canDeactivate Guard does not work if we type the url in address bar directly 
				and does not work when navigate to external url

#creating the route with parameter 
:- in the route defination include a (forslash) / : name of the parameter
ex: { path : 'employee/:id ' ,component : EmployeeDetailComonnent }


# activating the route 
:-to activate the route in code we use angular router service navigate method 
to this navigate method we pass link parameter array 
within the navigate method of Router serviec we pass array as an argument
this array is called link parameters array ,first parameter/elemnt to this arry is the path to the destination component
and second elemnt of array is rote parameter

this._router.navigate(['/employees', EmployeeId],)

what if we want to activate the route declaratively in the html 
:-we use router link derective notice we bind router link directive to the same link parameter
<a [routerLink]= "['/employee',2]">get employee with id 2 </a>


#How to read route parameter value in angular 2
:-read employee id from the url and retrive that specific employee details using employee service 
reading route parameter value is easy,angular provide service for that and
that servie is called ActivatedRoute service so import and inject the service where we want to use
on  ActivatedRoute object we have params property and it return observable
so one way to read route parameter value is by subscribing Observable we have other aproch also 
that aproch is snapshot aproach	 on this snapshot property we have params property and now to read router parameter value we have to specify
its name remeber when we define this route in route modul file we specify the route parameter value 


#difference between routerLink and [routerLink]
:- if we are binding to simple string (ex: routerLink="/list" )	then we dont need square bracket
we need to use this square bracket when we are binding this directive to link parameter array (ex: [routerLink]="['/list']" )
or binding to a property within component class 

#In angular 2 on snapshot object we use params property like this ( const id= +this._route.snapshot.params['id']; )
on otherhand if we are using angular 4 or future version they introduce a new property called paramMap
param have been depricated since angular 4 ( const id= +this._route.snapshot.paramMap('id');  )

#read route parameter value is by subscribing Observable
:-if we want the user to be able to navigate from employee to employee directly without navigating to list employee component first
then we will have to use Observabel aproch ,the snapshot aproch will not work  beacuse the code we have in this ngOnInit is only executed 
when the component is first loaded and initialised after that when we click nextEmployee or any event occure ,the route parameter value 
chnages but this component is not reinisialised and hence the code we have in this ngOnInit is not executed now if we want to react to 
route parameter changes and execute some code everytime this route parameter value changes then we will have to subscribe to those changes 
so in ngOnInit instead of using snapshot aproch to read the route parameter value lets use observable aproch 

#since we are subscribing , everytime the route parameter value changes we reciew a notification and when that happend 
we want to execute some code 

#when to use snapshot over observable ?
:-
snapshot :-if the route parameter value does not change and you  only want to read the intial route parameter value 
-====----

Observale :-if the route parameter value change and if you want to react and execute some code in responce to that changes 
-========

note :- whenever we subscribing an observable we also must unsubscribe from it 
	however their are some exception to this rule ActivateRoute Observable is one such exception
	we dont have to expletcitly unscribe from this Observable beacuse the angular Router take care of that for us


Optional Parameter
-========-======---
:-on some route parameter are required and on some route they are optional
<a class="btn btn-primary" [routerLink]="['/targetUrl''required parameter','optional paramter']">Back to List</a>
to pass optional paramter we use an object and specify optional parameter as key value pair
to read route parameter wheather it is required or optional we use same service provided by angular which 
is ActivatedRoute Service.

Angular Required vs Optional Parameters
:-
1.Required route paramter are part of route configuration where as optional parameters are not 
2.Required Route paramter are used in patern matching where as optional route paramters are not 
3.optional route parameters must be passed after the required route parameters if any
4.prefer  a required route paramter when the value is simple and mandatory .
for ex: to view specific employee detail, the ID parameter is mandetory  and it is simple integer 
on the other hand ,prefer an optional route parameter when the value is optional and complex 

#to prevent canDeactivate Guard from being triggered we must rest the createEmployee form  before 
attempting to redirect the user to the list Employee form
Reseting the form is easy we can do that 
in the  html declratively or programatically in code 

#object referece variable are pointers to object ,they are not object themselve
let e1= new Employee('venket');
let e1=e2;
e1.name=null;
e2 is affected 

let e3= new Employee('venket');
let e4=Object.assign({} ,e3);
e3.name=null
e4 is not affected 

#Angular team recommond not to use filter pipe to filter and sort data
this is because the filtering and sortind pipe can significantly impact the performnce of the application if not implemented carefuly

two types of pipe
:-
1.pure
2.impure

whenever we create new pipe its pure by default (ex: pure :true)
if we want to make this pipe impure ,change value of this false  ,imoure pipe are bad perfomrs perspective

pure :- executed only when a pure change to the inpute value is detected
	what is pure change ?
	:-pure change is either a change to a primitive input value (String ,Number,Boolean ) or a
          changed object reference (Array ,Date , Object )
pure pipr are very fast because javascript is very quick at checking if there is  pure change 
a pur pipe is NOT Executed if the input to the pipe is an object and only the property values of the object 
change but not the reference 

#pure pipe are fast ,but filtering and sorting may not work as expected if the source data is updated 
without change to the object reference .
#using an impure pipe to filter and sort data is not recommonded because it is processed on every change , 
even when source data does not changed ,
the recomonded aproch is to move the filtering and sorting code to the component itself so you have better 
control on when that code should and shouldnt execute

Query string paramter
-=-====================
http://localhost:4200/employees/3?searchTerm=john&testParam=testValue
:-Query string paramter in the url start with '?' and if we have multiple query string parameter they are seprated using ' & '
Query paramter are usually used when u want the parameters on the route to be optional and when u want to retain those parameters 
acrose multiple routes.
just like optional route parameters , query paramters are not part of the 
route configuration and therfore they are not used in  route patern matching
this._router.navigate(['/employees', EmployeeId])
#to pass query string paramter in codes we pass second parameter to the navigate method and
that second paramter is an object ,the key for this object is an queryParams and value is an other object this object contain 
our query string paramter key value pair ,u can have as many query string paramter as u want 

#passing query string parameters in code
this._router.navigate(['/employees', EmployeeId] , { queryParams : { 'searchTerm': this.searchTerm , 'testParam': 'testValue' } } )

this is on component side but what if we want to pass them in html
#passing query string parameters in html
<a [routerLink]="['/employees']"
   [queryParams]="{ 'searchTerm : 'john' , 'testParam': 'testValue' }" >
   List
</a>

in html we used queryParams directive  here we bind queryParams directive to an object and this object contain
query string paramter as key value pair and resulting url will look like this http://localhost:4200/employees/3?searchTerm=john&testParam=testValue
when we back form this url ,we have lost our query string paramters that beacuse by default query string paramter are not retain between diferent route 
to be able to retain them we have to explicitly configured  and the way we do that is by using  queryParamsHandling directive 

Prserve query string Paramters in code 
:-
this._router.navigate(['/employees', EmployeeId],{
      queryParamsHandling : 'preserve'	or 'merge'
      });

Prserve query string Paramters in HTML
:-
<a [routerLink]="['/list']" queryParamsHandling ="preserve" >
Back to list	
</a>		

#the value to queryParamsHandling is preserve or merge 
merge: if we any queryStringParameter here where we adding queryParamsHandling or when we are navigating that new query string paramter will be merged 
with the already existing query string parameter  but in case of preserve it is not merged we only have wxisting query string paramter 

#queryParamsHandling is introduce in angular 4 ,in angular 2 we dont have instead we will have to use preserveQueryParams directive ,
preserveQueryParams directive is depricated since angular 4


#In Angular we have three types of parameter 
1.Required Parameter
2.optional Parameter
3.Query Parameter

#using ActivatedRoute we can read Query string Paramter 
there are two aproches to read query string parmeter
1.snapshot aproch
2.observable aproch

whether we are using snapshop aproch or the observable aproch there are theree methods and properties that are extreamly usefull
1.has(name) :- method return true if the paramter is found in the parametre map else it return false
		this method is usefullto  check existing of optional route and query paramters

2.get(name) :- this method return one of the three things 
		if specified paramter is found in the paramter map it returns the parameter value 
		if parameter not found it return  null
		if the paramter value is an array then it returns the first element 

3.getAll(name) :- this method is usefull when u know ,the parameter value is an array of values 
		so this method is going to return array of value if the specified parmter is found in the paramter map 
		if parameter not found then it return empty array

4.Keys() :- it return string array of all the parameters


#to work with query param we use queryParamMap property
#to work with required or optional route paramter we use ParamMap property 

#we should use observable aproch  ,why do we need to return observble ?
:- in real world application we will not have data hardcoded ,we retrivie it from database by callinfg server side service using 
angular http service ,angular http service returns an observable and caller or where we are consuming this service ,has to subscribe 
to that observable and the way we do that by usig subscribe method .
when we call the getEmployee method of employee service it returns the data immedietly without any delay but in real world application we 
retrive data from db by calling server side service so there may be some network latency and we may not get data immedietly so introduce som artificial latency 
by rxjs delay operator 

#resolve Guard  
:-if we dont want to display partial page to the user while we are waiting for data ,it can be fixed by using resolve guard 
 before we activate the list route and display the view template associted withe list route we want to prefetch the data 
 once the data is avilable thats when we want to render the view template so the end user does not see partial page 
 in short we want to delay rendering the routed component view template until all neccesory data have been fetch 
 #to prefetch data for a route we use routeResolver
 routeResolver can be use as function or as a service 
 step 1: implement the route resovler service in its own file 
 step 2 : register the route resolver service in app module in provider
 step 3: add the route resolver service to the route for which we want to prefetch the data 
         add resolve property to the  route object ,the value for the resolve property is an object containg key and value 
	 u can give any  meaningfull name to key   and value is our resolver service 
	 when angular router see this resolve property on a route its going to use associted resolve service to prefetch the data 
	 and then activate the route and render its associated view template 

step 4: read prefetch data from activateRoute 
------------------------------------------------------

#sequence of navigation events  that are trigger by the angualr router when navigating from one route to another route 
this navugation events range from when the navigation start and ends too many points in between 
to see the sequence of events trigger by the angular router all we have do is enableTracing 
here we pass an object as second paramter to the forRoot method and withing that object set enableTracing : true  
it will log all navugation event triger when navigatin from one to another on console 

#first event that is trigger is NavigationStart this  event is trigger when route navigation start then RouteRecognized  event is trigger 
fallowed by that we have GuardCheckStart event this event trigger when the route guard start executing 
some of this events have  corresponding end event ex: NaviagtionEnd ,  GuardCheckEnd 
we cann use them to moniter route or troubleshooting  when application routing does not work as expected 
we may also use them to display loading or proccesing request msg if ther is delay navigating from one route to another 
#when navigation start we want to display loading indicator and when navigation end we want to hide loading indicator 
to be able react and execute some code in responce to this router navigation event we need to subscribe to the angular
Router Event Observable ? where we do the subscribe to the Router event observable 
appComponent here we use <router-outlet> directive and depending on the route that is active the associated component view template  
is render at the location wher we have this roter outlet directive this component is  aware any route chnages  
so import NavigationStart and NavigationEnd event from angular router package 


this._router.event.subscribe() :- so every time when the navigation events  emmited by the angular router 
		we are notified of that event because we are subscribe and specify some callback function so we can execute some code
		in responce to those navigation event  ,the event that is raised is passed as paramter to the callback function																			

CanActivateGuard
-==================
:- 
use cases of CanActivateGuard
:-1. it is used to check if the user is authenticated before allowing him to access protected area of our appliaction 
     if the user is not authencated we redirect the user to acces denied component or login component
  2.similarly we can also use it check if the specific resource his looking for exist 
    if resource does not exist we redirect him to page Not Found component 
    if resource exist we redirect the user to navigate that specific resource 

step 1: implement canActivate Guard as a service 
	:-implement the guard serviec class make the guard service class implement canActivate Interface and  provide implementation of interface method

step 2: Register the guard with angular dependancy injection system
step 2: tie the  guard to a route that u want to protect	


create component 
:
ng g c employees\displayEmployee --flat --no-spec


onChanges method is call every time when input property of this comonent is changes 
and changes to the input property are pass into this method as a parameter and parameter has type 
and that type is SimpleChanges  and that available in angular core 


Template driven form is heavy on the template
form tag :-whenever angular sees this form tag ,its going to automatically attach directive called ngForm to this form element
	ngForm dirctice supliments form element with addtional feutures 
	it keeps track of the all the form control that we create and moniter their property
	like value valid touched dirty pristin etc 
	to get refference to form we create varibale like #empForm = "ngForm"
	here #empForm called the template refference variable meaning it hold a refference to this entire form


Bydefault angular 4 and later version disabled browser native validation .
how to enable browser validation
:-Bydefault angular 4 and later version disabled browser native validation by 
automatically including novalidate attribute on the form tag
novalidate:-this  attribute instruct the browser not to do its own validation

ngNativeValidate directive  :-this enable browser built in validation
				
why it is better to disable browser built-in validation and use angular to validate instead
:- different browser vendors implement browser validation differently and as result ,end user have different experience 
depending on browser they used
because of this inconsistency it is better to disabled browser native validation and use angular instead to validate form field

Error :-
Angular form validation property 
1.touched - untouched
2.pristine-dirty
3.valid-invalid
this property are avialable at each control form level

html 5 validation attribute 
1.required
2.maxlength
3.pattern									      
4.min
5.max

angular uses html 5 validation attribute  for validating form field and displayig validation error message
ngModule directive provide two way data binding i.e it keeps this input property name on html and its corresponding
property name on component class in synck ,export this ngModel directive into the local template refference  variable  
it is also called as local variable or template variable or local template refference variable 
#fullName="ngModel"

Employee model instead of angular genrated form module 

using this local template refference variable we can access those three set of validation property
i.e touche untouched ...

boostrap classess has for validation error message 
:-
has-error
control-label
help-block
 

#Binding Angular form to our own model class
#using multiple validators on a single input field
#Angular safe navigation operator

#email validator is new and introduce in angular 4
#to use regular expression we use pattern validator
#email validation regular expression
pattern="^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$"
pattern="^[a-zA-Z0-9_.+-]+@(?:(?:[a-zA-Z0-9-]+\.)?[a-zA-Z]+\.)?(dz)\.com$" :-only take anything@dz.com

whats the difference between value and ngValue
:-if option value is simply string then use value property
otherwise if option va;ue is null or object then use ngValue property

custom validator 
:- to use cutom validator in template driven form we have to create that validator as directive 
onec we have the directive created we can then use the directive as an attribute on the select element that we want to validate
this is going to be configurable and reusable data we can use it with any select list in an angular application 

Befor we are using our custom validator we have to register our custom validator with the list of validator that angular already mentains
by using providers property 
NG_VALIDATORS : this is called big token in angular and it contain  list of all validator including angular built in validators
		for as to be able to use our custom validator will have to register it with  NG_VALIDATORS thats the reason we have set 
		useExisting: SelectRequiredValidatorDirective, also need to set
		multi : true

and we need to import our custom validator in the module where we want to use it
right now we have only one module i.e root module i.e appModule 

#use ngModelGroup directive to create a sub-group within a form
#we can register the service at component level or module level
when we register the service at component level then that service is availabel only to that component and its children
if register at module level then it is available to all the component in  application


Forms
=====

FormBuilder
-----------==
:- It is used to create a big reactive form with minimum code in Angular. 
FormBuilder has methods as group(), control() and array() that returns FormGroup, FormControl and FormArray respectively. 
Using FormBuilder we can directly pass object or array of object of a class to create the form.
We need to create form HTML template with formArrayName by assigning the field name of that class. 
Suppose we want to create a FormGroup with some fields, then first create a class with those fields and then pass the instance of that class to FormBuilder.group() and 
it will return FormGroup with form controls with same name as class fields. After form submit, we can get complete form value as an object of a class.

FormBuilder creates reactive form with minimum code using FormGroup, FormControl and FormArray. FormBuilder has following methods. 
group(): Creates FormGroup. 
control(): Creates FormControl. 
array(): Creates FormArray. 


Form Control
-=============
FormControl are the basic building blocks of a reactive form or a form in general. Think of them as input box,select box, radio buttons, dropdown etc.
Under the hood it’s a class which tracks a particular form control and keeps track of its validity and values.

Form Group
-==========
FormGroup is a collection/group of FormControls. 
It also offers many api’s such as tracking validity and values of the whole formGroup.

# Since FormArray, FormGroup & FormControl all extend from AbstractControl so I guess a FormArray can consist of any of those .
AbstractControl — 
can be skipped not part of the public API directly.
A thing to note about these FormControl, FormGroup & FormArray is that they all inherit from AbstractControl.
AbstractControl is something which holds most of the API’s that are exposed by FormControl, FormGroup & FormArray 
like valid , value , errors, touched, untouchedetc. 
exposes some abstract method such as setValue, patchValue& reset which get overridden in all the 3 classes explained above.

There are some rules which I keep in mind while designing the form structure.
I think they can prove helpful while structuring a form so I am listing them here. 
Always refer to this rules and you’ll never face any difficulty and after a point of time you get used to it.

RULE 1: Whenever there is a formControl(smallest entity of a form like an input) with any other basic block
	like FormControl, FormGroup, FormArray. We have to nest them under a FormGroup.
RULE 2: Whenever you find yourself saying something like X has many Y, that is when you should know you are 
	looking at a possible FormArray of Y inside X(where X is almost always a FormGroup).











