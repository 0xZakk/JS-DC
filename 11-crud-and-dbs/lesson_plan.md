# CRUD and Databases

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Web Application Architecture (Review)
1. What are the parts of a Full Stack application? What sorts of tasks does each part perform and how do they relate to each other?
  - Client and Server (Front end and Back end)
  - The client is the part of the application the user sees and interacts with
  - The server is where most of our business logic will be and where we'll work with databases

2. What are the parts of an HTTP request and response? What is important about each part?
  - Request:
    - URL (universal resource locator), address of a resource on the internet
    - method, Get, Post, Put and Delete - the action we want to perform with our request
    - header, meta data about our request
    - body, data we're sending to the server
  - Response:
    - status code, code explaining how the server responded
    - header, meta data about our response
    - body, the body of our response( HTML, CSS, JS, JSON )

3. Describe (generally) the steps involved in setting up a basic web application using `express`.
  - run `npm init` and download `express` and any other packages we need (i.e. nodemon)
  - require `express` and setup our app
  - configure at least a root route listening for `/`
  - have express listen on a port
  - run our express server

## Homework Review
__Goal: walk through how to build a simple app using express and handlebars use the pokedex from Pokemon as an example. Source code for the pokdex can be found in the solution subdirectory for the previous class__

## Introduction to Databases
__Goals: What do we use databases for?__

After today, we'll be one step closer to building out just about any application we can think of.

We're adding a really crucial component today, which is __persistence__: a way of keeping our data, saving it so our users can come back to it later. Think back on our to do list and what happened when we refreshed the page (and all our to dos disappeared) - we can't have that!

Almost every application you can think of uses a database in some way.  

### History
__Goal: provide a brief history of databases__
- one of the first things databases were used for
- computers would take in punch cards and punch holes in to them to represent data, like census data
- these punch cards would then be indexed and stored in lockers where they could be retrieved later and updated or deleted

1960s:
  - the first Database Management System comes out
  - uses a model of linked lists, sort of like an array
  - every record in the database has a unique id
  - you can find records using one of three methods:
    (1) a record's primary key
    (2) navigating relationships between records
    (3) scanning all records sequentially

1970s:
  - relational databse is introduced
  - instead of storing records in a free-form linked list, a relational database stores data in tables
  - each type of data or entity gets its own table
  - takes off and becomes really popular - in the 70s we have SQL

SQL:
  - Structured Query Language
  - Management System or Query Language for relational databases
  - specifically built for specifying and retrieving combinations of rows and columns from a relational database

ORM:
  - SQL keeps going strong starting in the 70s and through on into the 90s and early 00s
  - in the 90s, there is a movement to make data more object oriented
  - affects how data is stored in the DB and how we work with it outside of the DB, and trying to bring these in to alignment
  - it was difficult/inconvenient to translate from a programm object (or model) to database tables

NoSQL:
  - rejects the strict relational structuring of data
  - avoid having to research what data conceivably needs to be tracked

## Working with Databases
If we think about stored data on a really general level there are really only four things we can do with it:
- we can save it, so create a record in a database
- we can read that record from the database
- we can update that record
- we can delete that record
- these four methods together form `CRUD`

## CRUD
Create - Read - Update - Delete

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

## Downloading MongoDB
__Goal: give students 30 minutes or so to get mongo installed__
- make sure everyone follows both the installation and setup instructions
- if students run in to problems, you may have to change the permissions of `/data/db` so that Mongo can read/write to that directory
- if anyone has a lot of trouble or can't get mongo installed for some reason, have them use vagrant-mongobox as a last resort:
  - https://github.com/bobthecow/vagrant-mongobox
  - http://justinhileman.info/article/mongodb-virtual-machine/

## Guestbook
__Goal: (1) review setting up a basic express application, (2) how to submit forms / make post requests and capture that request on the server, and (3) how to set up a database (using mongoose) and save records to a database__

Outline steps going forward:
1. Set up a basic express app, with a single route
2. Define our data
3. Setup and connect `mongoose`
4. Create some data and show it in our view
5. Implement a form so users can submit their entries to our guestbook

- `npm install --save express express-handlebars body-parser mongoose`
- get `nodemon` too

Review: get a quick hello world style application up and running first
  - require express and hbs, set up the `/` route and set up to listen on port 3000 and create our first view

Next thing we need to create is something to represent our Entries. Our guest book is going to have a bunch of entries that users submit, how will we know what a valid entry is? How will we know what properties and methods an entry has? Refer back to MVC lesson
- make a `models` folder and an `entry.js` file
- require `mongoose` and `mongoose.Schema` __Introduce Schemas__
- create our schema
- attach our schema and export it

## To Do App
__Goal: have students build their own simple express app with a databse. If there's time after the Guestbook exercise, this can be started in class, otherwise it becomes homework.__
