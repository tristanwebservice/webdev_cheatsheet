# Introducing Functions

## Intro to Functions

Functions are fundamental building blocks in JavaScript that allow you to encapsulate reusable code. A function is a block of code designed to perform a specific task. Functions can take inputs, called arguments, and can return outputs. They help organize code, improve readability, and facilitate code reuse.

## A Basic Function

A basic function is defined using the `function` keyword, followed by a name, parentheses for parameters, and a block of code enclosed in curly braces. 

```javascript
// Example of a basic function
function greet() {
  console.log("Hello, World!"); // Outputs a greeting message
}

// Calling the function
greet(); // Output: Hello, World!
```

## Arguments

Functions can accept parameters, which are specified within the parentheses. These parameters act as placeholders for the values (arguments) that will be passed to the function when it is called.

```javascript
// Example of a function with an argument
function greetUser(name) {
  console.log(`Hello, ${name}!`); // Outputs a personalized greeting
}

// Calling the function with an argument
greetUser("Alice"); // Output: Hello, Alice!
```

## Functions with Multiple Arguments

Functions can accept multiple arguments by separating them with commas in the parentheses. Inside the function, you can use these parameters to perform operations.

```javascript
// Example of a function with multiple arguments
function addNumbers(a, b) {
  return a + b; // Returns the sum of two numbers
}

// Calling the function with two arguments
let sum = addNumbers(5, 10);
console.log(sum); // Output: 15
```

## The Return Keyword

The `return` keyword is used to specify the value that a function should output when it is called. If no `return` statement is specified, the function will return `undefined` by default.

```javascript
// Example of using the return keyword
function multiply(x, y) {
  return x * y; // Returns the product of two numbers
}

// Calling the function and storing the result
let product = multiply(4, 5);
console.log(product); // Output: 20
```
