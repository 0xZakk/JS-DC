
<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" style="max-width: 100px; border: none; box-shadow: none"/>
## Class 08: Events

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 45 min | Review & Warm Up Exercise                |
| 45 min | Events and event handlers                |
| 30 min | Events and event handlers cont'd         |
| 30 min | Events mini lab                          |
| 5  min | Closing Questions & Exit                 |

---
## Looking Ahead

| Lesson No. |        Topic             |
| ---------- | ------------------------ |
|     07     | Intro to the DOM         |
|   **08**   | **Events**               |
|     09     | Templating               |
|     10     | Express                  |
|     11     | Databases & CRUD         |
|     11     | APIs                     |
|     12     | Application Architecture |
|     13     | Lab #2                   |

---
## Homework Review!

---
## Warmup Exercise: Build a Slideshow!!
In the `/warmup` directory

---
## Events

--
### Types of Events
- Document
- Window
- Mouse
- Key
- Form

--
### Document / Window Events
- load
- resize
- scroll
- unload

--
### Mouse Events
- click
- dblclick
- mouseenter
- mouseleave

--
### Key Events
- keypress
- keydown
- keyup

--
### Form Events
- submit
- change
- focus
- blur

---
## Events

--
### Working with Events
- listening for events
- responding (handling) events

--
### Event Listeners & Handlers
```
let button = document.querySelector('.js-button')
button.onclick = function() { ... }
button.addEventListener("click", function() { ... })
```

--
### Exercise 1

--
### The Event object
- Passed to our event handler as a parameter/argument
- contains useful information about the event
- methods for controlling the event

--
### Anatomy of an Event Handler
```
var myButton = document.getElementById('#js-button')
myButton.addEventListener("click", function( event ) {
  console.log( "clicked on " + event )
})
```
