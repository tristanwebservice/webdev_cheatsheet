# Exploring Modules and the npm Universe

## Working with `module.exports`
In Node.js, `module.exports` is used to export functions, objects, or variables from a module so that they can be used in other files. By default, each file in Node.js is treated as a separate module. Here’s an example of how to use `module.exports`:

```javascript
// math.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

// Exporting functions
module.exports = {
    add,
    subtract
};
```

You can then import this module in another file using `require`:

```javascript
// app.js
const math = require('./math');

console.log(math.add(5, 3)); // Outputs: 8
console.log(math.subtract(5, 3)); // Outputs: 2
```

## Requiring a Directory
When requiring a directory, Node.js looks for an `index.js` file within that directory by default. This allows you to organize your modules neatly. For example, if you have a directory structure like this:

```
/utils
  ├── index.js
  └── math.js
```

You can require the `utils` directory, and it will automatically use `index.js`:

```javascript
// utils/index.js
const math = require('./math');

module.exports = {
    math
};

// app.js
const utils = require('./utils');

console.log(utils.math.add(5, 3)); // Outputs: 8
```

## Introducing npm
npm (Node Package Manager) is the default package manager for Node.js. It allows developers to install, share, and manage dependencies for their projects. npm hosts a vast repository of open-source packages that can be easily integrated into applications.

## Installing Packages
To install a package using npm, you can use the following command in your terminal:

```bash
npm install package-name
```

This command installs the specified package and adds it to the `node_modules` directory in your project. For example:

```bash
npm install express
```

## Adding Global Packages
Global packages are installed system-wide and can be used from any project. To install a package globally, use the `-g` flag:

```bash
npm install -g package-name
```

For example, to install the `nodemon` package globally:

```bash
npm install -g nodemon
```

This allows you to run `nodemon` from the command line in any project.

## The All-Important `package.json`
The `package.json` file is a crucial part of any Node.js project. It contains metadata about the project, including its name, version, description, scripts, and dependencies. You can create a `package.json` file by running:

```bash
npm init
```

This command will prompt you to enter details about your project. You can also use `npm init -y` to create a default `package.json` file with default values.

### Example of `package.json`
```json
{
    "name": "my-project",
    "version": "1.0.0",
    "description": "A sample Node.js project",
    "main": "app.js",
    "scripts": {
        "start": "node app.js"
    },
    "dependencies": {
        "express": "^4.17.1"
    }
}
```

## Installing All Dependencies for a Project
To install all dependencies listed in the `package.json` file, simply run:

```bash
npm install
```

This command reads the `package.json` file and installs all the required packages into the `node_modules` directory. This is particularly useful when cloning a project from a repository, as it ensures that all necessary dependencies are installed.
