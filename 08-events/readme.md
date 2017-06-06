# Events

# Learning Objectives
- Understand how to work with events and how to implement event handlers
- Learn about event propagation

## Class Structure
- Welcome to Class
- Review the homework and/or do the warmup
- Go over Learning Objectives
- Deliver Lesson
- Closing Questions / Tying up loose ends
- Exit Tickets

## Review
Build a slide show - follow the steps, get and set properties of the DOM to build out a slideshow

## Introduction to Events
Goals:
  - introduce events and event types
  - talk about the most important/common events
  - discuss the event object

- last class we learned about the DOM and getting elements from an HTML page
- today we're learning about how we can listen for events on those elements
- not just events on certain elements but working with events in general

### Event Types
- we're going to start by thinking about the types of events we can listen for in JS
- cover these briefly then get in to listening for and halding events

Event Types:
Document: Events emitted by the `document` object
Window  : Events emitted by the `window` object
Mouse   : Events emitted from the mouse
Key     : Key press events (i.e. from they keyboard)
Form    : Form events (like `change` or `submit`)

- Going to dig in to a lot of these

### Specific Events

#### Document / Window Events
- load
- resize
- scroll
- unload

#### Mouse Events
- click
- dblclick
- mouseenter
- mouseleave

#### Key Events
- keypress
- keydown
- keyup

#### Form Events
- submit
- change
- focus

### Check for Understanding
- Name one type/category of events
- Name one specific event

## Working with Events
- Two ways of working with events:
  - the browser will fire an event and we declare a function that
  is called to handle that event

### Creating Event Listeners
Goals:
  - describe what an event listener is
  - create event listeners in JS for most common event types

Two ways of adding an event listener to an element:
- event specific function on the element object
- `addEventListener` function

Event Specific:
`someElement.onclick = function() { ... }`

Using `addEventListener`:
`someElement.addEventListener("click", eventHandler, false )`

### Exercise 01
Build out a basic counter by responding to events

### Exercise 02
Learn about the event object

### The Event Object
- stopping default behavior with `preventDefault()`
- `stopPropagation()`

### Review: Anatomy of an Event Handler
