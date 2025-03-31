# Our First Database: MongoDB

## Intro to Databases
Databases are structured systems for storing, managing, and retrieving data. They allow applications to efficiently handle large amounts of information, ensuring data integrity and accessibility. Databases can be categorized into two main types: SQL (relational) and NoSQL (non-relational).

## SQL vs NoSQL Databases
- **SQL Databases**: These are relational databases that use structured query language (SQL) for defining and manipulating data. They are table-based and enforce a schema, which means the structure of the data must be defined before data can be inserted. Examples include MySQL, PostgreSQL, and SQLite.

- **NoSQL Databases**: These databases are designed to handle unstructured or semi-structured data. They are more flexible in terms of schema and can store data in various formats, such as key-value pairs, documents, or graphs. Examples include MongoDB, Cassandra, and Redis. NoSQL databases are often used for applications requiring high scalability and performance.

## Why We Are Learning MongoDB
MongoDB is a popular NoSQL database that stores data in a flexible, JSON-like format called BSON (Binary JSON). It is designed for scalability and performance, making it suitable for modern web applications. MongoDB's document-oriented structure allows developers to work with data in a more intuitive way, aligning closely with how data is represented in applications.

## Installing MongoDB on Linux
To install MongoDB on a Linux system, follow these steps:

1. Import the public key used by the package management system:
   ```bash
   wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
   ```

2. Create a list file for MongoDB:
   ```bash
   echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/multiverse amd64 mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
   ```

3. Reload the local package database:
   ```bash
   sudo apt-get update
   ```

4. Install the MongoDB packages:
   ```bash
   sudo apt-get install -y mongodb-org
   ```

5. Start the MongoDB service:
   ```bash
   sudo systemctl start mongod
   ```

## Note About the Mongo Shell
The Mongo shell is an interactive JavaScript interface to MongoDB. It allows you to perform database operations directly from the command line. You can access it by running the `mongo` command after starting the MongoDB service.

## The Mongo Shell
Once in the Mongo shell, you can interact with your MongoDB database using JavaScript-like syntax. You can create databases, collections, and perform CRUD (Create, Read, Update, Delete) operations.

## What on Earth is BSON
BSON (Binary JSON) is a binary representation of JSON-like documents. It is the data format used by MongoDB to store documents. BSON supports additional data types, such as `Date` and `ObjectId`, which are not available in standard JSON. This allows for more efficient storage and retrieval of data.

## Inserting with MongoDB
To insert documents into a collection, use the `insertOne()` or `insertMany()` methods.

### Example of Inserting a Document
```javascript
db.comments.insertOne({
    author: "Alice",
    text: "This is a comment",
    date: new Date()
});
```

## Finding with MongoDB
To retrieve documents from a collection, use the `find()` method. You can specify query criteria to filter results.

### Example of Finding Documents
```javascript
db.comments.find({ author: "Alice" }); // Find all comments by Alice
```

## Updating with MongoDB
To update existing documents, use the `updateOne()` or `updateMany()` methods. You can specify the criteria for the documents to update and the new values.

### Example of Updating a Document
```javascript
db.comments.updateOne(
    { author: "Alice" },
    { $set: { text: "Updated comment text" } }
);
```

## Deleting with MongoDB
To delete documents from a collection, use the `deleteOne()` or `deleteMany()` methods.

### Example of Deleting a Document
```javascript
db.comments.deleteOne({ author: "Alice" }); // Delete the first comment by Alice
```

## Additional Mongo Operators
MongoDB provides various operators to perform complex queries and updates. Some commonly used operators include:

- **Comparison Operators**: `$eq`, `$ne`, `$gt`, `$gte`, `$lt`, `$lte`
- **Logical Operators**: `$and`, `$or`, `$not`, `$nor`
- **Update Operators**: `$set`, `$unset`, `$push`, `$pull`

### Example of Using Operators
```javascript
db.comments.find({ date: { $gte: new Date('2023-01-01') } }); // Find comments from 2023 onwards
```
