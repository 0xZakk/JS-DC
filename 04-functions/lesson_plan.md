# Functions

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


## Review: Control Flow
Have students break out into four groups of 3-4 students. Each group is assigned a `warmup.js` prompt and has to work together to solve it. The first team finished wins. After each team has finished, someone from each team should present both their prompt and their team's solution as well as how they approached solving it.


## Introduction to Functions ( 5 minutes )
*Goal is to introduce students to the concept of functions and at a high level why they're important, before going into the syntax and use of functions*

Looking back,
- we've learnt the basic data types in JavaScripts (numbers, booleans, strings) and we've learnt how to store them in variables
- so, we've learnt about data and how to store it
- last class, we learnt about control flow, which is how we could shape and how it reacted to what our data was.
- if a number (i.e. some data stored in a variable) is greater than 5, then do this, otherwise do that.
- so we've learnt how to store data and we've learnt how to respond to the value of our data, but we've only sort of covered how to actually manipulate our data
- we have talked about incrementing or multiplying our data, especially last class as part of learning control flow
- but we've really only touched the surface

We've got our data, we can respond to it, now we need actions that we can run based on our conditions - actions that affect our data in meaningful ways, triggering new responses and creating more actions.

That's one thing that functions give us.

It's code that does something

The other thing we need, that functions conveniently give us, is we need a way to encapsulate our code so that we can reuse it
- functions use this idea of blocks - just like loops do
- however, in a function blocks have something called scope, which we'll see almost makes them like subprograms without our program
- once we've declared our function and defined what actions it will perform for us, we can invoke it over and over again, on different data and it'll perform the same action as many times as we need it to


## Writing a function ( 10 minutes )
*The goal of this section is to introduce how to actually write functions*

Lets go ahead and write our first function:
```
function myFunction() {
  console.log( 'This is my first function' )
}
```

- syntax is starting to look familiar - compare to `if` statements and `for` loops and variable declaration
- this is the first step in creating and using a function - this is called declaring the function or function declaration
- the second step is called function invocation or invoking the function

```
myFunction()
```
- so now we've gone through the two steps of using functions: declaration and invocation

*Exercise 01 ( 10 minutes )*

```
function helloWorld() {
  console.log( 'Hello world' )
}
```


## Parameters ( 10 minutes )
*Here, we want to take our functions one step further by adding parameters*
- so we can now declare and invoke functions, but they're kind of limited in what they can do for us
- think about this add and subtract one example: if we're building a calculator, are we going to want to write one function for every possible action that we could take, adding 1, adding 2, adding 3, etc?
- so we can see the reusability in that we can encapsulate some code in a function and call it as many times as we want
- we need reusability in that our functions become actions that can be performed regardless of the values of our data, so become one level higher
- we call these `parameters`

```
function sayThanks( name ) {
  console.log( 'Thanks ' + name )
}

sayThanks( 'Obama' )
// => 'Thanks Obama'
```

*Refer to `functions.js`*

```
var number = 0;
function addOneToNumber() {
  number += 1
}

function addTwoToNumber() {
  number += 2
}
```

```
function addOne( number ) {
  return number + 1
}
```

*Exercise 02 ( 10 minutes )*


## Returning values ( 10 minutes )
*Point of this section is to understand returning a value from a function and the difference between ouput and side effects*
- one thing missing about using functions that we need
- what if we don't always want to `console.log` the product of our work?
- if we step back and think about if, our function is performing an action. We're giving our function some input in the form of parameters. How do we get our output back?
- Two ways: side effects and output

Side effects:
- we've already seen side effects, this is where running our function affects something by nature of the function running

```
var number = 0

function addNumber( adder ) {
  number += adder;
}

addNumber( 5 )
// => number = 5;
```

Output:
- We have not seen output - this is where we explicitly return the results of our function back after invoking it
- this completes the circle for us - or paints the whole picture: we have data, we perform an action on that data by calling a function, then we get a result back from the function that we can use

```
function addNumbers( num1, num2 ) {
  return num1 + num2
}

var number = addNumbers( 5, 10 )
console.log( number ) // => 15
```


## Function Scope  ( 15 minutes )
*Introduce the concept of scope, how it works and why it's useful*
- scope determines when and where variables are considered defined
- we've already seen one examples of scope when we talked about parameters


Scope Example 1
```
var a = 1

function addThree( x ) {
  return x + 3
}

addThree( a )
```
- do we think `x` exists outside of this function?

Scope Example 2:
```
function myFunction() {
  var a = 1
}

console.log( a ) // => error
```
- do we expect this `console.log` to work on `a`?
- variables declared within a function are only available within that function

Scope Example 3:
```
var a = 1

function myFunction() {
  console.log( a )
}
```
- do we expect this `console.log` to work on `a`?
- hierarchy of scopes
- global scope vs function scope

Scope Example 4:
```
var a = 1;
function firstFunction() {
  // do we expect this to work?
  console.log( a )

  var b = 2

  function internalFunction() {
    var c = 3

    // do we expect this to work?
    console.log( a )
    console.log( b )
    console.log( c )
  }

  // do we expect this to work?
  console.log( a )
  console.log( b )
  console.log( c )
}
// do we expect this to work?
console.log( a )
console.log( b )
console.log( c )

```

## Using Functions
In javascript, functions are instances of the Functions object - a native javascript object to describe functions. That's right, functions are objects. If you run `typeof v` where v is a function, you'll get `function` back, which is helpful, but what it means for us is that functions are another datatype and can be used as one.

That means we can store functions in a variable - or in an array, or in an object. Anywhere we can use a variable

- Alias a function by creating a variable that points to it.
- Put functions in an array (possibly mixed with other types of data).
- Use functions as properties of an object (see Chapter 9).
- Pass a function into a function.
- Return a function from a function.
- Return a function from a function that itself takes a function as an argument.


## Functional Programming
- now that we've covered declaring functions and how to use them, it's time to take a step back and think at a higher level
-  here, we're going to think about functions as functions, in the mathematical sense
- functional programming is a programming paradigm that is derived from mathematics
- entire languages that are purely/solely functional, like haskell, and supersets of javascript that enforce functional programming, like elm.

### Pure Functions
Two criteria for pure functions:
1. always return the same output for the same set of inputs
2. don't have any side effects (invoking our function wont have any affect on the state of our program elsewhere)

- this is a paradigm of programming that many people like to follow, one of it's biggest use cases is that it will often lead to fewer bugs in your programs

### Making a function pure
We have the following function for determining if it is currently a leap year:
```
function isCurrentYearLeapYear() {

   const year = new Date().getFullYear()

   if(year % 4 !== 0) {
     return false
   } else if(year % 100 != 0) {
     return true
   } else if(year % 400 != 0) {
     return false
   } else {
     return true
   }

}
```

We can make this function pure, by not having it tied to the current year:

```
function isCurrentYearLeapYear( year ) {

   if(year % 4 !== 0) {
     return false
   } else if(year % 100 != 0) {
     return true
   } else if(year % 400 != 0) {
     return false
   } else {
     return true
   }

}
```

### Why use pure functions
- makes programming more like math?
- because pure functions make your code easier to test, easier to understand, and more portable.
- functions that return different values under different circumstances or rely on outside data or create side effects are tied to their context
- if I spend all this time writing a function that is tied to it's context and I want to use it for a very slightly different task - will it work?


## Exercise 4 Solution

Part 1:
```
function createDeck( suits, ranks ) {
  // Check to make sure both parameters are arrays
  if (
    !(typeof suits === 'object') ||
    !(suits.length > 1) ||
    !(typeof ranks === 'object') ||
    !(ranks.length > 1)
  ) {
    return console.log('broken')
  }

  var finalArray = []

  for (var i = 0; i < suits.length; i++) {

    for (var j = 0; j < ranks.length; j++) {
      finalArray.push( ranks[ j ] + ' of ' + suits[ i ] )
    }

  }

  return finalArray;
}

var deckOfCards = createDeck( suits, ranks )
```

Part 2:
```
function getRandomCard() {
  // random number between 0 and 51
  var randomIndex = Math.floor( Math.random() * 51 )

  // get card at index of the random number we created above
  return deckOfCards[ randomIndex ]
}

myRandomCard = getRandomCard()
```

Part 3:
```
function dealHand( num ) {
  numOfCards = num || 1
  var handOfCards

  if ( numOfCards === 1 ) {

    handOfCards = getRandomCard()

  } else {

    handOfCards = []

    for (var i = 0; i < numOfCards; i++) {
      handOfCards.push( getRandomCard() )
    }

  }

  return handOfCards;
}
```

Part 4:
```
var playerOneCards = dealHand( 7 )
var playerTwoCards = dealHand( 7 )
```

Part 5:
```
function showHand( cardsArray ) {
  if ( !cardsArray ) return console.log( 'no hand passed in as param' )

  var showOfHand = 'This player has the following cards: '

  for (var i = 0; i < cardsArray.length; i++) {
    showOfHand += ' ' + cardsArray[i] + ','
  }

  console.log( showOfHand )
}

showHand()
showHand( playerOneCards )
```
