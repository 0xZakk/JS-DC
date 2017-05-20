# Express

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Quick note on homework
- didn't want to assign a ton of homework

## Quick note on the Lesson
- What we're going to try today is building out an application

## Web Application Architecture
__Goal: (a) Cover the basic architecture of a full stack application, (b) Understand the difference between the client and the server, (c) understand how the client and the server communicate.__

### Full Stack application
- A full stack application is one where we have a client and a server and logic that exists in both
- The definition of full stack application has gotten  grey over the last couple of years as more and more libraries and patterns are coming out
- At it's core, a full stack app has these two parts and they communicate with each other in response to user input

#### The Client
- we've already worked with the client
- the client refers to the browser, typically
- the part of the application that the user actually sees and interacts with
- the client communicates back to the server, through HTTP

#### The Server
- the server is probably what we actually think of when we think of web application development
- this is where the majority of our logic will probably be and it's where we'll persist data and other related tasks

#### Client and Server Relationship
- There's a spectrum between the two
- Before we had robust and powerful browsers, most
computation and work in our application had to happen on
the server
- this meant most if not all actions on a web
application required navigating to a new page and
hitting the server and the server would return a new
html document to the client
- the only client to speak of was some javascript that
responded to events
- then in the history of JavaScript libraries starting
coming out, starting with backbone and ember, that let
us build a lot of business logic in to the front end
- to the point where now you can construct a robust
applications that is almost entirely a front end
applications

#### Client and Server Review
- The client is the part of the application that we send to the user to run in their browser
- The server is the part of the application that happens on our servers
- another way of referring to these is the front end and the back end
- that sums up our discussion of the relationship between the client and the server
- except that we need to talk about an important aspect of any healthy relationship: communication
_make a joke about getting married ... ?_

#### Communication between the Client and Server
- The client and the server have to communicate in some way
- the client needs to be able to tell the server about it's needs and the server needs to be able to respond with which needs it can meet and which it can't _Sarah and my socks?_

### Hyper Text Transfer Protocol
- like any good communication style, HTTP is structured
- we can be explicit about which requests we can receive and most importantly, which we can respond to
- you've no doubt seen and worked with HTTP requests in your life
- whenever you navigate to a webpage, you're making a http request and when the page loads you've received the HTTP response
- A metaphor that is often used to describe this process is the USPS
  - we send in a request, we get back a response
  - our request is like an invoice - we're asking for something
  - the response the response to the invoice (the payment)

### HTTP Request: URL
- Universal Resource Locator
- continuing with our metaphor of an invoice - the URL represents where we're sending our invoice to - like the address
- the address can have a couple of different parts to it

`http://www.domain.com:1234/path/to/resource?a=b&x=y`

__Draw associations__

Anatomy of a HTTP request (URL):
- protocol: `http:`
- host: `www.domain.com`
- port: `1234` (channel through which we can send and receive communications)
- path: `/path/to/resource`
- query parameters: `?a=b&x=y`

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

Common Status Codes:

- ​2XX​ Success
​ - 200​ OK - the request was processed successfully
- ​3XX​ Redirects - the URL has changed
- ​4XX​ Problem with the request
  - ​400​ Bad Request (generic bad request code)
  - 403 Forbidden
  - ​404​ Not Found (The URL is wrong)
- ​5XX​ Problem with the server
  - ​500​ Generic server error
  - ​503​ Service Unavailable (usually happens when traffic is high)

### HTTP: Response: Header
Just like the request, a response can also have headers describing metadata.

### HTTP: Response: Body
The body of a response can contain:

- HTML if we are requesting a webpage
- CSS if we're requesting linked stylesheets
- JS if we're requesting scripts
- JSON if we're requesting data


Sum Up:
- We're making an HTTP Request, the metaphor for this is sending an invoice
- where we want to send the invoice to is the _URL_
- what we want our invoice to achieve is the _method_ (cover letter for our invoice)
- the supporting information for our invoice is the _header_
- the **SOMETHING** is the _body_


__BREAK__

## Building our First Server
__Goal: (a) introduce the basic structure of a server using Express, (b) talk about each part of a server: the port, the route, the route handler, the request, the response, (c) introduce and talk about parameters__

Going forward, the things to pick up are:
  - how to create a simple express application
  - how to set up a port to listen on
  - what is routing and how to we do it in Express
  - how do we render views in express
  - how can we use parameters in express

- first want to run `npm init`
- then we want to run `npm install --save express`
- then run `npm install --save-dev nodemon`
  - `nodemon` is a utility that we can use when developing applications in node to monitor for changes in our code base and automatically restart our server
- touch `app.js`, this is where we're going to build out our first application
- Our first application:

```
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Example app listening on port 3000!');
});
```

- We're building out our server here, which means we're building out what requests we can respond to and how we can respond to them
- `app.listen`: here we're opening a channel of communications on port 3000, so we can send and receive messages through this port
- `app.get`: here we're saying we can respond to requests to read information
- `/`: this is the route or the address at which we can receive and respond, so a specific request
- `callback`: this function is the handler - the function that runs in response to a request and where we'll send our response from
- how different is this construction from, say, event handlers? What is similar? what is different?
- we call this `app.get` part a route and a route handler. Let's create some more

```
app.get('/about', function( request, response ) {
  response.send( 'My name is Zakk' )
})

app.get('/work', function( request, response ) {
  response.send( 'I work at nclud' )
})
```
- we're going to leave the other methods we introduced until next time when we talk about databases and persistence.

Routing
- we call this process _Routing_: mapping requests to specific handlers by method and address
- that's to say depending on what method we put here and what url we put here, will determine which function will run
- inside express, all of these are being stored somewhere, and when our application received a request, Express compares it against each one of these, in the order that we define them until it gets a match, then it calls this function
  - hey, that's a lot like events!
- we can define a route at the end here that will run for all remaining routes

Views
- How can we configure our Express app to send a full HTML page?
- We know Handlebars, it would be great if we could use that
- run `npm install --save express-handlebars`

- Handlebars isn't by default configured to work with express so someone created this `express-handlebars` library that makes it easy for us to use handlebars in our applications
- before we go any further, lets build out our views:
```
- views /
  - home.handlebars
  - layouts /
    - main.handlebars
```

layout.handlebars:
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Our First Application</title>
</head>
<body>

    {{{body}}}

</body>
</html>
```

home.handlebars
```
<h1>Example App: Home</h1>

```

Quick review - what are we doing here?
We've defined this layout, which we talked about briefly during last class. This body is going to represent whatever

Now we have our templates, we want to configure our server to use them.
  - `var exphbs  = require('express-handlebars')`
  - `app.engine('handlebars', exphbs({defaultLayout: 'main'}))`
  - `app.set('view engine', 'handlebars')`
  - `app.get('/', function( request, response ) {
      response.render('home', { 'title': 'Test' })
     })`

_define and about page then a work page using the same method so that it sinks in_

Parameters
- the next thing we want to talk about before we close this part of the lesson out is parameters
- a parameter is data that we send with the request object, but it's data that is specific to the address
- so it's a way of creating a catch all for for our addresses if we have a bunch that are relatively similar
- to illustrate, lets create an object that will represent some projects that we're working on:
```
var data = {
  'projects': [
    {
      'id': 0,
      'title': 'War - the card game',
      'description': 'I implemented the game of war as a command line applications'
    },
    {
      'id': 1,
      'title': 'Foo the foo foo',
      'description': 'Foo fighters fighting foos'
    },
    {
      'id': 2,
      'title': 'Bar the bar bar',
      'description': 'Bar fighters fighting bars'
    }
  ]
}

```
- then we want to tie that to our projects view:
```
app.get('/projects', function( request, response ) {
  response.render( 'projects', data )
})
```

- then we create our template:
```
<h1>Projects:</h1>

<ul>
  {{#each projects}}
  <li>
    <a href="/projects/{{this.id}}">{{this.title}}</a>
  </li>
  {{/each}}
</ul>
```

Now we need to create a `project.handlebars` view that will take our project

How do params work:
```
app.get('/projects/:id', function( request, response ) {
  var index = parseInt( request.params.id, 10 )
  var project = data.projects[ index ]
  response.render( 'project', project )
})
```


## Building a Pokedex

Goals:
- build out an application that lets us see a list of every pokemon as well as the details for a specific pokemon

Recommendations:
- have code from `your_first_server` handy so that we can refer back to it
- have any notes you took handy so we can refer back to those
