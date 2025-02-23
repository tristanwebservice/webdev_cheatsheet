# Callbacks & Array Methods 

## What's This About?

Callbacks are functions that are passed as arguments to other functions and are executed after a certain event or condition is met. They are commonly used in asynchronous programming and array methods to handle operations on data collections.

## The forEach Method

The `forEach` method executes a provided function once for each array element. It is useful for iterating over arrays without returning a new array.

```javascript
// Example of forEach method
let numbers = [1, 2, 3, 4];
numbers.forEach(function(num) {
  console.log(num * 2); // Output: 2, 4, 6, 8
});
```

## Map Method

The `map` method creates a new array populated with the results of calling a provided function on every element in the calling array. It is often used for transforming data.

```javascript
// Example of map method
let doubled = numbers.map(function(num) {
  return num * 2; // Returns a new array with doubled values
});
console.log(doubled); // Output: [2, 4, 6, 8]
```

## Arrow Functions

Arrow functions provide a more concise syntax for writing function expressions. They are defined using the `=>` syntax and do not have their own `this` context.

```javascript
// Example of an arrow function
let add = (a, b) => a + b; // Concise arrow function
console.log(add(2, 3)); // Output: 5
```

## Arrow Function Implicit Returns

If an arrow function consists of a single expression, you can omit the curly braces and the `return` keyword. The result of the expression is returned implicitly.

```javascript
// Example of implicit return
let square = x => x * x; // Implicit return
console.log(square(4)); // Output: 16
```

## Arrow Functions Wrap-Up

Arrow functions are particularly useful for writing shorter and cleaner code, especially when used with array methods. However, they should be used with caution when dealing with methods that require their own `this` context.

## Set Timeout and Set Interval

- **`setTimeout`**: Executes a function after a specified delay (in milliseconds). It is often used for delaying actions.

    ```javascript
    // Example of setTimeout
    setTimeout(() => {
      console.log("Executed after 2 seconds");
    }, 2000); // Output: Executed after 2 seconds (after 2 seconds)
    ```

- **`setInterval`**: Repeatedly executes a function at specified intervals (in milliseconds) until cleared.

    ```javascript
    // Example of setInterval
    let count = 0;
    const intervalId = setInterval(() => {
      console.log(count++);
      if (count > 5) clearInterval(intervalId); // Stops after 5 iterations
    }, 1000); // Output: 0, 1, 2, 3, 4, 5 (one per second)
    ```

## The Filter Method

The `filter` method creates a new array with all elements that pass the test implemented by the provided function. It is useful for filtering data based on specific criteria.

```javascript
// Example of filter method
let evenNumbers = numbers.filter(num => num % 2 === 0); // Filters even numbers
console.log(evenNumbers); // Output: [2, 4]
```

## Some and Every Methods

- **`some`**: Tests whether at least one element in the array passes the test implemented by the provided function. Returns `true` or `false`.

    ```javascript
    // Example of some method
    let hasEven = numbers.some(num => num % 2 === 0); // Checks for even numbers
    console.log(hasEven); // Output: true
    ```

- **`every`**: Tests whether all elements in the array pass the test implemented by the provided function. Returns `true` or `false`.

    ```javascript
    // Example of every method
    let allEven = numbers.every(num => num % 2 === 0); // Checks if all are even
    console.log(allEven); // Output: false
    ```

## The Reduce Method

The `reduce` method executes a reducer function on each element of the array, resulting in a single output value. It is often used for accumulating values.

```javascript
// Example of reduce method
let sum = numbers.reduce((accumulator, current) => accumulator + current, 0); // Sums all numbers
console.log(sum); // Output: 10
```

## Arrow Functions & This Keyword

Arrow functions do not have their own `this` context; they inherit `this` from the enclosing lexical scope. This behavior is particularly useful in scenarios where you want to maintain the context of `this` in callbacks.

```javascript
// Example of arrow functions and this
const obj = {
  value: 42,
  getValue: function() {
    setTimeout(() => {
      console.log(this.value); // 'this' refers to obj
    }, 1000);
  }
};

obj.getValue(); // Output: 42 (after 1 second)
```
