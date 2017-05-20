# Objects

## Class Structure
- Welcome to Class
- Review previous class
- Go over Learning Objectives
- Deliver Lesson
  - Introduce concept
  - Give exercise
  - Repeat
- Go over Learning Objectives
- Closing Questions / Tying up loose ends
- Exit Tickets

## Review: Functions

## Introduction to Objects
*The goal of this section is to introduce students to the basics of JavaScript Objects: what they are and why and how we use them*

Looking back,
- Start - as we have the last two classes - by thinking about what we've learnt from the previous couple of lessons
- We've covered the basic data types in JavaScript, we've covered arrays and we've covered functions.
- last class was about completing a circle, that started 3 classes ago, when we learned basic data types
- the circle starts with basic data types, creating and working with data, saving it as variables
- the second part of this circle was learning how to write programs that reacted to this data - control flow
  - if something is true or if some condition is met, do this, otherwise do that
  - while some condition is true, do this
- the final part of this circle was writing code that did stuff - performed actions
- so completing the circle, we set some data, we responded it to it conditionally in some way and then called an action that had the power to create new data or change our existing data and so we could start the circle over again
- we know today's lesson is about objects, so where do they fit in?
- today we're going to learn that objects are at the center of the circle
  - objects are a kind of like a data type, we can save them to variables and we'll change them sort of like we did with data types
  - they can also contain or house not just data types, but arrays and functions and even other objects in a really powerful way, that lets us create new, complex data types that model some problem in our application
  - that's what I mean when I say objects are at the center of the circle

## Object Syntax
*This section should thoroughly cover the object syntax*
We're going to start with a quick "anatomy" lesson, if you will

The anatomy of an object:
```
var Person = {
  'first name': 'Zakk',
  lastName: 'Fleischmann',
  favoriteColors: ['green', 'blue'],
  height: {
    feet: 6,
    inches: 4
  },
  isShort: false,
  sayHello: function( name ) {
    console.log( 'Hello, ' + (name || 'you') + '! Hope you are well!' )
  }
}
```

- here we have an object called `Person` and there are a couple of things I want to talk about
  - first is the anatomy of this object (i.e. what the different parts are called)
  - second is what we're doing with this object, we're modeling a real world thing

The Anatomy:
- We open an object with curly braces - this is one way we can create a new object, it's probably the most succinct and the one you'll use the most
- next, within these curly braces, we have a list of comma separated properties
- each property is made up of a key and a value, into what we call key/value pairs
  - each key maps to a value, otherwise we'd have a syntax error
- we close with what we call a method
- as you can see from this object, we can put anything into an object: a string, an array, another object, a function  


## Working with Objects
*Now that students know how to create objects, this section should introduce them to the concepts of working with objects: getting/setting properties in an object and creating object methods*
- Now we have an object - we've declared it, we've given it some data and some functionality, now lets go ahead and work with it
- There are a couple aspects of working with objects, getting and setting data and calling the methods we declared as part of our objects

Getting data:
- Dot notation
`myObject.myProperty`
- Bracket notation
`myObject['myProperty']`

We can use both to get and set properties and methods of our object


## JSON
*Sidebar and talk about JSON*
- Quick sidebar to talk about JSON
- JSON: JavaScript Object Notation
- Proposed by someone named Douglas Crockford
- it's a lightweight data format, 'data format' in the way that SQL is
  - a way for us to organize data into a database and work with it

## Bringing it all together
*Now, we want to bring it all together: returning objects from a function, using different datatypes within an object, working with multiple objects, creating multiple objects*

Modeling:
- Doing two things here, the first is creating an object and the second is I'm modeling a real world thing, a person
- I could have done this with a car or a house or an airplane
- This is really why objects are powerful and useful for us and this is the basis of Object Oriented Programming
  - on some level they give us a way to organize data and functions that are all related to each other, but we can do that in a way that models some real world thing that we're trying to emulate in our program
  - What are some common things we may want to model in an application?
    - a user, a class or lesson, etc


- lets create an object that models a car
- we have all this to create a car, but what we don't have is a way - based on this - to take this one car and create multiple versions of this object to represent different types of cars
- lets take a step back - what have we learned that lets us encapsulate and run code and return a result from it when we need to? => functions!
- so instead of making an object called `Car`, lets create a function called `Car` that returns an object
