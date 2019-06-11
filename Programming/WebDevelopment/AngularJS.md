# AngularJS

`<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>`

## **Intro**

### Directives

*Invoked as an element name, attribute, class, or comment*

ng-app: defines an application  
ng-model: binds the value of HTML controls (input, select...) to application data  
ng-bind: binds application data to the HTML view  
ng-controller: directs data  
ng-init: initializes variables (not common)  
ng-repeat: repeats element  
ng-show: visibility  
ng-model: bind value of an input field  

{{ expression }}

```js
var app = angular.module('app', []);
app.controller('controller', function() {
    
});
)
```

*Adding 'data-' before directives makes the statements valid HTML*

Restrict directions with property 'restrict: E: element, A: attribute, C: class, M: comment

ng-model

