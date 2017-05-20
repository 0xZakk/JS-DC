# Templating & Build Tools


## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Homework Review
- How did people feel about the assignment?
- Do we feel confident about our understanding of working with events?
- Was this a fun / good / helpful assignment?
- Size off assignment: bigger / smaller?
- jQuery - what do people think of jQuery? Did anyone redo the pixart assignment with jQuery?

## jQuery
jQuery is a library for working with the DOM

Pros:
- provides an easy/simple interface for working with the DOM
- builds jQuery objects with a ton of helpful and easy to use methods
- truly incredible cross browser support

Cons:
- it's big and slow
- makes it difficult to actually learn JavaScript
- promotes a not great way of thinking about the DOM and building web applications

Why don't we spend class time on learning it?
- I'm conflicted about whether to teach it.
- This is a course on JavaScript and it would be a bit of a cop out to teach jQuery
- My fear is students wouldn't learn to understand the most important aspect of JavaScript, build dynamic web applications
- If you know it or you want to learn, go for it and feel free to use it in your homework assignments

## Templating
- templating is an important tool/method for us for a few reasons:
  1. gives us a way to be modular about how we construct a page for a user
  2. lets us react to user input and change parts or all of a page
  3. lets us get data into the page and respond when that data changes by updating the page

### Types of Templating Engines / Languages
- 3 classifications of templating Languages
  - recognize them by (1) their syntax and (2) their feature set
- Jade / Pug:
  - html processing component gives us everything a templating engine does but includes a cleaner, more terse way to write html
- Nunjucks / Swig:
  - logic-full templating (can process/manupulate data)
  - EJS - embeded JavaScript (port of ERB: Embeded Ruby)
- Handlebars / Mustache
  - logic-less (typically), typically recognized with `{{}}`

### Relation to web components
- if you've ever looked at react, you may have seen something like this (ref to component in slide)
- this is the opposite approach to templating
- in templating, the templates are solely for displaying data
  - especially true with handlebars (which is mostly logic-less)
- we often need some way of efficiently render variations of the same template depending on the data
  - this problem is what gave rise to logic-full templating
  - logic-full templating tries to - as the name suggests - provide logic in our templates (i.e. in html)
  - requires a lot of additional effort
  - components/react solution is to do the opposite, bring html into our JS, so we can use JS to build out our markup

### Handlebars
- we're going to be using handlebars
- every templating language has it's pros and cons
- handlebars is beginner friendly and has a nice syntax

### Try Handlebars
http://tryhandlebarsjs.com/

#### Activity 1
Basic syntax of handlebars
  - open up tryhandlebarsjs and cover the template, data and output
  - the template is where we'll write out what our final html will look like
  - the data is what we're going to give our template to render

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

### Turning Handlebars into Views
Now we know how to use handlebars, lets use it to build out views for our application.

Step 1:
First we need to get handlebars locally. We can use `npm` but for this were going to link to the library directly:

`<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.5/handlebars.min.js"></script>`

Step 2:
Lets define our first view! Below `app.js` add the following:

`<script id="to-do-template" type="text/x-handlebars-template">
    <li class="todo-list-item">Learn HTML</li>
</script>`

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
- `var renderedTemplate = template()`
  - `console.log( renderedTemplate )`
  - returns a string of our compiled template

Step 6:
- How do we add our template to the page?
- can we used `appendChild()`
- we can set `content.innerHTML`:
  - `content.innerHTML = renderedTemplate`

Step 7:
- lets modify this to use some data
- create a data object with a todos attribute and an array of todos
- refactor our template to loop through these todos and print each out

```
var data = {
  todos: [
    'Learn JavaScript',
    'Learn CSS',
    'Learn HTML'
  ]
}
```

```
<script id="to-do-template" type="text/x-handlebars-template">
    {{#each todos}}
      <li class="todo-list-item">{{this}}</li>
    {{/each}}
</script>
```

Step 8:
- all we need to change is we need to pass this data to our function that renders the template:
`var renderedTemplate = template( data )`
