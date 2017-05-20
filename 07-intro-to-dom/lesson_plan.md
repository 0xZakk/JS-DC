# JavaScript in the Browser

## Class Structure
- Welcome to Class
- Review the Lab
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Closing Questions / Tying up loose ends
- Exit Tickets






## Lab review
- How do students feel it went?
- What did people find difficult?
  - structuring their program
  - approaching the task of writing a program
  - the syntax
  - understanding the material (data types, loops, conditionals, functions, objects)
- Are students proud of what they put together?
- Are students excited about the challenge?

*Go through solution briefly with students*






## Looking Ahead
- finished part 1 of the course
- part 1 is our introduction to the language by focusing on the language features
- the rest of the course is more focused on using the language
- we'll continue to use everything we learned in part 1 on a regular basis
- focus will be on using the language and becoming JavaScript developers

### Intro to JavaScript: Part II
- building applications in JavaScript
- start on what we call the front end or the client side of an applications
  - what the user sees and interacts with
  - start with the dom - how does the browser build and render HTML web pages and how can we use javascript to interact and manipulate an html web page once it's been rendered
  - templating: building an html page on the client using javascript, rendering new parts of the page with new data
  - we'll also talk about build tools which are ways for us to use javascript to automate mundane work that comes with building websites or web applications
  - take a jump to the back end and build our first server. using a framework called Express, we'll build servers that can respond to http requests
  - once we know how to build servers, we'll need to know how to work with databases so we can save data somewhere safe. At this point we'll be able to build feature rich applications
  - then we're going to talk about APIs - at this point we'll have everything we need to build our own APIs and to work with APIs others have built. An API is often shrowded in mystery but it's really just a pattern for organizing a server that manages data in a database - we'll know how to build servers, we'll know how to work with databases, so we'll know how to build APIs
  - We'll close this section off by talking about application architecture - this lesson will focus on how we break up our application into different parts, what functionality do we put where and why
- our lab for this class will be a clone of the popular Hacker News site
- one we know how to build applications probably around lesson 11 or 12 we're going to start thinking about the final project - we'll do some early ideation to figure out what you want to build and get started at a very high level







## JS In the Browser
**Goals:
- introduce the browser and an environment to program and run JavaScript
- how are the browser and JavaScript related?
- how do we run JS in the browser?
- what is the JS console? how do we interact with it?
- 'hello world' for the browser**

### History
- we remember from our first day of class, when we talked about the history of JavaScript, that it was built originally for the browser
  - wasn't until later that we were able to run JavaScript on the server
- JS started as a client side scripting language
  - change, move, remove, update elements on the page in the browser
- that's still an incredibly important part of JS
  - what we're focusing on learning today
- doing stuff to what's on the page, after the page has loaded
- making our static html pages dynamic

### How do Browsers work
- When a user loads a page or navigates to a URL a couple of things happen
- first the browser makes a request to a url (something we'll talk about when we talk about servers and APIs)
- the browser gets back an document that is written in HTML
- it then parses that document and does a bunch of stuff with it but the steps that we care about are:
  - it fetches the assets it needs to render the document, so the css and the JavaScript
  - it then builds a model of the document's structure and uses that model with a rendering engine to draw that page on the screen
  - this document model is what we care about today

### Exercise: How do we use JS in the browser
- Open up a browser and navigate to the console
- reference the browser's `document` object

**Exercise 1:**
- Demonstrate the console, how to get to it and what it is
- Compare it to the live node environment we saw when we ran `node` in the terminal
- explore the `window` and `document` objects
- `console.log( 'sup world?' )`

How do we run JS in the browser?
Method 1: Inline, in the `script` tag
- html is a markup language made up of tags that we can use to structure a document
- one of those tags is the `script` tag
*Add a `script` tag to `index.html` and `console.log('hello world')`*

Method 2: External js files
- just like we can reference external stylesheets, we can also reference external JavaScript
- using the `script` tag but giving it a path to a JS file
*Modify the `script` tag to import `index.js` and reload the page, showing that the file runs. Talk about the difference between loading js at the beginning versus end of a document*






## Intro to the DOM
**Goals:
- understand what the DOM is
- understand the different parts of the DOM
- what is a DOM tree? what is a DOM node?**

### What is the DOM?
- the DOM is built by the browser and gives us a way to interact with the document
- it's a data structure - which means its an organized group of data
- the "structure" is what we call a `tree` structure - a document tree

### What is a document tree?
- we've seen a tree structure before: the file system we navigate with our terminal
- we have some starting point, which we call the `root` and then we have some number of branches and subbranches and sub-subbranches that we can navigate through to get to a certain point
- the DOM works like this, but as a JS object

**draw a document tree on the board, referring to the html file**
- We have an `html` element, within which we have `head` and `body` elements, within each of these, we have further nested elements
- this is how trees work
- this is important terminology for us to be familiar with
- when we're working with the DOM, we typically mean we're working with DOM nodes (i.e. nodes of the DOM tree)





## Working with the DOM
**Goals:
- how do we use JS to work with the DOM?
- what can we do with the DOM?**

So we now know how to get javascript to run with our documents, either with inline js or by referencing an external JS file.

What happens when we import a file? It runs (i.e. when we used `require`)

Same happens with JS being imported through a `script` tag

### Document Methods
- `document.getElementById('myID')`
- `document.getElementsByTagName('div')`
- `document.getElementsByClassName('my-class')`
- `document.querySelector('#myID')`
- `document.querySelector('.my-class')`
- `document.querySelectorAll('.my-class')`
- `document.querySelectorAll('div')`





### Getting data from the DOM
**Goals:
- understand  and use the methods for getting data from the DOM
- how to use selectors
- understand how to work with data that we get back from the DOM**

- our `document` object has a set of methods that we can use to get information from our page
- based on how we select html elements using CSS
- two types of methods that we can use - the original API and the newer API

#### Original methods
- `document.getElementById('myID')`
- `document.getElementsByTagName('div')`
- `document.getElementsByClassName('my-class')`

- all of these are methods on the document object
- they all start with `getElement` or `getElements`
- the plurality determines whether or not we'll get one or an array of elements back
- we have to pass in a `selector` - a reference to what we want from within the DOM
  - also use selectors in CSS to target and style html elements
  - can be thought of as a reference to an element
  - tag, class, id, name

#### Newer methods
- `document.querySelector('#myID')`
- `document.querySelector('.my-class')`
- `document.querySelectorAll('.my-class')`
- `document.querySelectorAll('div')`

- the `querySelector` set of methods is newer (may work inconsistently with older browsers) and also has some key differences
- the `getElement` and `getElements` methods are methods of the document object, but not methods of the child nodes of the object, while the `querySelector` methods are

*Pull open a document and see what it looks like by getting a p by id, then trying to get an a by id from within that p*

**Probably ready for a break right about now**






### Setting data in the DOM
**Goals:
- understand and use the methods for inserting data into the DOM
- creating elements in JS
- inserting those elements with JS
- changing elements with JS**

We've talked now about how to get stuff from the DOM, next we're going to talk about how to work with that data once we've retrieved it and then how to put it back on to the page. For now we're somewhat limited because we haven't talked about events (which is what most of our next class will be on). Events let us define functions and call them when a certain browser event happens, like when someone clicks on a link.

- get an element from the DOM
- review what methods and properties it has
- how do we get the text of the element as a string?
- how can we manipulate the style of an element?



### Exercises
Build a Table of contents


## jQuery
**Goals:
- discuss the pros and cons of using jQuery
- review a little bit about the history of jQuery and why it's so big
- comment the drawbacks of jQuery
- go over jQuery's syntax
- compare native JS selection and editing methods with using jQuery
- talk about some of jQuery's methods**
