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

## Value
```javascript
function calculate(a, b, operation) {
  return operation(a,b)
}

calculate(5, 10, add)
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

