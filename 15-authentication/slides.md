<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" style="max-width: 100px; border: none; box-shadow: none"/>
## Class 15: Authentication

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 30 min | Final Project Discussion                 |
| 20 min | Middleware                               |
| 80 min | Authentication                           |
| 5  min | Closing Questions & Exit                 |

---
## Looking Ahead
| Lesson No. |        Topic             |
| ---------- | -----------------------  |
|     14     |   APIs                   |
|   **15**   | **Authentication**       |
|     16     | Databases Part 2         |
|     17     | Deployment               |
|     18     | Final Project            |
|     19     | Presentations            |

---
## Final Projects

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

1. **Routing**
2. **Middleware**
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
