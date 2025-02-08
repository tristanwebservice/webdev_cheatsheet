# JavaScript Decision Making

## Decision Making and Coding

Decision making in programming involves using conditional statements to execute different code paths based on certain conditions. This allows developers to create dynamic and responsive applications that can react to user input and other variables.

## Comparison Operators

Comparison operators are used to compare two values and return a Boolean result (`true` or `false`). Common comparison operators include:

- **`==`**: Equal to
- **`!=`**: Not equal to
- **`>`**: Greater than
- **`<`**: Less than
- **`>=`**: Greater than or equal to
- **`<=`**: Less than or equal to

```javascript
// Example of comparison operators
let a = 5;
let b = 10;
console.log(a < b); // Output: true
```

## Equality: Triple vs Double Equals

JavaScript provides two types of equality operators:

- **Double Equals (`==`)**: Compares values for equality after performing type coercion. This means it converts the values to a common type before comparison.

    ```javascript
    console.log(5 == '5'); // Output: true (type coercion occurs)
    ```

- **Triple Equals (`===`)**: Compares both value and type without type coercion. This is generally recommended for strict equality checks.

    ```javascript
    console.log(5 === '5'); // Output: false (no type coercion)
    ```

## Console, Alert, and Prompt

JavaScript provides several methods for interacting with users:

- **`console.log()`**: Outputs messages to the web console, useful for debugging.

    ```javascript
    console.log("Hello, World!"); // Output: Hello, World!
    ```

- **`alert()`**: Displays an alert dialog with a specified message.

    ```javascript
    alert("This is an alert!"); // Displays an alert box
    ```

- **`prompt()`**: Displays a dialog that prompts the user for input.

    ```javascript
    let userInput = prompt("Enter your name:");
    console.log(userInput); // Outputs the user's input
    ```

## Running JS from a Script

JavaScript can be executed in a web page by including it in a `<script>` tag. This can be done inline or by linking to an external JavaScript file.

```html
<!-- Example of running JS from a script -->
<script>
  console.log("JavaScript is running!");
</script>

<!-- Linking to an external JS file -->
<script src="script.js"></script>
```

## If Statements

The `if` statement executes a block of code if a specified condition is true.

```javascript
// Example of an if statement
let age = 18;
if (age >= 18) {
  console.log("You are an adult."); // Output: You are an adult.
}
```

## Else If

The `else if` statement allows you to check multiple conditions. If the first condition is false, it checks the next condition.

```javascript
// Example of else if
let score = 85;
if (score >= 90) {
  console.log("Grade: A");
} else if (score >= 80) {
  console.log("Grade: B"); // Output: Grade: B
} else {
  console.log("Grade: C or lower");
}
```

## Else

The `else` statement executes a block of code if none of the preceding conditions are true.

```javascript
// Example of else
let temperature = 30;
if (temperature > 30) {
  console.log("It's hot outside.");
} else {
  console.log("It's not hot outside."); // Output: It's not hot outside.
}
```

## Nesting Conditionals

You can nest conditional statements within each other to create more complex decision-making structures.

```javascript
// Example of nesting conditionals
let num = 10;
if (num > 0) {
  if (num % 2 === 0) {
    console.log("Positive even number."); // Output: Positive even number.
  } else {
    console.log("Positive odd number.");
  }
} else {
  console.log("Not a positive number.");
}
```

## Truthy and Falsy Values

In JavaScript, certain values are considered "falsy," meaning they evaluate to `false` in a Boolean context. These include:

- `false`
- `0`
- `""` (empty string)
- `null`
- `undefined`
- `NaN` (Not-a-Number)

All other values are considered "truthy."

```javascript
// Example of truthy and falsy values
let value = 0;
if (value) {
  console.log("This is truthy.");
} else {
  console.log("This is falsy."); // Output: This is falsy.
}
```

## Logical OR

The logical OR operator (`||`) returns `true` if at least one of the operands is true.

```javascript
// Example of logical OR
let x = 5;
let y = 10;
if (x > 0 || y > 0) {
  console.log("At least one number is positive."); // Output: At least one number is positive.
}
```

## Logical NOT

The logical NOT operator (`!`) negates a Boolean value. If the value is true, it returns false, and vice versa.

```javascript
// Example of logical NOT
let isRaining = false;
if (!isRaining) {
  console.log("It's not raining."); // Output: It's not raining.
}
```

## The Switch Statement

The `switch` statement is a control structure that allows you to execute different blocks of code based on the value of a variable. It is often used as an alternative to multiple `if` statements.

```javascript
// Example of a switch statement
let fruit = "apple";
switch (fruit) {
  case "banana":
    console.log("It's a banana.");
    break;
  case "apple":
    console.log("It's an apple."); // Output: It's an apple.
    break;
  default:
    console.log("Unknown fruit.");
}
```
