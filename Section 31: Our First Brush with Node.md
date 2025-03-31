# Our First Brush with Node

## Introduction to Node.js
Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It allows developers to execute JavaScript code on the server side, enabling the creation of scalable and high-performance applications. Node.js uses an event-driven, non-blocking I/O model, making it efficient for handling multiple connections simultaneously.

## What is Node Used For
Node.js is commonly used for building:

- **Web servers**: Creating RESTful APIs and serving web applications.
- **Real-time applications**: Such as chat applications and online gaming.
- **Microservices**: Developing small, independent services that communicate over a network.
- **Command-line tools**: Automating tasks and building scripts.
- **Data streaming applications**: Processing data in real-time.

## Installing Node
To install Node.js, follow these steps:

1. Visit the [Node.js official website](https://nodejs.org/).
2. Download the installer for your operating system (Windows, macOS, or Linux).
3. Run the installer and follow the prompts to complete the installation.
4. Verify the installation by running the following command in your terminal:

```bash
node -v
```

This command should display the installed version of Node.js.

## The Node REPL
The Node REPL (Read-Eval-Print Loop) is an interactive shell that allows you to execute JavaScript code in real-time. To start the REPL, simply type `node` in your terminal:

```bash
node
```

You can then enter JavaScript expressions, and the REPL will evaluate and return the results immediately. For example:

```javascript
> console.log('Hello, Node.js!');
Hello, Node.js!
```

## Running Node Files
To run a JavaScript file using Node.js, create a `.js` file and use the following command in your terminal:

```bash
node filename.js
```

For example, if you have a file named `app.js`, you can run it with:

```bash
node app.js
```

## `process` and `argv`
The `process` object is a global object in Node.js that provides information about the current Node.js process. The `argv` property is an array that contains the command-line arguments passed when the Node.js process was launched.

```javascript
// app.js
console.log(process.argv);
```

When you run the file with additional arguments:

```bash
node app.js arg1 arg2
```

The output will include the Node.js executable path, the script path, and the arguments:

```
[
  '/path/to/node',
  '/path/to/app.js',
  'arg1',
  'arg2'
]
```

## File System Module Crash Course
The File System (fs) module in Node.js allows you to interact with the file system. It provides methods to read, write, and manipulate files and directories. Here’s a quick overview of some common operations:

### Importing the File System Module
To use the fs module, you need to require it in your script:

```javascript
const fs = require('fs');
```

### Reading a File
You can read a file asynchronously using `fs.readFile`:

```javascript
fs.readFile('example.txt', 'utf8', (err, data) => {
    if (err) {
        console.error('Error reading file:', err);
        return;
    }
    console.log('File content:', data);
});
```

### Writing to a File
To write data to a file, use `fs.writeFile`:

```javascript
fs.writeFile('output.txt', 'Hello, Node.js!', (err) => {
    if (err) {
        console.error('Error writing file:', err);
        return;
    }
    console.log('File written successfully!');
});
```

### Appending to a File
You can append data to an existing file using `fs.appendFile`:

```javascript
fs.appendFile('output.txt', '\nAppending this line.', (err) => {
    if (err) {
        console.error('Error appending to file:', err);
        return;
    }
    console.log('Data appended successfully!');
});
```
