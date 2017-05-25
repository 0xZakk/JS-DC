

<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" style="max-width: 100px; border: none; box-shadow: none" />
## Class 05: Objects

---
### Agenda
| Timing | Topic                                    |
| ------ | ---------------------------------------- |
| 5  min | Check In                                 |
| 30 min | Review                                   |
| 90 min | Objects                                  |
| 30 min | Object Oriented Programming              |
| 5  min | Closing Questions & Exit                 |

---
## Review

---
## You are here

| Lesson No. | Topic             |
| ---------- | -------           |
|     02     |   Data Types      |
|     03     |   Control Flow    |
|     04     |   Functions       |
|   **05**   | **Objects**       |

---
## Objects

--
### Anatomy of an Object
- Open with curly braces, `{}`
- Properties: key/value pairs
- Methods: functions within an object

--
### Our First Object
```
  let Person = {
    'first name': 'Zakk',
    lastName: 'Fleischmann'
  }
```

--
### Objects
- Can store anything in an object
- Can use objects to model real world things

--
### Objects
```
  let Person = {
    firstName: 'Zakk',
    favoriteColors: ['green', 'blue'],
    height: {
      feet: 6,
      inches: 4
    },
    isShort: false,
    sayHello: ( name ) => {
      console.log( `hello ${name}` )
    }
  }
```

--
### Data Modeling with Objects
- Grouping data and functionality
- Model some real world object (like a car)

--
### Exercise 01

--
### Working with Objects

--
### Working with Objects: Getting Data
- Bracket notation, `myObject['property']`
- Dot notation, `myObject.property`

--
### Working with Objects: Setting Data
- reassignment: `myObject['property'] = 1`

--
### Looping over properties in an object
- first get keys of an object as an array
- loop over array of keys and look up value

--
### Looping over properties in an object
```
  Object.keys( person ).forEach((prop) => {
    console.log(`${ prop }: ${ person[ prop ] }`)
  })
```

--
### Sidebar: JSON
- JavaScript Object Notation
- lightweight data format (like SQL, but nothing like SQL)

---
## Object Oriented Programming

--
### Terminology
|  Term       |  Definition         |
| ------      | ------------------- |
| class       | a generic thing     |
| instance    | a specific thing    |
| method      | class functionality |

---
## Exercise

---
## Closing questions and Exit Tickets
