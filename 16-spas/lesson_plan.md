# Single Page applications

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Final Project
Start with two 20 minute exercises:
  1. Wireframing
  2. User Journeys

### User Experience Exercise
__Quick UX/UI exercise to draw and iterate on final project__
We're going to start class with two quick User Experience exercises that will help you think more holistically about your application.

Each exercise we do is aimed at making the idea in your mind a little bit more clear so that when you go to start building, you have a plan of what it is you're building - what the finished product will be.

Today we're going to be doing _wireframing_ and _user journeys_.

__wireframing:__ sketch and outline the views of our applications, without necessarily thinking about styling yet

__user journeys:__ creating a map of how a user will navigate through and around your application

These two exercises are going to help us achieve two things:
  1. understanding what views we'll have in our application and help us understand how each view is going to be structured and
  2. understand the architecture of our application

#### Wireframing
Wireframing is the process of quickly sketching out the views of our applications

The purpose is to quickly test out different ideas. Nothing we draw is final, we can throw anything away and start over. The goal is to come up with a layout and organization for the content of a specific view that will work the best.

To do this we need to think about what each view is going to show and so what kind of information we're going to have on it.

The best way to do this is to start broad and work our way down

__See it in action:__
- wireframe a view of your application
- probably the farmer's market detail view
- things to consider: what information do I want to show on this page:
  - image, title, location, link to driving directions?

__Class Activity:__
- now everyone pick one potential view from their application and wireframe it
- think about what information you might have on your view first
- come up with three different ways of displaying that information

#### User Journeys
User Journey mapping the processes of mapping the flow of users through an application. This typically has a very specific goal, like getting them to sign up or become a member of your application or to get them to purchase your product.

At their softer, more UX-ey level, they get in to a lot about who your actual users are by creating user personas. They also help you identify parts of your application that could be bottlenecks.

At their more technical level, they'll basically translate into the routes and views of your application and how they all relate to each other.

__See it in action:__
- map out all the views of your application and how they'll relate to each other
- start with the home page, search for farmer's markets by location, then open the view for a specific farmers markets

__Class Activity:__
- Everyone map out the navigation through their application


## Single Page Applications
An application delivered to the browser that doesn't reload the page during use.

We can think of a fat client that's loaded from a web server.

### Architecture
Weight:
  - we started with just the client
  - we then worked our way backwards, adding a server and then a database
  - then we built full stack applications that used all three of these, but the majority of our logic lived in the middle ( in the server )
  - that's how a lot of applications work today
  - SPAs fatten up or push a lot of logic to the client here

What kind of logic might we want to push to the client?
  - views/rendering
  - simple calculations and data manipulation

### History
- have become industry standard when building Apps
- to the point that users will find it frustrating to wait for a page refresh
- for a long time building a single page app required not only a lot of work but what you'd end up with wasn't great
- the first mainstream single page app was gmail
- driven by the desire to provide a really fluid and interactive user experience
