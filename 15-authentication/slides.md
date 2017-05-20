

<img src="https://ga-core.s3.amazonaws.com/production/uploads/program/default_image/5225/JS-logo-official.png" style="max-width: 100px; border: none; box-shadow: none" />
## Class 15: Authentication

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 20 min | Lab Review                               |
| 30 min | Final Project Discussion                 |
| 10 min | Break                                    |
| 20 min | Middleware                               |
| 30 min | Authentication                           |
| 10 min | Break                                    |
| 50 min | Authentication                           |
| 5  min | Closing Questions & Exit                 |

---
## Looking Ahead
| Lesson No. |        Topic             |
| ---------- | -----------------------  |
|   **15**   | **Authentication**       |
|     16     | Single Page Apps         |
|     17     | Deployment               |
|     18     | Final Project            |
|     19     | Presentations            |

---
## Lab Review
Walk through the solution <br />
https://github.com/ga-students/JS-DC-4-Lab02

---
## Final Projects
- Designing and building a web application of your choice
- check out https://gallery.generalassemb.ly/ for ideas!

--
### Important Deadlines
|  |  |
| ----------- | --------------------------------- |
| April 4th   | Idea Submission                   |
| April 20th  | UI Draft and Project Requirements |
| April 27th  | In Class Lab Time                 |
| May 2       | Due - Presentation                |

--
### Necessary Deliverables
- a production ready web application (live, on the web)
- a new git repository hosted on GitHub
- a 5-10 minute presentation including: 3 technical hurdles, 2 new things you learned, Q&A

--
### Project Feedback and Evaluation
- Technical Requirements
- Creativity
- Code Quality
- Problem Solving

--
### Exercise
- count off 1 through 3
- present your idea to the group for 2 minutes
- group asks follow up questions for 3 minutes

--
### One person presents their idea ( 2 minutes )
- What problem does your idea solve?
- What features will your application have?
- What technical challenges to you foresee with building this app?

--
### Group Question Ideas ( 3 minutes )
- What third-party libraries will you use?
- How will you architect your applications?
- What models will you use? what properties will they have?

---
## Middleware

--
### Middleware
Express is based on four things:
**1. Routing**
**2. Middleware**
3. Convenience methods & properties
4. Views

--
### Middleware
Middleware is/are functions that have access to the request and response objects, and the next middleware function

--
### Sample Middleware function
```
app.get('/', function (req, res next ) {
  // do some stuff to req and res

  next()
})
```

--
### Sample (more) Middleware function
```
app.get('/', function (req, res next ) {
  // do some stuff to req and res

  next()
}, function( req, res, next ) {
  // do some more stuff to req and res

  next()
})
```

--
### Sample (more more) Middleware function
```
app.get('/',
  someMiddleware,
  someMoreMiddleware,
  evenMoreMiddelware,
  function( req, res ) {
    res.send('ENOUGH ALREADY!')
  }
)
```

--
### Using Middleware
- useful for a lot of things
- can be scoped or applied wholesale

--
### Using Middleware
```
app.use(function( req, res, next ) {
  console.log( 'Time: ', Date.now() )
  next()
})
```

--
### Using Middleware
```
app.get('/pages', function( req, res, next ) {
  console.log( 'Request URL: ', req.originalURL )
  next()
}, function ( req, res next ) {
  console.log( 'Request Method: ', req.method )
  next()
})
```

--
### Common Middleware libraries:
- `serve.static` - serve static files
- `body-parser` - parse HTTP request body
- `morgan` - request logger
- `passport` - authentication

---
## Authentication

--
## Authentication
- confirming/proving identity

--
### Authentication
Authentication is the process of confirming and proving identity.
- ownership of data
- security

--
### Authorization
Is the current user allowed to access/edit this data?
- permission

--
### Passport

--
### Build an application with it!
