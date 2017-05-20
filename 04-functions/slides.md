

<img src="https://ga-core.s3.amazonaws.com/production/uploads/program/default_image/5225/JS-logo-official.png" style="max-width: 100px; border: none; box-shadow: none" />
## Class 04: Functions

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 20 min | Review                                   |
| 90 min | Functions                                |
| 25 min | Functional Programming                   |
| 20 min | Exercise                                 |
| 5  min | Exit                                     |

---
## Review
- Each row will become a group of 3-4 students
- Each group has a `warmup.js` file in the `exercises` directory
- Once all groups finish, someone from each group will present their solution

---
## Looking Ahead

| Lesson No. | Topic             |
| ---------- | -------           |
|     02     |   Data Types      |
|     03     |   Control Flow    |
|     **04**     |   **Functions**       |
|     05     |   Objects         |

---
## Functions

--
### Our first function
```
function myFunction() {
  console.log( 'This is my first function' )
}
```

--
### Calling our function
```
myFunction() // => 'This is my first function'
```

--
### Parameters
```
function sayThanks( name ) {
  console.log( 'Thanks ' + name )
}

sayThanks( 'Obama' )
// => 'Thanks Obama'
```

--
### Paramaters vs Arguments
Parameters: the variables defined in the function's declaration
Arguments: the actual values passed into the function when it's called
```
// Parameter
function doSomething (parameter) {
  // does something
}

// Argument
doSomething(argument)
```

--
### Returning values
- use and capture the results of our functions

--
### Returning values
```
function add( num1, num2 ) {
  return num1 + num2
}

var myNumber = add( 5, 10 )
// => myNumber = 15
```

--
### Function Scope
Scope determines where variables are considered defined

---
## Exercise

---
:# Thank you!
