# Authentication


## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Lab Review

### Application walk through

### Final Project
The assignment for today was to submit your final project idea. Today we're going to flush them out a together.

We're going to break out in to groups - count 1 through 3. You'll present your idea to the group for 2 minutes, answering a specific set of questions in your presentation. Then your group will ask you questions.

## Middleware
   - Express is a framework for building web applications built on two things:
      1. Routing
      2. Middleware
   - We've already seen routing - a lot! A lot of the lab involved routing.
   - middleware is/are functions that have access to the request object and response object and the next middleware function.
   - these functions are stored in an array, and called in order until a response is sent back to the client

### Using Middleware
   - We can use middleware in a lot of different places and ways
   - We've already kind of used it

Simple example: This middleware function will get called on every route:
```
app.use(function( req, res, next ){
  console.log( 'Time: ', Date.now() )

  next()
})
```

More complex example: This middleware function is scoped to `get` requests for our `pages`:
```
app.get('/pages/:num', function( req, res, next ) {

  console.log( 'Request URL: ', req.originalUrl )

  next()
}, function( req, res, next ) {

  console.log( 'Request method: ', req.method )

  next()
})
```

The reason we're covering middleware now is twofold:
(1) it's a really important part of Express and, depending on the functionality of your final project, you should definitely look to see if someone has already written middleware that will handle some of the business logic for your application
(2) we're going to be using middleware today to authenticate users in our sample application

## Authentication
__Goal: provide a basic overview of authentication__
Today's class is about authentication. We're going to touch on a related topic, which is authorization. We'll implement authentication but leave authorization for another time.

Authentication is the process of confirming and proving identity. In web applications, authentication refers to users identifying themselves through a login procedure.

Everyone will already be somewhat familiar with authentication, it's what happens when you sign in to Facebook or Twitter or Netflix. But signing-in is really only part of the whole story. There's a lot going on in an application that has authentication which we're going to cover today.



## Passport
We're going to use a library called `Passport` for all of this.

`Passport` is industry standard for JavaScript applications, there are other libraries out there and in many larger scale applications you'll end up building your own authentication package so you can fully control security, but by and large `Passport` is the way to go.

`Passport` is a middleware library, just like the ones we just created and used. `Passport` also has a huge ecosystem of secondary libraries that will implement other authentication strategies for you, like Facebook, Twitter, GitHub, Spotify.

### Setting up our application
We're going to build an application called PeopleBook - which is going to be a very simple social network where people can log in and comment on each other's profiles.

To get started, we need to install our dependencies. All you all need to do is run NPM install - but open up the `package.json` file to see what we're getting.

Express, express-session, mongoose, and body-parser are all libraries we've used before. These others we haven't, so what is bcrypt-nodejs, connect-flash, cookie-parser and express-session?

`bcrypt` is a library for a hashing algorithm that we'll use to hash our user's passwords

`flash` is a library for storing flash messages - a flash is a special part of the session object used for storing short messages. These messages get flashed to the user, typically before a redirect (i.e. that page you see when you sign up for a new account somewhere and it say "Your new account will load in 3 seconds. If it doesn't load, click here")

`cookie-parser`, just like `body-parser` but for cookies. This will create a `req.cookie` with an object keyed by cookie names.

`express-session` will create and manage a session object for all active sessions of our application

### Creating our User Model

Our User model is going to be pretty standard. Our Schema is going to be a bit more flushed out:
```
var mongoose = require('mongoose')
var Schema = mongoose.Schema

var userSchema = new Schema({
  username: {
    type: String,
    required: true,
    unique: true
  },
  password: {
    type: String,
    required: true
  },
  createdAt: {
    type: Date,
    default: Date.now
  },
  displayName: String,
  bio: String
})

userSchema.methods.name = function() {
  return this.displayName || this.username
}
```

Now our `password` field is a string, but we don't want to store the user's password as a string in our database - that would be bad! That's where `bcrypt` comes in!


```
var bcrypt = require('bcrypt-nodejs')
var SALT_FACTOR = 10
```

bcrypt works by running its hashing algorithm multiple times on itself. So it will take our password, hash it, then has that, then has that, on and on. The more times we hash it, the more secure our password are but the long it will take to create them. That number is called the `salt factor` and we can determine how many times bcrypt should run. We're going to say 10.


#### Pre-save hooks
We didn't talk about hooks when we talked about mongoose, but they're a really powerful tool. We're going to use a `pre` hook here to hash our password before a user is saved to the database. All `pre` hooks run before an operation and all `post` hooks run after an operation.

```
var noop = function() {}

userSchema.pre("save", function( done ) {

  var user = this

  if ( !user.isModified("password") ) {
    return done();
  }

  bycrypt.genSalt( SALT_FACTOR, function( err, salt ) {

    if ( err ) { return done( err ) }

    bcrypt.hash( user.password, salt, noop, function( err, hashedPassword ) {

      if ( err ) { return done( err ) }

      user.password = hashedPassword
      done()

    })

  })

})
```

#### Checking if a password is correct
The last method we need to define will tell us if the password entered in the front end of our application in the sign-in form is the correct password for that user. We're going to assume it's a guess and we want to check to see if that guess is correct. If it is, we'll authenticate them.

```
userSchema.methods.checkPassword = function( guess, done ) {

  bcrypt.compare( guess, this.password, function( err, isMatch ){

    done( err, isMatch )

  })

}
```

Boom! We're done

## Using our User

We're going to build out our `index.j` file but we're going to do one thing different, and that's we're going to separate our routes into a separate file to make it easier to focus on working with passport - I think it'll become more clear in a minute.

Our `index.js` file:
```
var express = require('express')
var bodyParser = require('body-parser')
var hbs = require('express-handlebars')
var mongoose = require('mongoose')
var session = require('express-session')
var flash = require('connect-flash')
var cookieParser = require('cookie-parser')
var path = require('path')
var routes = require('./routes')

var app = express()

mongoose.connect("mongodb://localhost:27017/user-solution")

app.engine('handlebars', hbs({ defaultLayout: 'default' }))
app.set('view engine', 'handlebars')

app.use(bodyParser.urlencoded({ extended: true }))
app.use(cookieParser())
app.use(session({
    secret: "TKRv0IJs=HYqrvagQ#&!F!%V]Ww/4KiVs$s,<<MX",
    resave: true,
    saveUninitialized: true
}))

app.use(flash())

// Use Routes
app.use(routes)

app.listen(3000)
```

Our `routes.js` file:
```
var express = require('express')
var User = require('./models/user')
var router = express.Router()

router.use(function(req, res, next) {

    res.locals.currentUser = req.user
    res.locals.errors = req.flash("error")
    res.locals.infos = req.flash("info")
    next()

})

router.get("/", function(req, res, next) {

    User.find()
        .sort({
            createdAt: "descending"
        })
        .exec(function(err, users) {

            if (err) { return next(err) }

            res.render("index", { users: users })

        })

})

module.exports = router
```

Now we have to create our sign-up route:
```
var passport = require('passport')
```

For our sign-up route, we need both a get request to render our signup form and a post request to submit that form to.


```
router.get("/signup", function(req, res) {

 res.render("signup")

})

router.post("/signup", function(req, res, next) {
    var username = req.body.username
    var password = req.body.password

    User.findOne({
        username: username
    }, function( err, user ) {

        if ( err ) { return next(err) }

        if ( user ) {
            req.flash("error", "User already exists")
            return res.redirect("/signup")
        }

        var newUser = new User({
            username: username,
            password: password
        })

        newUser.save( next )

    })
}, passport.authenticate("login", {

    successRedirect: "/",
    failureRedirect: "/signup",
    failureFlash: true

}))
```
