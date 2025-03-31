# AJAX and APIs

## Introduction to AJAX
AJAX (Asynchronous JavaScript and XML) is a technique used to create asynchronous web applications. It allows web pages to communicate with servers and update content without reloading the entire page. This enhances user experience by making applications more dynamic and responsive.

## Introduction to APIs
APIs (Application Programming Interfaces) are sets of rules and protocols that allow different software applications to communicate with each other. They enable developers to access the functionality or data of other applications, services, or platforms, facilitating integration and data exchange.

## What is JSON?
JSON (JavaScript Object Notation) is a lightweight data interchange format that is easy for humans to read and write and easy for machines to parse and generate. It is commonly used for transmitting data between a server and a web application. A typical JSON structure looks like this:

```json
{
    "name": "John Doe",
    "age": 30,
    "isStudent": false
}
```

## Using Hoppscotch or Postman to Practice
Hoppscotch and Postman are tools that allow developers to test APIs by sending requests and viewing responses. They provide a user-friendly interface to experiment with different HTTP methods, headers, and body content, making it easier to understand how APIs work.

## HTTP Verbs
HTTP verbs (or methods) define the action to be performed on a resource. The most common HTTP verbs include:

- **GET**: Retrieve data from a server.
- **POST**: Send data to a server to create a new resource.
- **PUT**: Update an existing resource.
- **DELETE**: Remove a resource from the server.

## HTTP Status Codes
HTTP status codes indicate the result of an HTTP request. Common status codes include:

- **200 OK**: The request was successful.
- **201 Created**: A resource was successfully created.
- **400 Bad Request**: The server could not understand the request.
- **404 Not Found**: The requested resource could not be found.
- **500 Internal Server Error**: The server encountered an error.

## Understanding Query Strings
Query strings are a part of the URL that contains data to be sent to the server. They follow the `?` character and consist of key-value pairs separated by `&`. For example:

```
https://example.com/api/users?age=30&name=John
```

In this example, `age` and `name` are query parameters.

## HTTP Headers
HTTP headers provide additional information about the request or response. They can include metadata such as content type, authorization tokens, and caching policies. Common headers include:

- **Content-Type**: Indicates the media type of the resource (e.g., `application/json`).
- **Authorization**: Contains credentials for authenticating the client.

## Making XHRs
XMLHttpRequest (XHR) is a JavaScript object that allows you to make HTTP requests to servers. Here’s an example of making a GET request using XHR:

```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onload = function() {
    if (xhr.status === 200) {
        console.log(JSON.parse(xhr.responseText)); // Handle the response
    }
};
xhr.send();
```

## Using the Fetch API
The Fetch API is a modern alternative to XHR for making HTTP requests. It returns a promise that resolves to the response. Here’s an example of a GET request using Fetch:

```javascript
fetch('https://api.example.com/data')
    .then((response) => {
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        return response.json(); // Parse JSON response
    })
    .then((data) => {
        console.log(data); // Handle the data
    })
    .catch((error) => {
        console.error('Fetch error:', error);
    });
```

## Introducing Axios
Axios is a popular JavaScript library for making HTTP requests. It simplifies the process of sending requests and handling responses. Axios automatically transforms JSON data and provides a clean API. Here’s an example of a GET request using Axios:

```javascript
axios.get('https://api.example.com/data')
    .then((response) => {
        console.log(response.data); // Handle the data
    })
    .catch((error) => {
        console.error('Axios error:', error);
    });
```

## Setting Headers with Axios
You can easily set custom headers in Axios requests. Here’s how to include headers in a request:

```javascript
axios.get('https://api.example.com/data', {
    headers: {
        'Authorization': 'Bearer your_token_here',
        'Content-Type': 'application/json'
    }
})
    .then((response) => {
        console.log(response.data); // Handle the data
    })
    .catch((error) => {
        console.error('Axios error:', error);
    });
```
