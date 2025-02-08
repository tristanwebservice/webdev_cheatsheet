# JavaScript Object Literals

## Intro to Object Literals

Object literals are a way to define objects in JavaScript using a simple and concise syntax. An object is a collection of key-value pairs, where each key (also known as a property) is a string, and the value can be of any data type, including other objects, arrays, functions, or primitive values.

```javascript
// Example of an object literal
let person = {
  name: "Alice",
  age: 30,
  isStudent: false
};
```

## Creating Object Literals

You can create an object literal by enclosing key-value pairs in curly braces `{}`. Each key is followed by a colon and its corresponding value. Multiple key-value pairs are separated by commas.

```javascript
// Example of creating an object literal
let car = {
  make: "Toyota",
  model: "Camry",
  year: 2021,
  features: ["Air Conditioning", "Navigation", "Bluetooth"]
};
```

## Accessing Data Out of Objects

You can access the properties of an object using either dot notation or bracket notation. Dot notation is more common, while bracket notation is useful when the property name is dynamic or not a valid identifier.

```javascript
// Example of accessing object properties
console.log(person.name); // Output: Alice
console.log(car["model"]); // Output: Camry

// Accessing nested properties
console.log(car.features[1]); // Output: Navigation
```

## Modifying Objects

You can modify the properties of an object by assigning new values to existing keys or adding new key-value pairs. This allows for dynamic updates to the object's data.

```javascript
// Example of modifying object properties
person.age = 31; // Update existing property
person.isStudent = true; // Add new property
console.log(person); // Output: { name: "Alice", age: 31, isStudent: true }
```

## Nesting Arrays and Objects

Objects can contain other objects and arrays, allowing for complex data structures. This nesting enables you to represent more intricate relationships and hierarchies in your data.

```javascript
// Example of nesting arrays and objects
let school = {
  name: "Greenwood High",
  students: [
    { name: "Alice", age: 30 },
    { name: "Bob", age: 25 }
  ],
  address: {
    street: "123 Main St",
    city: "Anytown"
  }
};

// Accessing nested data
console.log(school.students[0].name); // Output: Alice
console.log(school.address.city); // Output: Anytown
```
