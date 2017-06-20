# Application Architecture

## Learning Objectives
- Understand each part of the MVC architecture
- Use MVC to organize an application

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Mid-course Survey Results

Agenda:
1. Key findings
2. Next steps

### Key Findings
1. Pace of the class
  - in a typically class, we expect that 20% of the students will feel that the class is too slow, 20% will feel that the
  class is too fast and the remaining 60% will feel like it is just right
  - for the two more advanced part-time classes, Intro to JS and Intro to Data Science, we expect this to be more skewed
  towards the two ends of the spectrum
  - that makes managing this class more difficult
    - more students wished we moved through the material more quickly, while more wished we could review the material we've
    already covered
  - two things to note:
    - in either case, the pace of this class isn't going to change. So, in either case, you should reach out to us. We can
    assign more bonus work or give you ideas for more in depth topics for you to review if you feel the pace is too slow; if
    the pace is too fast for you, we can provide additional resources, go over things again, or answer any questions you
    might have.
    - also, in either case, there comes a point in this class where everyone struggles. Maybe for you it was databases,
    maybe it happened sooner but learning to code is inherently challenging for a number of reasons, so everyone reaches a
    point in this class where they struggle with the material. When this happens, please reach out to us for help.

2. Availability of instructors
  - Reiterate again that Christine and I will work with you and your schedules so that you feel like you're getting the help
  you need.
  - If you can't make office hours, reach out to us to set up a time to talk that is convenient
  - Reach out to us over slack and we can answer questions asynchronously
  - I don't want to see another exit ticket where a student says they wish office hours were at a different time
  - We're here for you, we just don't know your schedule

3. Feedback
  - last thing I want to say is thank you
  - I've taught this class a few times now and never have I had a class that so regularly gives us such detailed feedback on
  what goes well and what could be improved; similarly, I've never had a class where students help other students so much

### Next Steps
- we're going to keep doing the key takeaways, many have said that they find those helpful
- implement check-ins after lessons, one of us will reach out to you after a lesson if you note in the exit tickets that you
struggled with it
- try something that has been successful with the Data Science part time class, this week you can schedule a 15 minute block
of time during office hours. You can come in to Peet's or we can do it over google hang out. For that time, you'll have my
undivided attention to answer any questions you have or to go over any material from class.
- implement a syllabus change

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
