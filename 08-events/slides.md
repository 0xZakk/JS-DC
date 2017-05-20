

<img src="https://ga-core.s3.amazonaws.com/production/uploads/program/default_image/5225/JS-logo-official.png" style="max-width: 100px; border: none; box-shadow: none" />
## Class 08: Events

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 45 min | Warm Up Exercise                         |
| 5  min | Break                                    |
| 45 min | Events and event handlers                |
| 5  min | Break                                    |
| 30 min | Events and event handlers cont'd         |
| 30 min | Events mini lab                          |
| 5  min | Closing Questions & Exit                 |

---
## Looking Ahead

| Lesson No. |        Topic             |
| ---------- | ------------------------ |
|     07     | Intro to the DOM         |
|   **08**   | **Events**               |
|     09     | Templating & Build Tools |
|     10     | Express                  |
|     11     | Databases & CRUD         |
|     11     | APIs                     |
|     12     | Application Architecture |
|     13     | Lab #2                   |

---
## Warmup Exercise: Build a Slideshow!!
In the `/warmup` directory

---
## Events

--
### Event Driven Development

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

--
### Event Handlers

--
### Working with Events
- Browser fires an event
- Action on an element triggers an event

--
### Exercise 01

--
### `window.onload` versus `document.onload`
- different across browsers
- `document.onload` - when the DOM is ready
- `window.onload` - when the page is ready (including images, assets, etc)

--
### Writing our first event handlers
- `document.onreadystatechange = function() { ... }`
- `window.onload = functionReference`

--
### Event Listeners
```
var button = document.querySelector('.js-button')
button.onclick = function() { ... }
button.addEventListener("click", function() { ... })
```

--
### The Event object
- Passed to our event handler as a parameter/argument
- contains useful information about the event
- methods for controlling the event

--
### Stopping the default event behavior
- `event.preventDefault()`
- avoid navigating to a url when a link is clicked

--
### Stop event propagation
- `event.stopPropagation()`


--
### Anatomy of an Event Handler
```
var myButton = document.getElementById('#js-button')
myButton.addEventListener("click", function( event ) {
  console.log( "clicked on " + event )
})
```
