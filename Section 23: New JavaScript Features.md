# New JavaScript Features

## Default Parameters

Default parameters allow you to set default values for function parameters. If no value or `undefined` is passed for a parameter, the default value will be used.

```javascript
// Example of default parameters
function multiply(a, b = 1) {
  return a * b; // If b is not provided, it defaults to 1
}

console.log(multiply(5)); // Output: 5 (5 * 1)
console.log(multiply(5, 2)); // Output: 10 (5 * 2)
```

## Spread in Function Calls

The spread operator (`...`) allows you to expand an array into individual elements when calling a function. This is useful for passing an array as arguments to a function.

```javascript
// Example of spread in function calls
const numbers = [1, 2, 3];
const sum = (a, b, c) => a + b + c;

console.log(sum(...numbers)); // Output: 6 (1 + 2 + 3)
```

## Spread with Array Literals

The spread operator can also be used to create new arrays by combining existing arrays or adding new elements.

```javascript
// Example of spread with array literals
const fruits = ['apple', 'banana'];
const moreFruits = ['orange', 'grape'];

const allFruits = [...fruits, ...moreFruits]; // Combines both arrays
console.log(allFruits); // Output: ['apple', 'banana', 'orange', 'grape']
```

## Spread with Objects

The spread operator can be used to create new objects by copying properties from existing objects or merging multiple objects.

```javascript
// Example of spread with objects
const person = { name: 'Alice', age: 30 };
const job = { title: 'Developer' };

const employee = { ...person, ...job }; // Merges both objects
console.log(employee); // Output: { name: 'Alice', age: 30, title: 'Developer' }
```

## Rest Parameters

Rest parameters allow you to represent an indefinite number of arguments as an array. This is useful for functions that need to accept multiple arguments without knowing how many in advance.

```javascript
// Example of rest parameters
function sumAll(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0); // Sums all provided numbers
}

console.log(sumAll(1, 2, 3, 4)); // Output: 10
```

## Destructuring Arrays

Destructuring allows you to unpack values from arrays into distinct variables. This makes it easier to work with array elements.

```javascript
// Example of destructuring arrays
const colors = ['red', 'green', 'blue'];
const [firstColor, secondColor] = colors; // Unpacks values into variables

console.log(firstColor); // Output: red
console.log(secondColor); // Output: green
```

## Destructuring Objects

Destructuring can also be applied to objects, allowing you to extract properties into variables.

```javascript
// Example of destructuring objects
const person = { name: 'Alice', age: 30 };
const { name, age } = person; // Unpacks properties into variables

console.log(name); // Output: Alice
console.log(age); // Output: 30
```

## Destructuring Parameters

You can use destructuring directly in function parameters to extract values from objects or arrays passed as arguments.

```javascript
// Example of destructuring parameters
function displayPerson({ name, age }) {
  console.log(`Name: ${name}, Age: ${age}`); // Uses destructured parameters
}

displayPerson({ name: 'Bob', age: 25 }); // Output: Name: Bob, Age: 25
```
