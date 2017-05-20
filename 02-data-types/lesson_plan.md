# Data Types

- Welcome to Class
- Go over the Learning Objectives
- draw Git chart on board for review

## Review: Git & Terminal
- What is Git?
- How does Git work?
- Why do we use Git?
- Fill in the chart:
  - making changes
  - staging
  - committing
  - pushing
    - fetch
    - merge
  - pulling
  - remote vs local

## Where are we?
- spent the last two classes downloading and learning a set of tools:
  - Git
  - Terminal
  - Node & NPM
- Next 4 classes are when we're going to learn how to write programs
- Start at the beginning/most atomic unit of any program, which is the data passing through that program
- every class is going to build of the ones before it and by the end we'll know just about everything about the language we need in order to write and build programs
- to draw an analogy, in your Language Arts or English classes in High School and maybe College, you learned about subjects, verbs, punctuation, sentence structure, paragraph structure, etc - since JavaScript is a *language* it's helpful to think about what we're learning over the next few weeks as synonymous in a lot of ways
  - instead of sentences and paragraphs, we have expressions and statements
  - instead of subjects and verbs, we have values and operators

## Variables
  - variables are identifiers for data
  - can think of them as boxes we store data in
  - functional and practical purpose:
    - need some way to store data in memory so we can reuse it, perform calculations and other operations on it
    - need to give our data meaning
      - a 4 is no longer just a 4 but the number of people sitting in the front row
      - a string is no longer just a string but someone's name

### Type Checking
  - We can check the type of a variable by using `typeof()`, which returns a string for the variable's type (i.e. `'number'`, `'string'`)

## Introduction to Data Types
**Write the below out as a mind map on the board**

- At the most generalized level of discussing programming, all we're doing is moving and manipulating data.

### What is a "Data Type"
- Data types are simply the kinds of data that we can work with within our program
- more nuanced than saying we can use numbers, strings, booleans, etc
- data types determine what the possible values can be in any given part of our program
- data types also determine what actions we can perform on our data
  --> Values and Operators

Two ways of classifying data types: Simple or Basic Data Types and Complex Data Types
- Today, we're talking about **Simple Data Types:**
1. Numbers
2. Strings
3. Booleans

- We'll get in to our first Complex data type: Arrays

- For each data type we cover, we'll answer these two questions:
  - What values constitute this data type?
  - What operations can I perform on this data type?

## Numbers
- What values constitute Numbers?
- What operations can we perform on Numbers?

### Numeric Values
- Numbers are *numeric values* stored in computer memory
- It's important to note that there is a limit to the size of numbers you can work with - but you wont need to worry about it, because it's really big
- JavaScript Numbers can be `integers` or `floats`
  integers: whole numbers like `1`, `10` or `-100`
  floats: fractional numbers like `1.2`, `3.14`, `0.25`

- That's kind of it as far as what we need to worry about when it comes to numeric data
- There are a lot of use cases for numeric data in JavaScript
  - numeric data: number of people on the bus
  - numbers as information: the score in a game we're building
  - numbers as attributes: the x and y coordinates of an element on the screen that we want to animate

### Operators
1. Arithmetic Operators
2. Number Operators (`Math` object)

#### Arithmatic operators

Addition:
```
console.log( 'Addition:' )
console.log( 1 + 1 ) // => 2
```

Subtraction:
```
console.log( 'Subtraction:' )
console.log( 2 - 5 ) // => -3
```

Division:
```
console.log( 'Division:' )
console.log( 5 / 1 ) // => 2.5
```

Multiplication:
```
console.log( 'Multiplication:' )
console.log( 6 * 2 ) // => 12
```

Modulo/Remainder:
```
console.log( 'Modulo:' )
console.log( 10 % 2 ) // => 0
console.log( 5 % 2 ) // => 1
```

#### Special Number Operators
`Math` object

Absolute value
```   
console.log( 'Absolute value:' )
console.log( Math.abs( 12.234 ) )
console.log( Math.abs( 0.1 + 0.2 ) )
```

Power
```
console.log( 'Power:' )
console.log( Math.pow( 3, 2 ) ) // => 9
```

Square root
```
console.log( 'Square root:' )
console.log( Math.sqrt( 4 ) ) // => 2
```

Random Number
```
console.log( 'Random Number:' )
console.log( Math.random() ) // => 0.229375290430
```

*How might I get a random number between 0 and 10*
```
Math.floor( Math.random() * ( max - min + 1 ) + min );
```

## Strings
- What values constitute Strings?
- What operations can we perform on Strings?

### String Values
- strings are made up of characters and stored within single or double quotes
  - can be either single or double quotes - important that the outermost quotes are the same and any inner quotes are the opposite
- We use string values a lot to represent text data - names, addresses, anything!

```
'hello world'
"hello world"
"hello 'world', hello"
```

### String Operations
1. Concatenation - adding two strings together
2. String methods

#### Concatenation
```
'hello ' + 'world'
'I have ' + 20 + ' dogs!'
```

### String Interpolation & Templates
- new in latest version of JavaScript
- function a lot like strings
- make with the backtick character

```

`test`

```

#### String Methods
```
'hello'.toUpperCase()
'HeLLo'.toLowerCase()
```

### Exercise
1. `console.log( 'zachary ' + 'fleischmann' )`
2. `console.log( 'zachary'.charAt(2) + 'zacary'.charAt(4) + 'zachary'.charAt(0) )`

## Booleans
- What values constitute Booleans?
  - something is either `true` or `false`
  - Sort of it
  - where this gets interesting is in what we use Booleans for - which is a lot
- What operations can we perform on Booleans?
  - Logical Operators - set of operators based on whether something is true or false
  - `and`, `or` and `not`
  - we care about what this evaluates to
  - evaluated values - any expression can evaluate to true or false

### Value
- only `true` and `false`

### Operations
- Logical operators
- Evaluated expressions

#### Logical Operators
Logical And ( && )
```
console.log( true && true ) // => true
console.log( true && false ) // => false
console.log( false && false ) // => false
```

Logical Or ( || )
```
console.log( true || true ) // => true
console.log( true || false ) // => true
console.log( false || false ) // => false
```

Logical Not ( ! )
```
console.log( !true ) // => false
console.log( !false ) // => true
```

#### Evaluated Expressions
Comparison operators
`==`, `===`, `>`, `<`, `>=`, `<=
`
True
```
console.log ( 1 == 1 ) // => true
```

False
```
console.log( 4 < 2 ) // => false
```

Combining them
```
console.log( !( 4 < 2) ) // => true
```

### Type Conversion
- we can convert a variable from one type to another
- we can convert a variables type by using conversion methods like `toString()`

```
var e = 5
console.log( typeof( e ) ) // => 'number'
e = e.toString()
console.log( typeof( e ) ) // => 'string'
e = parseInt(e)
console.log( typeof( e ) ) // => 'number'
e = e + '0'
console.log( typeof( e ), e ) // => 'string' 50
e = undefined
console.log( typeof( e ) ) // => 'undefined'
```

## Arrays
- Quick review - we now know numbers, strings, booleans - all of the basic data types
- we also know how to save data of these basic data types into variables so that we can reuse it elsewhere and actually work with that data
- what we will quickly find is that we need an efficient way of organizing our data into more than just individual variables and one way to do that is with *arrays!*
- in some other programming languages, arrays are called lists and I think that's a better way to describe what arrays are and what they do - it's a list of data

```
[1, 2, 3, 4, 5]
```

### Array Indexes
- once we've got our data into a list, we want to work with it
- How do I get the first value of an array?
- Indexes are 0 based - meaning the first item is `0`

```
var myOnlyFriends = ['Moe', 'Larry', 'Curly']

console.log( myOnlyFriends[0] ) // => 'Moe'
console.log( myOnlyFriends[1] ) // => 'Lary'
console.log( myOnlyFriends[2] ) // => 'Curly'
```

### Array Length
- the length of array is equal to the number of elements in the array
- always one larger than the index for the last element within the array

```
console.log( myOnlyFriends.length ) // => 3
console.log( myOnlyFriends[ myOnlyFriends.length ] ) // undefined
console.log( myOnlyFriends[ myOnlyFriends.length - 1 ] ) // 'Curly'
```

### Array Methods
- There are a ton of methods we can perform on arrays natively
- these let us efficiently perform some basic operations on arrays, like adding and removing elements from the beginning and end of arrays

remove and return the last element from an array
`console.log( myOnlyFriends.pop() ) // => 'Curly'`

Add an item to the end of an array
`console.log( myOnlyFriends.push( 'Christine' ) ) // => [ 'Christine', 'Moe', 'Larry', 'Curly' ]`

Reverse the order of items within an array
`console.log( myOnlyFriends.reverse() ) // => [ 'Curly', 'Larry', 'Moe' ]`

Concatenate elements of an array together into a string
`console.log( myOnlyFriends.join() ) // => 'Moe,Larry,Curly'`
