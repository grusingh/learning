# Function
* A unit of code. 
* Allows code reuse.

## Declaration 
```javascript
// hoisted
function add(a, b) {
  return a + b
}

// not hoisted
const add = function(a, b) {
  return a + b
}

const add = (a, b) => a + b

// returns undefined
function puts(message) {
  console.log(message)
}
```

## Function is object
```javascript
// pass as parameter
function calculate(a, b, operation = (a,b) => a + b) {
  calculate.counter += 2
  return operation(a,b)
}

// define property
calculate.counter = 0

calculate(5, 10)
console.log(calculate.counter)
```

## Roles

```javascript
// function
add(5, 10)

// constructor
new Date()

// method
const calculator = {
  add(a, b) {
    return a + b
  }
}

calculator.add(5,10)
```

## Pass by value

```javascript
let counter = 1

function increment(counter) {
  counter = counter + 1
}

increment(counter)
console.log(counter) // 1
```


```javascript
let counter = { value: 1 }

function increment(counter) {
  counter.value = counter.value + 1
}

increment(counter)
console.log(counter.value) // 2
```

## Named parameters

```javascript
function printMovie(name, releaseDate, director, cast) {
  console.log(name, releaseDate, director, cast)
}
printMovie('The Matrix', '1999', 'The Wachowski Brothers', ['Keanu Reeves', 'Laurence Fishburne', 'Carrie-Anne Moss'])

function printMovie({ name, releaseDate, director, cast }) {
  console.log(name, releaseDate, director, cast)
}
printMovie({ 
  name: 'The Matrix', 
  releaseDate: '1999', 
  director: 'The Wachowski Brothers', 
  cast: ['Keanu Reeves', 'Laurence Fishburne', 'Carrie-Anne Moss']
})
```

## Call, apply, bind
```javascript
const movie = {
  name: 'The Matrix',
  
  print(msg) {
    console.log(msg, this.name)
  }
}

movie.print("method")

const printMovie = movie.print
printMovie("function")

printMovie.call(movie, "call")
printMovie.apply(movie, ["apply"])

const printBound = printMovie.bind(movie)
printBound("bind")
```

# Scope
* Lexical scoped.
* Variables are function scoped.
* Nesting and Shadowing.
* Variable declarations are hoisted.

```javascript
function movieInfo(rating) {
  var name = "The Matrix"
  var releaseDate = 1999
  
  function directorInfo() {
    var name = "The Wachowski Brothers"
    console.log("rating", rating)
    console.log("director rating", directorRating)
    var directorRating = 9
    return name
  }
  
  console.log("name:", name, releaseDate, directorInfo())
  console.log("directorRating", directorRating)
}

movieInfo(9)
```
