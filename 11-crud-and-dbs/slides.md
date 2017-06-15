

<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" style="max-width: 100px; border: none; box-shadow: none"/>
## Class 11: CRUD and Databases

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 30 min | Review Express & Pokedex                 |
| 70 min | Introduction to Databases & CRUD         |
| 50 min | Guestbook Exercise                       |
| 5  min | Closing Questions & Exit                 |

---
## Looking Ahead

| Lesson No. |        Topic             |
| ---------- | ------------------------ |
|     07     |   Intro to the DOM       |
|     08     | Events                   |
|     09     | Templating &             |
|     10     | Express                  |
|   **11**   | **Databases & CRUD**     |
|     11     | APIs                     |
|     12     | Application Architecture |
|     13     | Lab #2                   |

---
## Homework Review: Interviews!
- Count off 1 through 3
- A question will come up here
- One student will answers the question for one minute
- The group will discuss for 2 minute


--
### 1. What are the parts of a Full Stack application? What sorts of tasks does each part perform and how do they relate to each other?


--
### 2. What are the parts of an HTTP request and response? What is important about each part?


--
### 3. Describe (generally) the steps involved in setting up a basic web application using `express`.
(hint: 3 steps)

---
## Homework Review
Walk through on how to build the pokedex

---
## Class overview
1. Conceptual Introduction
2. Activity 1: Setting up our first DB
3. Activity 2: Building an application that uses a database

---
## Introduction to Databases

--
### Databases
- A way to store our data so we can access it later

--
### Introduction: SQL
- Structured Query Language
- data organized by relation

--
### Introduction: NoSQL
- rejects the strict relational structuring of data

--
### Introduction: ORM
- Object-Relational Mappings
- part of a movement to make data storage more object oriented

--
### Key Terms
| Term | Definition |
| --- | --- |
| relational database | Data stored in tables and rows |
| non-relational database (NoSQL) | Data in unstructured collections |
| SQL | Structured Query Language |
| ORM | Object-Relational Mapping |

---
## Database Operations
`CRUD`

---
## Database Operations
Create - Read - Update - Delete

--
### CRUD: Create
- `save()`

--
### CRUD: Read
- `find()`
- `findOne()`

--
### CRUD: Update
- `update()`

--
### CRUD: Delete
- `remove()`

---
## Working with Databases
Installing MongoDB: <br>
- [Mac](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
- [Windows](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)

__Follow the Installation and Setup instructions__

---
## First App: Pokedex
We're going to make it so that we can make and edit pokemon!

---
## Second App: To Do List
We want to build an app that lets anyone who visits our site create an entry in a guestbook.
