autoscale: true
build-lists:true

#[fit] DOM events
![right](https://cdn-images-1.medium.com/max/800/1*hkP5rHnuVHHfbJGh4rzOuw.gif)

---

# Objectives:

* Attach event handlers to DOM elements
* Modify the DOM in response to an event
* Use callbacks in methods like addEventListener
* Explain the difference between this and event.target in event listeners
* Respond to the event DOMContentLoaded event

---

## Review: making a directory and files from the command line

(you tell me)
How can I efficiently create a new directory that includes and **index.html, app.js,** and a **style.css** file?

---

#[fit]WIRE IT UP

^have emmit for auto complete? create html shortcut
^why and how?, how can you tell if your css and js files are connected?

---

# EVENTS?
^gimme some examples

---

## _In your console on any webpage..._

```JavaScript
monitorEvents(window)
```
What do you see?

---

# Review: how do you view & access properties on the #document object?

* what events do you see?

^access document properties(methods) and event listeners!
^look at link to events in learn article...what else is going on besides screen events?
^next: start going through article exercises...

---

# Targeting elements in the DOM
(JQuery will make quick work of this, but how do you do it from scratch?)

_...so many ways!_

```html
<button id='myButton' class='buttonUp'>Click Me!</button>
```
```JavaScript
var btn = document.querySelector('button');
// OR
var btn = document.getElementsByClassName('buttonUp')[0];
// what does this return??
// OR
var btn = document.getElementById('myButton');
// OR
var btn document.querySelectorAll('button');
// OR
var btn = document.getElementsByTagName('button')[0];
// what does this return?

```
^do this in the app.js file and make sure that people are getting something back
^what exactly does the query selector return to you? //DOM node or element

---

#[fit] Now, we've targeted a node, so let's attach an event listener!

---


# eventListener(s)
* addEventListener
* removeEventeListener
* __these require a callback function__

---

# eventListner Anatomy

```JavaScript
// selector
var button = document.getElementById('myButton');

// example with anonymous callback function
button.addEventListener('click',function() {
  alert('someone clicked something somewhere');
})

// OR define a REUSABLE function
var alertMe = function() {
  alert('someone clicked something somewhere');
}
button.addEventListener('click',alertMe)

```

---

# Event Propagation
![right fit](http://javascript.info/files/tutorial/browser/events/event-order-w3c.gif)

---

## another view...

---

![fit](https://cdn-images-1.medium.com/max/800/1*etdwI7mSrwdO87Ma_rgL7w.png)

---

# THIS vs. event.target ???

---

# DOMContentLoaded?

---

# fin

---
