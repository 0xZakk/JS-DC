#

## Learning Objectives
- Understand the architecture of a SPA
- Build out a basic SPA

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Advanced Mongo Queries
- Querying the database can be broken up in to 2 parts:
  1. A query
  2. Filtering

### Query
- An object that we send to the database
- all items in the collection are matched against this object
- the positive matches are returned
- we can query against any parameter defined in our Schema

### Common Queries

Given the following Schema:
```
const pokemonSchema = new Schema({
  name: String,
  attack: Number,
  defense: Number,
  evolveLevel: Number,
  type: String,
  moves: Array,
})
```

1. Find all pokemon
```
Pokemon.find({}, callback)
```

2. Find a pokemon by it's ID
We've already seen how to find a pokemon by it's ID:
```
Pokemon.find({'_id': someId}, callback)
```

3. Find a pokemon by it's name
```
app.get('/find-by-name/:name', ( req, res ) => {
  Pokemon.findOne({ 'name': req.params.name }, ( err, pokemon ) => {
    res.json( pokemon )
  })
})
```

4. Find a pokemon by it's evolveLevel
```
app.get('/find-by-evolveLevel/:evolveLevel', ( req, res ) => {
  Pokemon.find({ 'evolveLevel': req.params.evolveLevel }, ( err, pokemon ) => {
    res.json( pokemon )
  })
})
```

5. Find a pokemon with an attack greater than a certain number
```
app.get('/find-by-attack/:attack', ( req, res ) => {
  Pokemon.find({ 'attack': { $gt: req.params.attack } }, ( err, pokemon ) => {
    res.json( pokemon )
  })
})
```
You can also search for less than values with `$lt`

### Filter
In addition to querying, we can filter results once we get them back to the database.

This is an important distinction:
  - querying provides a set of criteria to the database and we get the results back that meet those
  criteria
  - filtering takes the results we got from the database and lets us narrow them down (filter them)

1. We can filter against criteria, like querying:
```
app.get('/filter/find-by-attack/:attack', ( req, res ) => {
  Pokemon.find({})
    .where('attack').gt( req.params.attack )
    .exec( ( err, pokemons ) => {
      res.json( pokemons )
    })
})
```

2. We can filter to only return a certain number of results
```
app.get('/filter/limit-by-attack/:attack', ( req, res ) => {
  Pokemon.find({})
    .where('attack').gt( req.params.attack )
    .limit(10)
    .exec( ( err, pokemons ) => {
      res.json( pokemons )
    })
})
```

3. We can filter to sort our results
```
app.get('/filter/sort-by-attack/:attack', ( req, res ) => {
  Pokemon.find({})
    .where('attack').gt( req.params.attack )
    .limit(10)
    .sort('attack')
    .exec( ( err, pokemons ) => {
      res.json( pokemons )
    })
})
```

## Promises
- before we can really talk about promises, we need to understand the problem that Promises solve

### Asynchronous Programming
- Node/JavaScript is an asynchronous language (Python is synchronous)
- practically: means that one line of code doesn't need to finish executing before the next line is read
  - contrast with Python: does one thing at a time
  - you can think of it as: JavaScript can juggle, Python throws one ball at a time
- we saw this initially when we discussed databases
  - DB queries take some time, we want to ensure that what ever action we want to perform on the data we're
  querying for happens _after_ the query has come back
  - we solved this with callbacks
  - what happens when we need to do multiple asynchronous tasks in order?

This is the problem that Promises solve: callback hell

### Callback Hell
- When we need to perform multiple asynchronous tasks in order, we end up deeply nesting multiple callbacks
- This is difficult to debug and extremely difficult to read:

```
doSomething(function(result) {
  doSomethingElse(result, function(newResult) {
    doThirdThing(newResult, function(finalResult) {
      console.log('Got the final result: ' + finalResult);
    }, failureCallback);
  }, failureCallback);
}, failureCallback);
```

With promises we get something like this: 
```
doSomething()
.then(result => doSomethingElse(result))
.then(newResult => doThirdThing(newResult))
.then(finalResult => {
  console.log(`Got the final result: ${finalResult}`);
})
.catch(failureCallback);
```

- Promises do not eliminate callbacks, they use callbacks.
- Promises ensure that callbacks are called in the same predictable manner

### Using Promises
- We create a new promise using the `Promise` constructor
- not very useful on their own
- we return a promise from an asynchronous function
- the promise acts as an object that will resolve to some data at some point in the future

## Array Methods
- In future versions of this class, I'm going to add a class on Arrays
- Arrays are a very common and under-utilized data type
- It's rare that we'll be dealing with a single object - so it's important to be able to process arrays in
batch
