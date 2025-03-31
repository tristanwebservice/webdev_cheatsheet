# Defining RESTful Routes

## GET vs POST Requests
In HTTP, GET and POST are two commonly used request methods. 

- **GET Requests**: Used to retrieve data from the server. They are idempotent, meaning multiple identical requests will have the same effect as a single request. GET requests can include query parameters in the URL.
  
- **POST Requests**: Used to send data to the server to create or update a resource. POST requests are not idempotent, as each request can result in a different outcome (e.g., creating a new resource).

## Defining Express POST Routes
In Express, you can define POST routes using `app.post()`. This method handles incoming POST requests to a specified path.

### Example of Defining a POST Route
```javascript
app.post('/comments', (req, res) => {
    // Logic to create a new comment
    res.send('Comment created!');
});
```

## Parsing the Request Body
To handle incoming request data, you need to parse the request body. Express provides middleware to parse JSON and URL-encoded data.

### Example of Parsing Request Body
```javascript
const bodyParser = require('body-parser');

// Middleware to parse JSON bodies
app.use(bodyParser.json());
// Middleware to parse URL-encoded bodies
app.use(bodyParser.urlencoded({ extended: true }));
```

## Intro to REST
REST (Representational State Transfer) is an architectural style for designing networked applications. It relies on stateless communication and standard HTTP methods (GET, POST, PUT, DELETE) to perform CRUD (Create, Read, Update, Delete) operations on resources.

## RESTful Comments Overview
In a RESTful application, comments can be managed through a set of routes that correspond to the CRUD operations. Each route will handle a specific action related to comments.

## RESTful Comments Index
The index route retrieves a list of all comments. This is typically a GET request.

### Example of Comments Index Route
```javascript
app.get('/comments', (req, res) => {
    // Logic to retrieve all comments
    res.send('List of comments');
});
```

## RESTful Comments New
The new route typically serves a form for creating a new comment. This is often a GET request.

### Example of Comments New Route
```javascript
app.get('/comments/new', (req, res) => {
    res.send('Form to create a new comment');
});
```

## Express Redirects
Express allows you to redirect users to different routes using `res.redirect()`. This is useful for guiding users after certain actions, such as creating or updating resources.

### Example of Redirecting
```javascript
app.post('/comments', (req, res) => {
    // Logic to create a new comment
    res.redirect('/comments'); // Redirect to the comments index
});
```

## RESTful Comments Show
The show route retrieves a specific comment based on its ID. This is typically a GET request with a path parameter.

### Example of Comments Show Route
```javascript
app.get('/comments/:id', (req, res) => {
    const commentId = req.params.id;
    // Logic to retrieve the comment by ID
    res.send(`Showing comment with ID: ${commentId}`);
});
```

## The UUID Package
The UUID package is used to generate unique identifiers for resources. This is particularly useful for assigning unique IDs to comments.

### Example of Using UUID
```bash
npm install uuid
```

```javascript
const { v4: uuidv4 } = require('uuid');

app.post('/comments', (req, res) => {
    const newComment = {
        id: uuidv4(), // Generate a unique ID
        text: req.body.text
    };
    // Logic to save the new comment
    res.redirect('/comments');
});
```

## RESTful Comments Update
The update route modifies an existing comment. This is typically a PUT or PATCH request.

### Example of Comments Update Route
```javascript
app.put('/comments/:id', (req, res) => {
    const commentId = req.params.id;
    // Logic to update the comment by ID
    res.send(`Updated comment with ID: ${commentId}`);
});
```

## Express Method Override
To support PUT and DELETE requests from HTML forms (which only support GET and POST), you can use the `method-override` middleware.

### Example of Using Method Override
```bash
npm install method-override
```

```javascript
const methodOverride = require('method-override');

// Middleware to override methods
app.use(methodOverride('_method'));
```

## RESTful Comments Delete
The delete route removes a specific comment based on its ID. This is typically a DELETE request.

### Example of Comments Delete Route
```javascript
app.delete('/comments/:id', (req, res) => {
    const commentId = req.params.id;
    // Logic to delete the comment by ID
    res.send(`Deleted comment with ID: ${commentId}`);
});
```
