# Control Flow

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

## Introduction to Control Flow
Programming is often described as writing and following a recipe. Recipes are a metaphor that we use to describe what we're doing when we're programing: taking a complex task and breaking it down into small and discrete steps that we can describe to a computer, so that the computer can not only follow those tasks, but do so with incredible speed and precision on a huge quantity of data.

But this metaphor is flawed. It certainly used to be the case that this is what programming consisted of, but not any more. This metaphor breaks when we start talking about accepting user input or responding to changes based on previous calculations. So this metaphor is archaic and not applicable - at least not for us.

We need to write programs that can respond to a set of circumstances. This is called Control Flow.

## What is Control Flow?
"Control Flow" refers to the order in which statements of a program are evaluated or executed. So, to that effect, we've already seen one type of control flow. When we did the distance calculator, we used what's called a linear control flow - we ran the program and ran each line in sequential order until we got to the end of the program: linear control flow. In this case, we're not really doing a whole lot of controlling as much as we are just letting the program run (or flow, if you will). What we're going to learn about today is how we can exercise control over which statements of our programs are run and in which order they run.

### Conditional Flow
The first type or category on control flow we're going to discuss is called conditional execution. In conditional execution, we define something as needing to be true before a block of code will run. We can take it a step further and say that if something is not true, run a separate block of code instead.

#### Linear control flow
We've already seen Linear control flow - it's when we just run a file and do nothing to manipulate which lines of code get run or do not get run under certain circumstances.

*From to `control-flow.js`*
So if I had a file that looked something like this:

```
console.log( 'This' )
console.log( 'is' )
console.log( 'linear' )
console.log( 'control' )
console.log( 'flow' )
console.log( 'in' )
console.log( 'action' )
```

We would expect each line to be `console.log`ed, in order.

#### Conditional Flow
With linear flow as our baseline, we want to first explore conditional flow: running a block of code when a condition is met. We do this with `if` statements.

*Refer to `control-flow.js` throughout this section*

##### `if` statements
If statements will run, if an expression evaluates as true.

```
if ( EXPRESSION ) {
  CODE
}
```

In the above block of code, if EXPRESSION is `true` then CODE will execute. If EXPRESSION is `false`, then we will continue on down the program until we reach the end.

##### `if`/`else` statements
In an if else statement, we can not only run a block of code if our condition is true, but also run a separate block of code if it is false:

```
if ( EXPRESSION ) {
  CODE TO RUN IF TRUE
} else {
  CODE TO RUN IF FALSE
}
```

##### Ternary statements
Ternary statements give us a condensed way of expression an if/else conditional:

```
EXPRESSION ? CODE IF TRUE : CODE IF FALSE;
```

#### Conditionals in Action:
*Assign `01_exercise.js` to do independently, then together as a class*

Version 1:
```
var age = 12
var allowed = false

if ( age >= 18 ) {
  allowed = true
  console.log( "Thank you for smoking." )
}
```

Version 2: (First refactor)
```
var age = 12,
    allowed;

if ( age >= 18 ) {
  allowed = true
  console.log( "Thank you for smoking." )
} else {
  allowed = false
  console.log( "You may have some gum, kid" )
}
```

Version 3: (Second refactor)
```
var age = 12
var allowed = false

if ( age >= 18 ) {
  allowed = true
  console.log( "Thank you for smoking" )
} else if ( age === 17 ) {
  allowed = false
  console.log( "Come back in a few months" )
} else if ( age < 12 ) {
  allowed = false
  console.log( "You may have some gum, kid" )
} else {
  allowed = false
  console.log( "Sorry, bud" )
}
```

Version 4: (Third refactor)
```
var age = 12,
    allowed = ( age > 18 ) ? "yes" : "no";

console.log( allowed );
```

**Recap:**
- What is the overall topic of this class? Control Flow
- What was the first type of control flow that we talked about? The one we used last class? - Linear
- What is Linear control flow? What do we mean by "linear"?
- What was the other type of control flow that we talked about? Conditional
- What do we mean by conditional? - our code will execute if a certain condition is met
- What tool do we have as part of the language to do this? If, If/Else and If/Else If statements

We've talked about linear flow, which runs through our program and executes each line in sequential order. We've just finished going over conditional flow, which will execute a block of code if a certain condition is met. What we're going to talk about next, is how we can execute the same block of code repetitively - over and over - based on a certain condition.

#### Iterative Flow
With Iterative or looping control flow, we want to execute a block of code for as long as a condition is true. As part of this, we'll be updating the data that our condition is based on during the loop.

*Refer back to `control-flow.js` throughout this section*

##### `for` loops
There are a couple of important parts to the `for` loop, which we're going to break down. Overall, the `for` loop looks like this:

```
for ( ITERATOR; CONDITION; INCREMENT ) {
  CODES
}
```

We initialize a `for` loop with the `for` keyword. Then in parenthesis, we provide three pieces of data that will determine the conditions under which our loop will run and eventually break.

We can think of these parts as before, during and after. This first, statement, the `iterator` is called before the loop starts and is where we'll define our counter. The second statement is the condition our loop is based on, so while this condition is true, our loop will run. The final statement, the `increment`, runs after each loop. The code between our brackets here is what will run during each loop.

Lets look at a basic loop:

```
for (var i = 0; i < 5; i++) {
  console.log( i )
}
```

Here, we're declaring a variable `i` which we're setting at 0. Then saying that we want our loop to run for as long as `i` is less than `5`, and we're incrementing the value if `i` with each loop. Within our loop, we're simple `console.log`ing the value of `i`. What we expect is for this to simple `console` the numbers `1` through `5` in order - and that's exactly what this does.

So when might this be helpful? We can modify our basic for loop and use it to iterate over an array and perform some action on each item in the array:

```
var myArray = ['one', 'two', 'three']

for ( var i = 0; i < myArray.length; i++ ) {
  console.log( myArray[ i ] )
}
```

We can modify our `for` loop slightly to make it more succinct when working with arrays specifically by using `for ... in`.

```
for ( VARIABLE in OBJECT ) {
  CODE
}
```


##### `while` loops
`while` loops are very similar to `for` loops - but without the explicit definition and incrementation of our looping conditions. You can see what I mean by looking at a while loop:
```
while( CONDITION ) {
  CODE
}
```

Any `for` loop can be written as a while loop:
```
// while loop
console.log( 'while loop' )
var x = 10;
while ( x >= 0  ) {
  console.log( x )
  x--;
}

// for loop
console.log( 'for loop' )
for ( var i = 10; i > 0; i-- ) {
  console.log( i );
}
```

We can modify our basic `while` loop into what is called a `do while` loop:
```
do {
  CODE
} WHILE ( condition )
```

Note that our code will always run at least once in a `do while` loop.


## Final Exercise
The final exercise can be found in `03_exercise.js`. This is meant to be worked on by students individually at the end of class, then gone over together as a class.

Prompt:

If we list the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all multiples of 3 or 5 below 1000.

Solution 1:
```
var ceiling = 10
var multiples = []
var total = 0

for ( var i = 1; i < ceiling; i++ ) {

  if ( i % 3 === 0 ) {
    total += i
  } else if ( i % 5 === 0 ) {
    total += i
  }

}

console.log( total )
```

Solution 2:
The first solution runs the same block of code under two conditions, we can condense that so it's more succinct:

```
var ceiling = 10
var total = 0

for ( var i = 1; i < ceiling; i++ ) {

  if ( i % 3 === 0 || i % 5 === 0 ) {
    total += i
  }

}

console.log( total )
```

Solution 3:
Using a while loop and a ternary:
```
var i = 0;
while ( i < ceiling ) {
  !(i % 3) || !(i % 5) ? total += i : 0;
  i++
}

console.log( total )
```

## Exit Tickets
- If there are things the students find helpful (like recaps, in-lecture coding, etc) please mention so
