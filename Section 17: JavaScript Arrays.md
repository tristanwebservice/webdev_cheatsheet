# JavaScript Arrays

## Introducing Arrays

Arrays in JavaScript are used to store multiple values in a single variable. They are ordered collections of elements, which can be of any type, including numbers, strings, objects, and even other arrays. Arrays are created using square brackets `[]`.

```javascript
// Example of creating an array
let fruits = ['apple', 'banana', 'cherry'];
```

## Array Random Access

You can access elements in an array using their index, which starts at `0`. This allows for random access to any element in the array.

```javascript
// Example of accessing array elements
console.log(fruits[0]); // Output: apple
console.log(fruits[2]); // Output: cherry
```

## Push and Pop

- **`push()`**: Adds one or more elements to the end of an array and returns the new length of the array.

    ```javascript
    // Example of push
    fruits.push('orange'); // Adds 'orange' to the end
    console.log(fruits); // Output: ['apple', 'banana', 'cherry', 'orange']
    ```

- **`pop()`**: Removes the last element from an array and returns that element.

    ```javascript
    // Example of pop
    let lastFruit = fruits.pop(); // Removes 'orange'
    console.log(lastFruit); // Output: orange
    console.log(fruits); // Output: ['apple', 'banana', 'cherry']
    ```

## Shift and Unshift

- **`shift()`**: Removes the first element from an array and returns that element.

    ```javascript
    // Example of shift
    let firstFruit = fruits.shift(); // Removes 'apple'
    console.log(firstFruit); // Output: apple
    console.log(fruits); // Output: ['banana', 'cherry']
    ```

- **`unshift()`**: Adds one or more elements to the beginning of an array and returns the new length of the array.

    ```javascript
    // Example of unshift
    fruits.unshift('kiwi'); // Adds 'kiwi' to the beginning
    console.log(fruits); // Output: ['kiwi', 'banana', 'cherry']
    ```

## Concat, IndexOf, Includes, Reverse

- **`concat()`**: Merges two or more arrays and returns a new array.

    ```javascript
    // Example of concat
    let moreFruits = ['mango', 'pineapple'];
    let allFruits = fruits.concat(moreFruits);
    console.log(allFruits); // Output: ['kiwi', 'banana', 'cherry', 'mango', 'pineapple']
    ```

- **`indexOf()`**: Returns the first index at which a specified value can be found in the array, or `-1` if it is not present.

    ```javascript
    // Example of indexOf
    console.log(allFruits.indexOf('banana')); // Output: 1
    ```

- **`includes()`**: Determines whether an array includes a certain value, returning `true` or `false`.

    ```javascript
    // Example of includes
    console.log(allFruits.includes('cherry')); // Output: true
    ```

- **`reverse()`**: Reverses the order of the elements in an array.

    ```javascript
    // Example of reverse
    allFruits.reverse();
    console.log(allFruits); // Output: ['pineapple', 'mango', 'cherry', 'banana', 'kiwi']
    ```

## Slice and Splice

- **`slice(start, end)`**: Returns a shallow copy of a portion of an array into a new array selected from `start` to `end` (not including `end`).

    ```javascript
    // Example of slice
    let citrus = allFruits.slice(1, 3); // Gets elements from index 1 to 2
    console.log(citrus); // Output: ['mango', 'cherry']
    ```

- **`splice(start, deleteCount, item1, item2, ...)`**: Changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

    ```javascript
    // Example of splice
    allFruits.splice(1, 2, 'grapefruit', 'lemon'); // Removes 2 elements and adds 2 new ones
    console.log(allFruits); // Output: ['pineapple', 'grapefruit', 'lemon', 'banana', 'kiwi']
    ```

## Reference Types and Equality Testing

Arrays are reference types in JavaScript, meaning that when you assign an array to another variable, both variables refer to the same array in memory. This can lead to unexpected behavior if not handled carefully.

```javascript
// Example of reference types
let array1 = [1, 2, 3];
let array2 = array1; // Both variables reference the same array
array2[0] = 10;
console.log(array1); // Output: [10, 2, 3]
```

## Arrays and Const

When using `const` to declare an array, you cannot reassign the array itself, but you can modify its contents (e.g., adding or removing elements).

```javascript
// Example of const with arrays
const numbers = [1, 2, 3];
numbers.push(4); // Allowed
console.log(numbers); // Output: [1, 2, 3, 4]

// numbers = [5, 6, 7]; // Not allowed, will throw an error
```

## Multi-Dimensional Arrays

Multi-dimensional arrays are arrays of arrays, allowing you to create complex data structures like matrices or grids.

```javascript
// Example of a multi-dimensional array
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

// Accessing elements in a multi-dimensional array
console.log(matrix[1][2]); // Output: 6 (second row, third column)
```
