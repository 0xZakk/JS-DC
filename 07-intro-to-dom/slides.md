

<img src="https://ga-core.s3.amazonaws.com/production/uploads/program/default_image/5225/JS-logo-official.png" style="max-width: 100px; border: none; box-shadow: none" />
## Class 07: Intro to the DOM

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 30 min | Review the Lab                           |
| 5  min | Break                                    |
| 25 min | JS In the Browser                        |
| 45 min | Intro to the DOM & Working with the DOM  |
| 5  min | Break                                    |
| 50 min | Working with the DOM cont'd              |
| 5  min | Closing Questions & Exit                 |

---
## The Lab
How did it go?

---
## Intro to JavaScript: Phase II

--
## Looking Ahead

| Lesson No. |        Topic             |
| ---------- | ------------------------ |
|   **07**   | **Intro to the DOM**     |
|     08     | Events                   |
|     09     | Templating & Build Tools |
|     10     | Express                  |
|     11     | Databases & CRUD         |
|     12     | APIs                     |
|     13     | Application Architecture |
|     14     | Lab #2                   |

---
## JS In the Browser

--
### History recap
- JavaScript started as a client side scripting language
- still is largely used for getting, setting, changing, moving, removing and updating elements on a page

--
### How do browsers work?
- Fetch assets to build a given page (HTML, CSS, JS)
- Builds a model of the document
- Uses a rendering engine to draw the document

--
### The Document Object Model
- a model built by the browser that represents the document's structure (a model)
- it describes aspects of the current document (properties!) and gives us ways to work with the document (methods!)

--
### Lets see it in action!
Open up Chrome

---
## What is the DOM?
- data structure that models our document
- exposes a number of properties and methods we can use to work with the document
- tree structure

--
### Document tree
How does the browser break a html document up into a tree?

---
## Working with the DOM
1. Getting data from the DOM
2. Setting data in the DOM

--
### Getting data from the DOM

--
### Getting Elements from the page
`document.getElementById('myID')` <br>
`document.getElementsByTagName('div')`<br>
`document.getElementsByClassName('my-class')`

--
### Understanding the methods:
`document.getElementById('myID')` <br>
`document.getElementsByClassName('my-class')`

- method
- selector

--
### New way of getting elements from the page
- `document.querySelector('#myID')`
- `document.querySelector('.my-class')`
- `document.querySelectorAll('.my-class')`
- `document.querySelectorAll('div')`

--
### Using DOM elements
Once we retrieve a DOM element, we have an object with properties and methods that we can use to work with that element

--
### Setting data in the DOM

--
### Exercises
