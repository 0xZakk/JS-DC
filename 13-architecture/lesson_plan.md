# MVC Architecture


## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## MVC
  - start of talking about MVC today
  - first of two application architecture patterns we'll talk about in this class

## Introduction to MVC
  - stands for __Model - View - Controller__
  - a common way of organizing applications so they're easy to build and maintain
  - application architecture pattern, two parts:
    1. a way of organizing code in our applications
    2. a way of thinking about our applications as we're building them
  - popularized by Ruby on Rails
    - ideas have been apart of application development for a long time
    - rails is an opinionated MVC framework
  - separation of concerns
    - we want to divide the different parts of a feature in a way that is logical
    - model - where we describe our data
    - view - where we display our data
    - controller - where we control what happens next in our application

The MVC pattern divides each resource of our application in to of three parts:

__The Model:__
The model is where we define the data of our application. The technical term is "things" and each "thing" within our application will have a model.

So if we're building an admissions application for a school, we'd have a model for student, advisor, individual applications, etc.

Each "thing" within our application gets a model

We've worked with models before:
  - when we worked with Mongoose/Mongo - it's how we defined our data

The concept of a Model is closely related to that of a Class. A model will describe our data, typically interact with the database, and typically data that our users will interact with. So, Spotify has a model for a song, an album, an artist. They'll have lots of other classes though.


__The View:__
The view is what the user sees.

In our case, this is the html and css that get's rendered to the screen.

Each Model can have a couple of different views, in MVC there are some conventions for the kinds of views we'll use:
  - a list/index view where we see every instance of that model
  - a show view where we see a single instance in more detail
  - an edit view
  - a new view

Together, all the views in our application will comprise the user interface of our application.



__The Controller:__
The controller is where we knit our models and views together.

This is where our business logic will live and where we'll choreograph our different views together.



__In Sum__, We've sort of talked about this stuff - just not necessarily in this way. Did we build models for things (like cards and decks)? Did we write code that organized and made those models work together (like in a game)? Did we build out a user interface for people to see what was happening in our application and interact with it? Those are models, views and controllers!

Similarly, I think we'll be able to see the benefit of having a strict structure on where we put stuff. When people were doing the lab, were they often wondering where to put something, where to write some logic? MVC solves that to a large degree.
