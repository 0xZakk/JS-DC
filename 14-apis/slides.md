
<img src="https://ga-core.s3.amazonaws.com/production/uploads/program/default_image/5225/JS-logo-official.png" style="max-width: 100px; border: none; box-shadow: none" />
## Class 12: APIs

---
### Agenda
| Timing | Topic                     |
| ------ | ------------------------- |
| 5  min | Check In                  |
| 30 min | Warmup                    |
| 20 min | Introduction to AJAX      |
| 10 min | Break                     |
| 20 min | Working with AJAX         |
| 30 min | Working with APIs         |
| 10 min | Break                     |
| 20 min | Working with APIs         |
| 30 min | Building an API cont'd    |
| 5  min | Closing Questions & Exit  |

---
## Looking Ahead

| Lesson No. |        Topic             |
| ---------- | ------------------------ |
|     07     |   Intro to the DOM       |
|     08     | Events                   |
|     09     | Templating               |
|     10     | Express                  |
|     11     | Databases & CRUD         |
|   **11**   | **APIs**                 |
|     12     | Application Architecture |
|     13     | Lab #2                   |

---
### Warmup Exercise

--
## AJAX

--
### Introduction to Ajax
- Way for the client to communicate with the server
- Doesn't require a page refresh


--
### The 4 Benefits of AJAX
1. Callbacks
2. Asynchronous Calls
3. User-Friendly
4. Increase Speed

--
### 1. Callbacks
- Ajax is used to perform a callback, making a quick round trip to and from the server to retrieve and/or save data without posting the entire page back to the server
- What benefits could this have?

--
### 2. Asynchronous Calls
- Ajax allows you to make Asynchronous calls to a web server
- The browser can avoid waiting for all data to arrive before allowing the user to act
- State Description
      0	The request is not initialized.
      1	The request has been set up.
      2	The request has been sent.
      3	The request is in process.

--
### 3. User-Friendly
- Ajax enabled applications will always be more responsive, feel faster and thus provide a better user experience

--
### 4. Increase Speed
- rather than require the user to navigate to entirely different HTML document, we can just get the data we need using AJAX and update the current document

--
### Where can we use Ajax?
- Ajax should be used anywhere in a web application where small amounts of information could be saved or retrieved from the server without posting back the entire pages
- Can we think of any examples?

--

### Lets explore the technical aspects of Ajax
Exercise 1

---
### Introducing APIs

--

### A Brief History of APIs
- Web APIs first appeared in the wild with the introduction of Salesforce on February 7th, when the company officially launched its API at the IDG Demo 2000 conference
- Ebay was next to follow suit
- In 2002 Amazon launched AWS
- (AWS) allowed third party sites to search and display products from Amazon.com in an XML format.


### Why APIs?
- Websites are designed to cater to people's strengths.
- The characteristics that make websites optimal for humans make them difficult for computers to use.
- What's the solution?

### APIs
- An API is the tool that makes a website's data digestible for a computer
- Through it, a computer can view and edit data

### API and HTTP
- API calls are really a fancy term for making HTTP requests to a server and sending/receiving structured data from that endpoint.
-We are still communicating with URLs, however instead of receiving markup, like we do with HTML pages, we receive data, in a variety of forms -- JSON, XML, CSV, and others.

### OMDB API
- http://www.omdbapi.com/

### Exercise 2
- Weatherify
- http://openweathermap.org/api

### Exercise 3
- Build our own Pokemon API
