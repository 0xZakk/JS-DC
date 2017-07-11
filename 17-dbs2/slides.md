<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" style="max-width: 100px; border: none; box-shadow: none"/>
## Class 17: Databases, Promises, and FP
Oh my!

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 30 min | Advanced Mongo Queries |
| 30 min | Promises |
| 30 min | Arrays 2 |
| 40 min | Final Project |
| 5  min | Closing Questions & Exit                 |

---
## Looking Ahead
| Lesson No. |        Topic             |
| ---------- | -----------------------  |
|     14     |   APIs                   |
|     15     |   Authentication         |
|     16     |   Deployment             |
|   **17**   | **Wild Card**            |
|     18     | Final Project            |
|     19     | Presentations            |

---
## Advanced Mongo

--
### Advanced Mongo
1. Queries
2. Filters

--
### Query
- Object we send to the database
- All instances are matched against this object
- The positive matches are returned
- Can query against any parameter defined in our Schema

--
### Filter
- Once we have a query, we can filter the results
- Narrow down final results by criteria
- limit number of results
- sort results

--
### Key difference:
- Query: set of criteria to match records in the DB against
- Filter: manipulating results from the DB

--
### Let's see them in action!

---
## Promises

--
### Promises: solution to a problem
- node/js is asynchronous
- traditionally handled by callbacks

--
### Callback hell:
```
doSomething(function(result) {
  doSomethingElse(result, function(newResult) {
    doThirdThing(newResult, function(finalResult) {
      console.log('Got the final result: ' + finalResult);
    }, failureCallback);
  }, failureCallback);
}, failureCallback);
```

--
### Promises
```
doSomething()
.then(result => doSomethingElse(result))
.then(newResult => doThirdThing(newResult))
.then(finalResult => {
  console.log(`Got the final result: ${finalResult}`);
})
.catch(failureCallback);
```

--
### Using Promises (Pt 1)
```
function wait( time ) {
  return new Promise(function( resolve, reject ) {
    return setTimeout( resolve, time )
  })
}
```

--
### Using Promises (Pt 2)
```
wait(3000).then(function() {
  console.log('Hello Promises!')
})
```

---
## Working with Arrays

--
### Let's see them in action
