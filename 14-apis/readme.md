# APIs

## Learning Objectives
- Describe what an API is and how to use it
- Understand how to work with an API
- Build an API using `Express`

## Class Structure
- Welcome to Class
- Go over Learning Objectives
- Deliver Lesson
  - Introduce concept
  - Give exercise
  - Repeat
- Go over Learning Objectives
- Closing Questions / Tying up loose ends
- Exit Tickets

## APIs
- API: Application Programmable Interface
  - web application that we can interact with programmatically
  - lets us store data in an accessible, script-able way
- to access that data, we use a concept called AJAX
  - way to make requests of a server from the client

## Introduce AJAX  (20 min)
- Ajax is a way for the client to make requests of the server
programmatically and without requiring a page refresh
- makes our application feel faster, only necessary data is
transmitted

## Client Side AJAX
- 2 implementations
  1. `XMLHttpRequest()`
    - older, stable methodology
    - a little cumbersome to work with
  2. `fetch()`
    - newer method
    - much easier/cleaner to work with
- Which should students use?
  - we will be focusing on `XMLHttpRequest()`
  - `fetch()` is not implemented in IE yet

## AJAX Exercise (20 min)
  - In order to make an HTTP request to the server using JavaScript, you need an instance of an XMLHttpRequest
  - Next you need to handle the servers response to your request:
    - Tell the HTTP request object which function will handle processing the response
    - Set the onreadystatechange property of the object to the name of the Javascript function that should be called when the state of the request changes

## The list of the potential readyState values (XMLHTTPRequest.readyState):
  -  0 (uninitialized)
  -  1 (loading)
  -  2 (loaded)
  -  3 (interactive)
  -  4 (complete)

## Server Side AJAX
- to make server site requests, we can use the native `http`
or `https` modules
  - requires an understanding of streaming and piping
  - instead, we're going to use a library that will abstract
  that stuff away for us


## Introduce APIs (10 min)
History of APIs - types of APIs
  - Have everyone install the JSON formatter
  - JSON is very simple to use if correctly structured:
    - One of the resources to validate JSON and check if the syntax is correct is [JSON Viewer](http://codebeautify.org/jsonviewer)
  - When talking about APIs, a lot of the conversation focuses on abstract concepts.
  - Let's start with something physical: the server.
    - A server is nothing more than a big computer.
    - It has all the same parts as the laptop or desktop you use for work, it’s just faster and more powerful.
    - Typically, servers don't have a monitor, keyboard, or mouse, which makes them look unapproachable.
    - The reality is that we connect to them remotely — for example, the way you log into a remote desktop-style — to work on them.
    - Analogy:
      - Solitaire waits for you to click on a card before it does something, a web server is running a program that waits for requests.

## What is an API and Why is it Valuable?
  - Websites are designed to cater to people's strengths.
    - Humans have an incredible ability to take visual information, combine it with our experiences to derive meaning, and then act on that meaning.
    - For example:
      - You look at a form on a website and can intuit that the text field with "Name" written above it means you are supposed to type in the word you use to identify yourself.
    - So what happens when you're faced with a time-intensive task, like copying contact information for a thousand customers from one site to another?
      - You want to delegate this work to a computer so it can be done quickly and accurately.
      - Unfortunately, the characteristics that make websites optimal for humans make them difficult for computers to use. The solution is an API.

    - API stands for Application Programming Interface
    - An API is the tool that makes a website's data digestible for a computer.
    - Through APIs, a computer can view and edit data, just like a person can by loading pages and submitting forms.
    - API calls are really just another term for making _HTTP requests_
    - We are still communicating with URLs but instead of receiving markup, like we do with HTML pages, we receive data
      - It can be returned in a variety of forms: JSON, XML, CSV, and others.

## Create 10 task exercises using the OMDB database (5 mins)
    http://www.omdbapi.com/
    - create searches using the parameters guide on the website
    - have the students try submitting a couple more queries to familiarize with the API.
    - search for their favorite movies, pull in the rotten tomatoes reviews

## API Code along exercise (15 min)
  http://openweathermap.org/api
  Weatherify - have starter code ready to pull
    - Have students walk me through the components that are already in place

## BREAK  (10 min)

## Build your own API using the Pokedex - Exercise 3 (30 min)
  - Use the Pokemon exercise as an API
  - Create your own requests
  - download hbs form helpers :
  - npm install hbs (need to do this to build on top of it)
  - npm install handlebars-form-helpers
  - load in the module and register it:
    var hbs = require('hbs');
    require('handlebars-form-helpers').register(hbs.handlebars);
    You have to register the helpers before you can use them in your templates. The register method expects the Handlebars object to be passed in, and an optional config object, for example:


## Wrap up and review (5 min)  
