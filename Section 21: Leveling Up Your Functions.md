# Leveling Up Your Functions 

## Function Scope

Function scope refers to the accessibility of variables within a function. Variables declared inside a function are not accessible outside of it. This encapsulation helps prevent variable name conflicts and keeps the global scope clean.

```javascript
function myFunction() {
  let localVar = "I'm local"; // Local variable
  console.log(localVar); // Output: I'm local
}

myFunction();
// console.log(localVar); // Error: localVar is not defined
```

## Block Scope

Block scope is introduced with `let` and `const` keywords, allowing variables to be limited to the block in which they are defined (e.g., within `{}` braces). This is different from function scope, where variables are accessible throughout the entire function.

```javascript
if (true) {
  let blockScopedVar = "I'm block scoped"; // Block-scoped variable
  console.log(blockScopedVar); // Output: I'm block scoped
}

// console.log(blockScopedVar); // Error: blockScopedVar is not defined
```

## Lexical Scope

Lexical scope refers to the visibility of variables based on their location in the source code. Inner functions have access to variables declared in their outer (enclosing) functions, even after the outer function has finished executing.

```javascript
function outerFunction() {
  let outerVar = "I'm from the outer function";

  function innerFunction() {
    console.log(outerVar); // Accesses outerVar from the outer function
  }

  innerFunction(); // Output: I'm from the outer function
}

outerFunction();
```

## Function Expressions

Function expressions define a function as part of a larger expression. They can be anonymous (without a name) and can be assigned to variables, passed as arguments, or returned from other functions.

```javascript
// Example of a function expression
const add = function(a, b) {
  return a + b; // Returns the sum of a and b
};

console.log(add(2, 3)); // Output: 5
```

## Higher Order Functions

Higher order functions are functions that can take other functions as arguments or return functions as their result. This allows for powerful functional programming techniques.

```javascript
// Example of a higher order function
function greetUser(greetingFunction) {
  return greetingFunction("Alice"); // Calls the passed function
}

const sayHello = function(name) {
  return `Hello, ${name}!`;
};

console.log(greetUser(sayHello)); // Output: Hello, Alice!
```

## Returning Functions in Functions

You can return a function from another function, creating closures that maintain access to the outer function's scope.

```javascript
// Example of returning a function
function multiplier(factor) {
  return function(x) {
    return x * factor; // Uses the factor from the outer function
  };
}

const double = multiplier(2); // Creates a function that doubles the input
console.log(double(5)); // Output: 10
```

## Defining Methods

Methods are functions that are properties of an object. They can be defined using function expressions or shorthand method syntax in object literals.

```javascript
// Example of defining methods
const calculator = {
  add: function(a, b) {
    return a + b; // Method to add two numbers
  },
  subtract(a, b) {
    return a - b; // Shorthand method definition
  }
};

console.log(calculator.add(5, 3)); // Output: 8
console.log(calculator.subtract(5, 3)); // Output: 2
```

## This Keyword

The `this` keyword refers to the context in which a function is called. Its value can vary depending on how the function is invoked. In methods, `this` refers to the object the method is called on.

```javascript
// Example of using this
const person = {
  name: "Alice",
  greet: function() {
    console.log(`Hello, my name is ${this.name}`); // Uses this to access name
  }
};

person.greet(); // Output: Hello, my name is Alice
```

## Using Try / Catch

The `try...catch` statement allows you to handle exceptions gracefully. Code that may throw an error is placed in the `try` block, and the `catch` block handles the error if it occurs.

```javascript
// Example of using try/catch
try {
  let result = riskyFunction(); // Function that may throw an error
} catch (error) {
  console.error("An error occurred:", error.message); // Handles the error
}
```
