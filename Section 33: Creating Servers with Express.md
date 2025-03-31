# Creating Servers with Express

## Introducing Express
Express is a minimal and flexible Node.js web application framework that provides a robust set of features for building web and mobile applications. It simplifies the process of creating server-side applications by providing a straightforward API for handling requests, responses, and middleware.

## Our Very First Express App
To create a basic Express application, you first need to install Express using npm:

```bash
npm install express
```

Then, you can create a simple server:

```javascript
// app.js
const express = require('express');
const app = express();
const PORT = 3000;

// Define a basic route
app.get('/', (req, res) => {
    res.send('Hello, Express!');
});

// Start the server
app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});
```

This code sets up a server that listens on port 3000 and responds with "Hello, Express!" when the root URL is accessed.

## The Request and Response Objects
In Express, the request (`req`) and response (`res`) objects are fundamental to handling HTTP requests and sending responses. The `req` object contains information about the incoming request, such as headers, query parameters, and body data. The `res` object is used to send a response back to the client.

### Example of Using Request and Response Objects
```javascript
app.get('/greet', (req, res) => {
    const name = req.query.name || 'Guest'; // Get name from query string
    res.send(`Hello, ${name}!`); // Send personalized greeting
});
```

## Important Note: Solving a Potential Error with the Start * Catch-All Route
To handle potential errors and ensure that all routes are covered, you can implement a catch-all route at the end of your route definitions. This route will catch any requests that do not match existing routes:

```javascript
app.get('*', (req, res) => {
    res.status(404).send('404 Not Found'); // Handle 404 errors
});
```

This ensures that users receive a proper response if they navigate to an undefined route.

## Express Routing Basics
Express routing allows you to define multiple routes for different HTTP methods and paths. You can use `app.get()`, `app.post()`, `app.put()`, and `app.delete()` to handle different types of requests.

### Example of Defining Multiple Routes
```javascript
app.get('/about', (req, res) => {
    res.send('About Us');
});

app.post('/submit', (req, res) => {
    res.send('Form submitted!');
});
```

## Express Path Parameters
Path parameters allow you to capture values from the URL. You can define parameters in your route paths using a colon (`:`) followed by the parameter name.

### Example of Using Path Parameters
```javascript
app.get('/users/:id', (req, res) => {
    const userId = req.params.id; // Access the path parameter
    res.send(`User ID: ${userId}`);
});
```

In this example, if a user accesses `/users/123`, the response will be "User ID: 123".

## Working with Query Strings
Query strings are used to pass additional parameters in the URL. You can access query parameters using `req.query`.

### Example of Handling Query Strings
```javascript
app.get('/search', (req, res) => {
    const query = req.query.q; // Get the search query
    res.send(`Search results for: ${query}`);
});
```

If a user accesses `/search?q=express`, the response will be "Search results for: express".

## Auto Restart with Nodemon
Nodemon is a utility that automatically restarts your Node.js application when file changes are detected. This is particularly useful during development. To install Nodemon globally, run:

```bash
npm install -g nodemon
```

You can then start your Express app with Nodemon:

```bash
nodemon app.js
```

This way, any changes you make to your code will automatically restart the server, saving you time during development.
