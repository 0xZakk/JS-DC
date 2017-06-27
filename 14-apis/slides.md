
<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" style="max-width: 100px; border: none; box-shadow: none"/>
## Class 14: APIs

---
### Agenda
| Timing | Topic                     |
| ------ | ------------------------- |
| 5  min | Check In                  |
| 50 min | Lab Review                |
| 50 min | Working with AJAX         |
| 50 min | Working with APIs         |
| 5  min | Closing Questions & Exit  |

---
## Looking Ahead
| Lesson No. |        Topic             |
| ---------- | -----------------------  |
|   **14**   | **APIs**                 |
|     15     | Authentication           |
|     16     | Databases Part 2         |
|     17     | Deployment               |
|     18     | Final Project            |
|     19     | Presentations            |

---
### Lab Review

---
## APIs

--
### APIs
1. Working with APIs
2. Building an API

--
### APIs
Application Programmable Interface

--
### APIs
1. Working with APIs on the Client
2. Working with APIs on the Server
3. Building a simple API

---
## AJAX

--
### Introduction to AJAX
- Asynchronous JavaScript and XML
- Way for the client to communicate with the server
- Asynchronous: doesn't require a page refresh

---
### AJAX in client side JavaScript
2 implementations:
1. `XMLHttpRequest()`
2. `fetch()`

--
### XMLHttpRequest
```
let req = new XMLHttpRequest()
req.onreadystatechange = handleRequest
req.open('GET', 'http://pokedexapi.com/')
req.send()
```

--
### Fetch
```
  fetch('http://pokedexapi.com/')
    .then((response) => {
      console.log( response )
    })
```
--
### Which should you use?
<iframe src="https://giphy.com/embed/3otPoUjeyRisIDxPhK" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/filmeditor-mean-girls-movie-3otPoUjeyRisIDxPhK">via GIPHY</a></p>

--
### Fetch is **very** new
<iframe src="https://giphy.com/embed/5G98t8QjqBLK8" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/mean-girls-regina-george-stop-trying-to-make-fetch-happen-5G98t8QjqBLK8">via GIPHY</a></p>

--
## Let's see them in action!

---
### AJAX in server side JavaScript

--
### Server Side AJAX
- `http` or `https` modules
- requires an understanding of streaming
- going to use `request` module from npm

--
### Request
```
request.get('http://pokedexapi.com/')
  .on('response', ( response ) => {
    console.log( response )
  })
```

--
## Let's see it in action!

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
