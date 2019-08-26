# AngularJS

`<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>`

## **Intro**

### Directives

```javascript
<new-directive></new-directive>
<div new-directive></div>
<div class="new-directive"></div>
<!-- directive: new-directive -->

var app = angular.module("myApp", []);
app.directive("newDirective", function() {
  return {
    restrict : "A",
    template : "<h1>Made by a directive!</h1>"
  };
});
```

*Invoked as an element name, attribute, class, or comment*

`ng-app`: defines an application  
`ng-model`: binds the value of HTML controls (input, select...) to application data  
`ng-bind`: binds application data to the HTML view  
`ng-controller`: directs data  
`ng-init`: initializes variables (not common)  
`ng-repeat`: repeats element `"el in elements"`  
`ng-show`: visibility  
`ng-click`: bind function to click  
`ng-if`: if function  

{{ expression }}

*Adding 'data-' before directives makes the statements valid HTML*

Restrict directions with property 'restrict: E: element, A: attribute, C: class, M: comment

### Model

`ng-model`: bind value of an input field  

*Adds the following CSS classes*
- `ng-empty`
- `ng-not-empty`
- `ng-touched`: been in focus
- `ng-untouched`: not been in focus
- `ng-valid`
- `ng-invalid`
- `ng-dirty`: changed
- `ng-pending`
- `ng-pristine`

### Controllers

```js
var app = angular.module('app', []);
app.controller('newController', function() {
    
}); 
)
```

### Scope

`$scope`: scope of the controller  
`$rootScope`: scope created in the element that contains the `ng-app` directive

### Filters

Add `|` after an expression

currency: Format a number to a currency format.  
date: Format a date to a specified format.  
filter: Select a subset of items from an array.  
json: Format an object to a JSON string.  
limitTo: Limits an array/string, into a specified number of elements/characters.  
lowercase: Format a string to lower case.  
number: Format a number to a string.  
orderBy: Orders an array by an expression.  
uppercase: Format a string to upper case.

```javascript
app.filter('newFilter', function() {
  return function(x) {
    var i, c, txt = "";
    for (i = 0; i < x.length; i++) {
      c = x[i];
      if (i % 2 == 0) {
        c = c.toUpperCase();
      }
      txt += c;
    }
    return txt;
  };
});
```

### Service

Pass dependency with $<service> with controller

```javascript
app.service('newService', function() {
  this.newFunc = function (x) {
  }
});
```

### Http

*Service*

`.delete()`  
`.get()`  
`.head()`  
`.jsonp()`  
`.patch()`  
`.post()`  
`.put()`  

```javascript
var app = angular.module('myApp', []);
app.controller('newCtrl', function($scope, $http) {
  $http({
    method : "GET",
      url : "index.html"
  }).then(function mySuccess(response) {
    $scope.index = response.data;
  }, function myError(response) {
    $scope.index = response.statusText;
  });
});
```

.config: the object used to generate the request.  
.data: a string, or an object, carrying the response from the server.  
.headers: a function to use to get header information.  
.status: a number defining the HTTP status.  
.statusText: a string defining the HTTP status.  

### Tables

*In the HTML*
- `$index`
- `$odd`
- `$even`

### Dropdowns

`x.field for x in array`  
`x.field for (x, y) in object`  

### Forms

```
Input fields have the following states:

    $untouched The field has not been touched yet
    $touched The field has been touched
    $pristine The field has not been modified yet
    $dirty The field has been modified
    $invalid The field content is not valid
    $valid The field content is valid

Forms have the following states:

    $pristine No fields have been modified yet
    $dirty One or more have been modified
    $invalid The form content is not valid
    $valid The form content is valid
    $submitted The form is submitted
```
*CSS classes*

```
The following classes are added to, or removed from, input fields:

    ng-untouched The field has not been touched yet
    ng-touched The field has been touched
    ng-pristine The field has not been  modified yet
    ng-dirty The field has been modified
    ng-valid The field content is valid
    ng-invalid The field content is not valid
    ng-valid-key One key for each validation. Example: ng-valid-required, useful when there are more than one thing that must be validated
    ng-invalid-key Example: ng-invalid-required

The following classes are added to, or removed from, forms:

    ng-pristine No fields has not been modified yet
    ng-dirty One or more fields has been modified
    ng-valid The form content is valid
    ng-invalid The form content is not valid
    ng-valid-key One key for each validation. Example: ng-valid-required, useful when there are more than one thing that must be validated
    ng-invalid-key Example: ng-invalid-required

```

### Includes

`ng-include="'file.html'"`: includes the HTML from another file

### Routing

`<ng-view></ng-view>`

```javascript
var app = angular.module("myApp", ["ngRoute"]);
app.config(function($routeProvider) {
  $routeProvider
  .when("/", {
    templateUrl : "main.htm"
  })
  .when("/london", {
    templateUrl : "london.htm",
    controller : "londonCtrl"
  })
  .when("/paris", {
    templateUrl : "paris.htm",
    controller : "parisCtrl"
  });
});
```

---

```
AngularJS Directives
Directive	Description
ng-app	Defines the root element of an application.
ng-bind	Binds the content of an HTML element to application data.
ng-bind-html	Binds the innerHTML of an HTML element to application data, and also removes dangerous code from the HTML string.
ng-bind-template	Specifies that the text content should be replaced with a template.
ng-blur	Specifies a behavior on blur events.
ng-change	Specifies an expression to evaluate when content is being changed by the user.
ng-checked	Specifies if an element is checked or not.
ng-class	Specifies CSS classes on HTML elements.
ng-class-even	Same as ng-class, but will only take effect on even rows.
ng-class-odd	Same as ng-class, but will only take effect on odd rows.
ng-click	Specifies an expression to evaluate when an element is being clicked.
ng-cloak	Prevents flickering when your application is being loaded.
ng-controller	Defines the controller object for an application.
ng-copy	Specifies a behavior on copy events.
ng-csp	Changes the content security policy.
ng-cut	Specifies a behavior on cut events.
ng-dblclick	Specifies a behavior on double-click events.
ng-disabled	Specifies if an element is disabled or not.
ng-focus	Specifies a behavior on focus events.
ng-form	Specifies an HTML form to inherit controls from.
ng-hide	Hides or shows HTML elements.
ng-href	Specifies a url for the <a> element.
ng-if	Removes the HTML element if a condition is false.
ng-include	Includes HTML in an application.
ng-init	Defines initial values for an application.
ng-jq	Specifies that the application must use a library, like jQuery.
ng-keydown	Specifies a behavior on keydown events.
ng-keypress	Specifies a behavior on keypress events.
ng-keyup	Specifies a behavior on keyup events.
ng-list	Converts text into a list (array).
ng-maxlength	Specifies the maximum number of characters allowed in the input field.
ng-minlength	Specifies the minimum number of characters allowed in the input field.
ng-model	Binds the value of HTML controls to application data.
ng-model-options	Specifies how updates in the model are done.
ng-mousedown	Specifies a behavior on mousedown events.
ng-mouseenter	Specifies a behavior on mouseenter events.
ng-mouseleave	Specifies a behavior on mouseleave events.
ng-mousemove	Specifies a behavior on mousemove events.
ng-mouseover	Specifies a behavior on mouseover events.
ng-mouseup	Specifies a behavior on mouseup events.
ng-non-bindable	Specifies that no data binding can happen in this element, or its children.
ng-open	Specifies the open attribute of an element.
ng-options	Specifies <options> in a <select> list.
ng-paste	Specifies a behavior on paste events.
ng-pluralize	Specifies a message to display according to en-us localization rules.
ng-readonly	Specifies the readonly attribute of an element.
ng-repeat	Defines a template for each data in a collection.
ng-required	Specifies the required attribute of an element.
ng-selected	Specifies the selected attribute of an element.
ng-show	Shows or hides HTML elements.
ng-src	Specifies the src attribute for the <img> element.
ng-srcset	Specifies the srcset attribute for the <img> element.
ng-style	Specifies the style attribute for an element.
ng-submit	Specifies expressions to run on onsubmit events.
ng-switch	Specifies a condition that will be used to show/hide child elements.
ng-transclude	Specifies a point to insert transcluded elements.
ng-value	Specifies the value of an input element.
AngularJS Directives on HTML Elements
AngularJS modifies the default behavior of some HTML elements.

Element	Description
a	AngularJS modifies the <a> element's default behaviors.
form	AngularJS modifies the <form> element's default behaviors.
input	AngularJS modifies the <input> element's default behaviors.
script	AngularJS modifies the <script> element's default behaviors.
select	AngularJS modifies the <select> element's default behaviors.
textarea	AngularJS modifies the <textarea> element's default behaviors.
AngularJS Filters
Filter	Description
currency	Format a number to a currency format.
date	Format a date to a specified format.
filter	Select a subset of items from an array.
json	Format an object to a JSON string.
limitTo	Limits an array, or a string, into a specified number of elements/characters.
lowercase	Format a string to lower case.
number	Format a number to a string.
orderBy	Orders an array by an expression.
uppercase	Format a string to upper case.
Filters are explained in Angular Filters.

AngularJS Validation Properties
$dirty
$invalid
$error
Validation is explained in Angular Validation.

AngularJS Global API
Converting
API	Description
angular.lowercase()	Converts a string to lowercase
angular.uppercase()	Converts a string to uppercase
angular.copy()	Creates a deep copy of an object or an array
angular.forEach()	Executes a function for each element in an object or array
Comparing
API	Description
angular.isArray()	Returns true if the reference is an array
angular.isDate()	Returns true if the reference is a date
angular.isDefined()	Returns true if the reference is defined
angular.isElement()	Returns true if the reference is a DOM element
angular.isFunction()	Returns true if the reference is a function
angular.isNumber()	Returns true if the reference is a number
angular.isObject()	Returns true if the reference is an object
angular.isString()	Returns true if the reference is a string
angular.isUndefined()	Returns true if the reference is undefined
angular.equals()	Returns true if two references are equal
JSON
API	Description
angular.fromJson()	Takes a JSON string and returns an JavaScript object
angular.toJson()	Takes a JavaScript object and returns a JSON string
Basic
API	Description
angular.bootstrap()	Starts AngularJS manually
angular.element()	Wraps an HTML element as an jQuery element
angular.module()	Creates, registers, or retrieves an AngularJS module
```