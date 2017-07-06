# Deployment

## Learning Objectives
- Understand microservices and containers
- Understand cloud hosting
- Learn how to deploy static and dynamic web applications

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Final Project Exercise

## Intro to Deployment

## Deploying Static Applications
- static deployment for deploying static applications
- where we have no server-side processing

### Branching
- branching is a feature of Git that we haven't talked about
- one of git's most used features
- two people are working on a feature for an application
- their feature will be finished and deployed in two weeks
- we have another set of features that we need to deploy this week
- with what we know about git now, there's no way for us to do
this
- if they push to github, then it will have their
unfinished work and we take the codebase as it is on github
and deploy it to our users
- branching comes in
- you can think of it like forking from within a repository
- take the code as it is now, and branch off of it
- we then have a separately maintained version of the codebase
- we can make changes, add them commit them
- we can push this branch to a remote branch in github
- what is on the main branch wont be affected, until we merge
our branches together
- branching opens up a lot of opportunities for maintaining
slightly different versions of a codebase
- for a large scale application, you'll have 1 branch per
feature, 1 branch where you'll maintain all almost completed
work, 1 branch for you staging environment and 1 branch for
your production environment

### GitHub Pages
- static hosting service, based on branching within a
repository
- reserved branch name, `gh-pages`
- pushing to the remote `gh-pages` branch will 'deploy' our
static application

### Follow along
- create a new repository on GH
- copy Pixart files into a new folder locally
- git init, add and commit
- add new GH repository as origin
- push to master
- checkout gh-pages branch
- push to gh-pages
- check settings to make sure it worked
- check email to make sure there isn't a build error
- in a few minutes, should see our application

We do with pixart, you do with static to do list application

## Deploying Dynamic Applications
- we're going to use a service called heroku to deploy our
dynamic applications
- provides a good free tier and is easy to work with
- uses git for all deployments!

### Heroku
- in the folder for Lab 02
- create a `Procfile` - this is what Heroku will use once we
push our code to the server to start our application
- edit our package.json
  - need to include an npm script for `npm start`
  - need to include an 'engine', which will tell Heroku what
  environment to build, in our case `node`

```
  "engines": {
    "node": "6.10.2"
  }
```

- once we do all that, we need to commit these changes
  - Heroku works off of git, so we have to commit changes
  before we can deploy them

#### Common Gotcha's
- there are some issues you may run in to when deploying to
Heroku

1. You may need to set the `buildpack` manually
- Heroku should detect the `buildpack` by looking at your code
and reading the `engine` from your `package.json`
- this sometimes doesn't work, so you'll need to set it
manually
- the buildpack is what Heroku uses to build the environment
your application is going to run in - i.e. a server that has
node and npm installed on it
- you can set the buildpack manually with:

```
heroku buildpacks:set heroku/nodejs
```

2. You may need to add the Heroku remote manually
- when you run `heroku create`, heroku creates a server for
you and creates a remote repository on that server (kind of
like GitHub)
- it _should_ add that repository as a remote to your local
repository, but it may not
- if it doesn't, copy the link and run:

```
git remote add heroku <link to heroku remote>
```

