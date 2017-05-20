

<img src="https://ga-core.s3.amazonaws.com/production/uploads/program/default_image/5225/JS-logo-official.png" style="max-width: 100px; border: none; box-shadow: none" />
## Class 11: CRUD and Databases

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 40 min | Review Express & Pokedex                 |
| 20 min | Introduction to Databases & CRUD         |
| 10 min | Break                                    |
| 50 min | Databases & CRUD continued               |
| 10 min | Break                                    |
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
### A brief history
- One of the first things computers we're used for
- The 'data base' was a stack of punch cards

--
### A brief history - 1960s
- first DBMS introduced, CODASYL
- found records with one of three methods:
  (a) primary key
  (b) navigating relationships
  (c) scanning all records sequentially

--
### A brief history: 1970s
- first relational database is created
- data is organized in to tables
- each entity gets its own table
- SQL

--
### A brief history: SQL
- Structured Query Language

--
### A brief history: ORM
- Object-Relational Mappings
- part of a movement to make data storage more object oriented

--
### A brief history: NoSQL
- rejects the strict relational structuring of data

--
### Key Terms
| Term | Definition |
| relational database | Data stored in tables and rows |
| non-relational database (NoSQL) | Data in unstructured collections |
| SQL | Structured Query Language |
| ORM | Object-Relational Mapping |

---
## Database Operations
`CRUD`

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
## First App: Guestbook
We want to build an app that lets anyone who visits our site create an entry in a guestbook.

---
## Second App: To Do List
We're going to build a to do list application that lets us create and manage to do list items, and even edit them.
