# Lab 01

## Class Structure
- Welcome to Class
- Review previous class
- Introduce both mini-lessons
- Work on the assigned Lab
- Closing Questions / Tying up loose ends
- Exit Tickets


## NPM
*Introduce students to node package manager and why we use third party packages*
- Npm is a command line application that helps us manage out project dependencies
- A dependency is any third party package that our program or application needs in order to run
- We use third party packages so that we don't have to write all that code ourselves - just the code that's important for us.

### Using NPM

`NPM` is a command line tool that helps us manage *dependencies* in our project. A dependency is any third party package that we rely on in building our application.

#### 1. Initialize a project
We initialize a project with npm by using the following command:
```
npm init
```

#### 2. Add Dependencies
We can then use npm through the command line to add and remove dependencies.

We add a package like this:
```
npm install --save some_third_party_package
```

We can remove that package if we don't need it any more like this:
```
npm uninstall --save some_third_party_package
```

Npm records the results of all of these actions in a file called `package.json`.

## Exercise 1
- initialize a project with npm
- install `prompt` using npm
- where does NPM install this library?
- uninstall `prompt`

## Architecting a program
*The goal of this mini-lesson is to introduce students to the idea of breaking their program out into multiple files and how to do so*
- for this one I want to dive right into the exercise and use the exercise to teach you about how we can break our program up into multiple files.
- start by creating four javascript files: `index.js`, `one.js`, `two.js`, and `three.js`
-

In `one.js`, write a function called `one` that `console.logs` the number `1` whenever it is called.

Back in `index.js`, import `one.js` using `require` and try to run the `one` function. What happens?

Modify your `one.js` so that it looks like this:

```
module.exports = function one() {
  return console.log( 1 )
}
```

`module` is an object associated with every javascript file that holds some cool and important information about the current file. Each `module` object has an `exports` subobject. This `exports` subobject is where we can put any data or functionality that we want to export from the current `module`.

Therefore, anything we put in the `module.exports` object, we can import into another file using `require`

Try these out:
- `console.log` `module` and see what you get
- `console.log` `module.exports`
- if `module.exports` is just an object, can we add properties to it? Why not?

In `two.js`, lets try adding our functions to an object and making them methods and then exporting that.

```var toExport = {}

toExport.one = function() {
  console.log(1)
}

toExport["two"] = function() {
  console.log(2)
}

module.exports = toExport
```

But if `module.exports` is an object, do we need to create this other object and then do this assignment in order to export these functions?

In `three.js` lets declare three methods directly on the `module.exports` object.

## Lab Overview
The goal of today's lab is to build out a working prototype in the command line of the card game `War`.

Explain the rules of War

The rules of war are pretty simple:
- A deck of cards is shuffled and divided evenly between two players
- Each player draws the first card in their deck and puts it down
- The player with the higher scoring card wins the round and collects both cards, putting them at the bottom of their deck
- Gameplay continues with each player drawing a card and the winner collecting both cards and adding them to their hand, until a player has no more cards left.
- If the players draw cards that match, they keep drawing another card each until someone draws a higher valued card
  - that player then adds all of the cards to their hand
