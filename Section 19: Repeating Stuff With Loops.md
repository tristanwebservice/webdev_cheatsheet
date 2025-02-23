# Repeating Stuff With Loops

## Intro to Loops

Loops are fundamental programming constructs that allow you to execute a block of code repeatedly based on a specified condition. They are useful for automating repetitive tasks, iterating over data structures, and managing control flow in your programs.

## More For Loops Examples

The `for` loop is one of the most commonly used loops in JavaScript. It consists of three parts: initialization, condition, and increment/decrement. 

```javascript
// Example of a basic for loop
for (let i = 0; i < 5; i++) {
  console.log(i); // Output: 0, 1, 2, 3, 4
}

// Example of a for loop with an array
let fruits = ['apple', 'banana', 'cherry'];
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]); // Output: apple, banana, cherry
}
```

## Infinite Loops

An infinite loop occurs when the loop's condition never evaluates to false, causing the loop to run indefinitely. This can lead to performance issues or crashes if not handled properly.

```javascript
// Example of an infinite loop (use with caution)
let count = 0;
while (true) {
  console.log(count);
  count++;
  if (count > 10) break; // Breaks the loop after 10 iterations
}
```

## Looping Over Arrays

You can use loops to iterate over the elements of an array. This allows you to perform operations on each element, such as modifying values or performing calculations.

```javascript
// Example of looping over an array
let numbers = [1, 2, 3, 4, 5];
for (let number of numbers) {
  console.log(number * 2); // Output: 2, 4, 6, 8, 10
}
```

## Nested Loops

Nested loops are loops within loops. They are useful for working with multi-dimensional data structures, such as arrays of arrays.

```javascript
// Example of nested loops
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

for (let i = 0; i < matrix.length; i++) {
  for (let j = 0; j < matrix[i].length; j++) {
    console.log(matrix[i][j]); // Output: 1, 2, 3, 4, 5, 6, 7, 8, 9
  }
}
```

## The While Loop

The `while` loop repeatedly executes a block of code as long as a specified condition is true. It is useful when the number of iterations is not known beforehand.

```javascript
// Example of a while loop
let i = 0;
while (i < 5) {
  console.log(i); // Output: 0, 1, 2, 3, 4
  i++;
}
```

## The Break Keyword

The `break` keyword is used to exit a loop prematurely. It can be used in any loop type to stop execution when a certain condition is met.

```javascript
// Example of using break
for (let i = 0; i < 10; i++) {
  if (i === 5) break; // Exits the loop when i is 5
  console.log(i); // Output: 0, 1, 2, 3, 4
}
```

## For...of Loop

The `for...of` loop is a modern way to iterate over iterable objects, such as arrays and strings. It simplifies the syntax and improves readability.

```javascript
// Example of for...of loop
let colors = ['red', 'green', 'blue'];
for (let color of colors) {
  console.log(color); // Output: red, green, blue
}
```

## Iterating Over Objects

To iterate over the properties of an object, you can use the `for...in` loop. This loop iterates over the keys of the object.

```javascript
// Example of iterating over an object
let person = {
  name: "Alice",
  age: 30,
  city: "New York"
};

for (let key in person) {
  console.log(`${key}: ${person[key]}`); // Output: name: Alice, age: 30, city: New York
}
```
