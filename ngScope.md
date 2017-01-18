autoscale: true;
build-lists: true;

#[fit] $scope
(it's dope)<br>
(and it's not new)

---

# Objectives
* start to understand how controller scope works in angular
* name the angular directives that create their own scope
* understand how to troubleshoot $scope problems with above directives(hint:dot!)
* intro to "Controller as..." syntax

---

#[fit] Review
In your own words on whiteboards, what is scope?


---

# $scope is an object {}
* objects use __prototypal inheritance__
* whiteboards: own words, what does __prototypal inheritance__ mean?

---

# $scope is an object {} (cont'd)
* we are defining $scope in our controllers
* controllers are "glue" between the view(html) and JS code


---

# $scope is an object {} (cont'd)
* the base scope object in angular is __$rootScope__
* Q: implications of $rootScope: ?
* A: store variables that can be used through the app!

---
# $rootScope (you need to inject it)

```JavaScript
  var app = angular.module("myApp", [])
      app.controller("Controller1", function($scope,$rootScope) {
        $scope.name = 'matthew'
        console.log('scope',$scope);
        console.log('rootScope',$rootScope);
      });
```
---

...If you can read this, you are now listening to shapes...

---

# $scope inheritance, like genetic inheritance, can produce some unexpected results...
[galvanize learn article on scope](https://github.com/gSchool/angular-curriculum/blob/master/Unit-1/07-intro-to-scope.md)

---

# What can we do to remedy this behavior?

* create a property on a new object in the controller

```JavaScript
var app = angular.module("myApp", [])
      app.controller("Controller1", function($scope) {
        $scope.view = {}
        $scope.view.posts = [{id:1, title:'titular'},{id:2,title:'entitled'}]
      });
```
```html
  <div ng-repeat="post in view.posts">
    <p>
      {{id}}: {{title}}
    </p>

  </div>
```
---

# OR
* use "Controller as" syntax

---

* refresher: scope is a property attached to html elements
* certain angular directives create their own scope. Use a dot with these. They include...
  1. ng-controller
  1. ng-repeat
  1. ng-if (destroys scope every time its false, careful!)
  1. ng-view
  1. ng-switch
  1. ng-include

----

![fit](http://vignette1.wikia.nocookie.net/waldo/images/c/c9/Waldo_Zen_7-21-1996.jpg/revision/latest?cb=20070926005330)

---

fin
