
> angular application are modular in nature,
> this application are collection of individual module 
> angular framework is itself collection of angular module 
  
##### install node node-v18.17.0-x64
C:\Users\Dz>node -v
```
v18.17.0
node v > 8.X
```

C:\Users\Dz>npm -v

```
npm WARN config init.author.name Use `--init-author-name` instead.
npm WARN config init.author.name Use `--init-author-name` instead.
9.6.7

npm v > 5.X
```

##### install angular on system
C:\Users\Dz>npm install -g @angular/cli

```
ng version
C:\Users\Dz>ng v

     _                      _                 ____ _     ___
    / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
   / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
  / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
 /_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
                |___/


Angular CLI: 16.1.8
Node: 18.17.0
Package Manager: npm 9.6.7
OS: win32 x64

Angular:
...

Package                      Version
------------------------------------------------------
@angular-devkit/architect    0.1601.8 (cli-only)
@angular-devkit/core         16.1.8 (cli-only)
@angular-devkit/schematics   16.1.8 (cli-only)
@schematics/angular          16.1.8 (cli-only)

```

#### Component 
- component is nothing but javascript class with some meta data
- metadata tell us how to proccessed this particular class
- in our metadata we may have html which is going to view for component 
  and in our class we can have the logic i.e going to influence the view 
- component helps us to bind view and models.
- component contain most of the binding code.

#### Data Binding 
- it is comminucation between component(type script file) and view(html file).
- Typescript file is superset of javascript where we write logics in method and do calculation
  that result we are showing it to user throught template file i.e html view .
  for that we need communication to fetch typescript file result to html template to display result
  and this role is fullfill by by data-binding.
  
- data-binding is two way process , it can both send and recieve data means 
  when we change something in view then model update automaticaly .

##### ONE WAY DATA_BINDING
 - when we want to bind data from component file to  view file and vice versa then we use one way data binding.
   - ###### String Interpolation `{{ data }}`
      - here we use component class property in double curly bracess on view file.
      - when we have to bind component file data with the html file attribute.
      - `we can use only string in interpolation and also we can do string concationation.`
   - ###### Property Binding `[property]='data'`
      - here we used square bracket around html attribute i.e bind dynamic peroperty to html Attribute.
      - property binding is used with attribute only.
      - `we can use string as well as non-string in property binding but we can not do string concatination.`
      - when we have to bind component file data with the html file attribute. 
   - ###### Event Binding `(event)="expression"`   
      - here we bind view data i.e html attribute is with component data .
      - when user has interaction on html like click on button then that efect should refleft in component file.
        means compnenet data get change .
      - event-binding means perform action on some events.
      - angular has reserved variable i.e `$event`.
      - $event is used  to get the information of that event which we are triggering means info like event property .
      
        
         
        
##### TWO WAY DATA_BINDING
- here data is bind in both direction i.e from component to view and view to component on same time.
> [(ngModel)]="data"


### installing bootstrap
1. Normal Botstrap
2. NGX-Bootstrap

#### Normal Bootstrap
- open terminal and type : `npm install --save bootstrap`.
- in angular.json file, add css reference in styles array and js reference in script array
  and restart project if bootstrap not loaded.
  

#### NGX-Bootstrap
- it is built using angular native directive without using Jquery.
- it is fully compatible with angular.
- the component which we want to use , only that component we can add
  so that app will be light-weight and the unnessary component which we don't use will be not there .
- `npm install ngx-bootstrap --save `  
- import that module in app.module and use it's template code in component.   
   
#### Ng-Directive
- directive is nothing but the angular instruction which help to change the DOM behaviour and appreance.
- component itself is directive , whenever we are using selecter of any component in the template , at this point
  here angular instructing to place componenet content in place of this selecter.
- Three Types of Directive
   1. Component Directive
       - Directive with own component. 
   3. Structural Directive
       - manipulating the dom elements.
       - means it removes and add, dom element on condition based.
       - ex: ngIf , ngFor , ngSwitch
   5. Attribute Directive  
       - it helps to changes the dom looks and behaviour.
       - ex: ngStyle , ngClass 

#### Routing 
- routing simply meaning is navigation amongs pages .
- different diferent url for different different page we called them as route.
- Angular is single page application so we use directive to change the some portion of the page
  and finally we ar always on same page  and base URL remains same.
- to display different different pages like home , about , contacts... for this we use angular routes
  using which we change the particular page section and with section change we also change the URL .
  user seem that, the new page get loaded but behind the sceen javascript change the page content . 





