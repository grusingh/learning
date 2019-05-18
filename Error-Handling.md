# Error Handling

Used when getting data from user inputs or API calls where data received may be unreliable.

Try, Catch handles run time errors. Code must execute it to work.

## Try

`Try` block runs or parses the code where error can be perceived.

## Catch

`Catch` block handles the errors generated at run time.

## Finally

Regardless of `Try` and `Catch`, `Finally` runs and executes something in case of error.

## Throw

`Throw` allows us to handle errors in a customized way.

## Example

```javascript
let data = {
  name: '',
  age: 26
}
try {
  console.log('Try block started')
  if(!data.name) {
    throw new SyntaxError('Incomplete data: Name is empty')
  }
  console.log(data.name)
  console.log('Try block ends')
} catch(error) {
  console.log('Error occurred:', 'Error object:', error, 'Error Name:', error.name, 'Error Stack:', error.stack, 'Error Message:', error.message)
} finally {
  console.log('This block always execute')
}

console.log('Further execution continues')
```