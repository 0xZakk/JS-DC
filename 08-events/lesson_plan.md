# Events and Templating

## Class Structure
- Welcome to Class
- Review the Lab
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Closing Questions / Tying up loose ends
- Exit Tickets




## Review
Build a slide show - follow the steps, get and set properties of the DOM to build out a slideshow




## Introduction to Events
Goals:
  - introduce events and event types
  - talk about the most important/common events
  - discuss the event object


### Event Driven Development
- paradigm - way of approaching the construction of software
- in this case, event driven development means that user events determine the flow of the program
- events are typically user actions, but can also be sensor readings and output or messages from other programs
- event driven development is a dominant paradigm in JS application development
  - most often concerned with building out an application that is going to respond to user input
  - your War lab is a great example of event driven development, sort of
  - caveat is that we didn't need user input at each step in the loop
  - that is a refactor we could do that would make them even more event driven


### Event Types

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
- What is event driven development?
- Name one type/category of events
- Name one specific event




## Working with Events
- Two ways of working with events:
  - the browser will fire an event and we declare a function that should be called when that event is fired
  - we add an event listener to an element that, again, should be called when a particular event fires on that element

In one case, the browser is firing the event in another an element on the page is firing the event.


### Exercise 01
- learn about `document.onreadystatechange` and `window.onload`
- write the function that we want to be called when the event is triggered
- these events are part of objects that the browser gives us - they're built in
- we're providing the handler
- these events get fired whether we do anything with them or not, last class we didn't do anything with them
- what about attaching an event to an element, in addition to the event handler itself?


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


### Exercise 02
Build out a basic counter by responding to events

### Exercise 03
Learn about the event object

### The Event Object
- stopping default behavior
- `stopPropagation()`

### Review: Anatomy of an Event Handler



## Templating
Goals:
  - introduce templating, why it's useful and what kind of templating engines there are out there
  - write our first set of templates
  - use templates to generate static html
  - use templates dynamically

### Introduction
- way for us to be modular and reactive in how we construct an HTML page
- rather than having entire html pages all built out that we navigate between, we can have multiple bits and pieces to our page that we use to construct full pages in response to events and other triggers


### Types of Templating Engines / Languages
- Jade / Pug:
  - html processing component gives us everything a templating engine does but includes a cleaner way to write html
- Nunjucks / Swig: logic-full templating, typically with
- EJS - embeded JavaScript (port of ERB: Embeded Ruby)
- Handlebars / Mustache - logic-less (typically), typically recognized with `{{}}`


### Handlebars
- we're going to be using handlebars
- every templating language has it's pros and cons
- handlebars is beginner friendly and has a nice syntax

### Try Handlebars
http://tryhandlebarsjs.com/

#### Activity 1
Basic syntax of handlebars

Handlebars:
```
<div class="profile">
  <img src="{{ person.profPic }}">
  <h1>{{ person.name.first }} {{ person.name.last }}</h1>
</div>
```

JSON:
```
{
  person: {
    profPic: "http://0.gravatar.com/avatar/f190542c0ce80b9bc399f5039f6a8b86",
    name: {
      first: "Zakk",
      last: "Fleischmann"
    }
  }
}
```

#### Activity 2
Dynamic handlebars

__Each loop__
Handlebars:
```
<div class="profile">
  <img src="{{ person.profPic }}">

  <h1>{{ person.name.first }} {{ person.name.last }}</h1>
  <h2>Todos</h2>
  <ul>
    {{#each person.todos }}
      <li>{{this}}</li>
    {{/each}}
  </ul>

</div>
```

JSON:
```
{
  person: {
    profPic: "http://0.gravatar.com/avatar/f190542c0ce80b9bc399f5039f6a8b86",
    name: {
      first: "Zakk",
      last: "Fleischmann"
    },
    todos: [
      'learn JS', 'learn HTML', 'learn CSS'
    ]
  }
}
```

__if statement__
Handlebars:
```
<div class="profile">
  <img src="{{ person.profPic }}">

  <h1>{{ person.name.first }} {{ person.name.last }}</h1>
  {{#if person.todos}}
  <h2>Todos</h2>
  <ul>
    {{#each person.todos }}
      <li>{{this}}</li>
    {{/each}}
  </ul>
  {{else}}
  <h2>Done for the day!</h2>
  {{/if}}

</div>
```

JSON:
```
{
  person: {
    profPic: "http://0.gravatar.com/avatar/f190542c0ce80b9bc399f5039f6a8b86",
    name: {
      first: "Zakk",
      last: "Fleischmann"
    },
    todos: [
      'learn JS', 'learn HTML', 'learn CSS'
    ]
  }
}
```

### Working with Handlebars
Include it from a CDN:
`<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.5/handlebars.min.js"></script>`

Step 1:
- add the cdn reference to handlebars to the body `<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.5/handlebars.min.js"></script>`
- refresh the page and check that handlebars is loaded
- explore handlebars some

Step 2:
- how do we build a handlebars template here?
- using the script tag, giving it a type of handlebars:
```
<script id="hello-world-template" type="text/x-handlebars-template">
  <h1>{{title}}</h1>
  <h3>{{author}}</h3>
  {{#each content}}
      <p>{{this}}</p>
  {{/each}}
</script>
```

Step 3:
- template is sort of like any html element and we can get it with JS using it's unique ID
- `var source = document.getElementById('hello-world-template')`
- `console.log( source )`

Step 4:
- How do we compile our template now that we have it?
- `console.dir( Handlebars )`, find `compile` method
- `var template = Handlebars.compile( source )`
- `var template = Handlebars.compile( source.innerHTML )`
- `console.log( template )` => function
- call the function

Step 5:
- we have our template, we've compiled it, now how do we render it?
- `var renderedTemplate = template( data )`
  - `console.log( renderedTemplate )`
  - returns a string of our compiled template

Step 6:
- How do we add our template to the page?
- can we used `appendChild()`
- we can set `content.innerHTML`:
  - `content.innerHTML = renderedTemplate`


## Activity - Combining Events and Templating
Refactor our To Do list to use templates
