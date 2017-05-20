# APIs

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

## Sections to cover:
1. AJAX
- Understand the benefits of AJAX
- Understand the technical aspects of AJAX
- Where should Ajax be used?

2. APIs
- Understand the general purpose of APIs
- Work with a 3rd party API
- Build our own API
- Work with the API we built

## Introduction to class
__Goal: We will be reviewing HTTP, CRUD, and Servers before learning AJAX and how to work with and build APIs ___

## HTTP/CRUD Review (10 min)

### HTTP Request: Method
Meta data about our request
​- "Cookie"​ - a list of cookies that have been set on the browser
​- "Auth"​ - encrypted auth information
​- "Content-type"​ - tells server what kind of content is inside the request
- ### HTTP Request: Header

### HTTP Request: Body
Optional extra text data we can send to the server. Especially useful for ​PUT​ and ​POST​ requests.

Body data is typically in the form of JSON (JavaScript Object Notation) or Form Data.

### HTTP: Response
When a server receives a request, it processes that request and then sends a response to the client.

If the request is an invoice, a response is the payment being sent back.

### HTTP: Response: Status Code
Every HTTP Response has a status code that represents whether or not the request was successfully fulfilled.

Have students name off some status codes

### HTTP: Response: Header
Just like the request, a response can also have headers describing metadata.

### HTTP: Response: Body
The body of a response can contain:


## Review the CRUD and the structure of a Server (10 min)

### Create
- `save` method
- going to take an object representing what we want to save, and create a record for it in the database

### Read
- `find` and `findOne` methods
- going to take a field (like the id or name) and return either one or all records that match that query

### Update
- `save` method
- get a record from the database, change some values, then save it again

### Delete
- `remove` method
- find a aprticular record and remove it from the database

### Key Terms
relational database: | Data stored in tables and rows |
non-relational database (NoSQL): | Data in unstructured collections |
SQL: | Structured Query Language |
ORM: | Object-Relational Mapping |

## Warmup (30 min)

## Break

## Introduce AJAX  (20 min)
__Goals:__
- Understand what AJAX is
- Understand when, where and why AJAX is used
- Understand how AJAX is relevant when working with APIs

## The History of Ajax:

- AJAX stands for Asynchronous JavaScript and XML
- It is the use of the XMLHttpRequest object to communicate with server-side scripts.
  - What is an XMLHttpRequest object?
    - API that provides client functionality for transferring data between a client and a server
    - It provides an easy way to retrieve data from a URL without having to do a full page refresh
    - This enables a Web page to update just a part of the page without disrupting what the user is doing
    - XMLHttpRequest was originally designed by Microsoft and adopted by Mozilla, Apple, and Google
- It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files
- The two major features of AJAX allow you to do the following:
  - 1. Make requests to the server without reloading the page
  - 2. Resolves and work with data from the server


- Ajax is not a programming language or a tool, but a concept.
- Ajax is a client-side script that communicates to and from a server/database without the need for a postback or a complete page refresh


## There are 4 main benefits of using AJAX:
  1. Callbacks:
    - Ajax is used to perform a callback, making a quick round trip to and from the server to retrieve and/or save data without posing the entire page back to the server
    - By not performing a full postback and sending all form data to the server,
    network utilization is minimized and quicker operations occur
    - This improves network performance, by using callbacks the server is to required to process all form elements
    - By sending only the necessary data, there is limited processing on the server

  2. Making Asynchronous Calls
    - ASK STUDENTS: This allows the client browser to avoid waiting for all data to arrive before allowing the user to act once more
  3. User-Friendly
    - Because a page postback is being eliminated, Ajax enabled applications will always be more responsive, faster and more User-Friendly
  4. Increase Speed
    - Example: The movie rating feature on Netflix:
      - The user rates a movie, the rating is sent to the database and the application doesn't stop it's functioning to wait for a response or a reload


## AJAX and how it relates to XML and JSON:
  - JavaScript is the client-side programming language and XML is a markup language to define data.
  - JSON is another markup language to define data.
  - JSON (JavaScript Object Notation) is much easier to use with JavaScript than XML. When it comes to Ajax and JavaScript, JSON Web Services are replacing XML Web Services

## Where should Ajax be used?
  - Ajax should be used anywhere in a web application where small amounts of information could be saved or retrieved from the server without sending back entire pages
    - ex: Data validation on save actions
    - ex: Change the values in a drop down list-box based on other inputs,
      such as state and college list boxes
        - When the user selects the state- the college list will repopulate with only that states colleges and universities
        - Other features include text hints and autocomplete text boxes.
        - The client types in a couple of letters and a list of all values that start with those letters appear below.
        - A callback is made to a web service that will retrieve all values that begin with these characters.

## Technical aspects of Ajax
  - Ajax callbacks can be done by instantiating an XmlHttpRequest object in the client-side JavaScript
  - The XmlHttpRequest object can be used to directly call server-side objects like pages and web services
  - These pages will either save and/or return data

## BREAK (10 Min)

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
