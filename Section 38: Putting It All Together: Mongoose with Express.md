# Putting It All Together: Mongoose with Express

## Express and Mongoose Basic Setup
To integrate Mongoose with Express, you first need to set up an Express application and connect it to a MongoDB database using Mongoose. Here’s a basic setup:

1. **Install Dependencies**:
   ```bash
   npm install express mongoose body-parser
   ```

2. **Basic Express and Mongoose Setup**:
   ```javascript
   const express = require('express');
   const mongoose = require('mongoose');
   const bodyParser = require('body-parser');

   const app = express();
   const PORT = 3000;

   // Connect to MongoDB
   mongoose.connect('mongodb://localhost:27017/mydatabase', {
       useNewUrlParser: true,
       useUnifiedTopology: true
   })
   .then(() => console.log('MongoDB connected'))
   .catch(err => console.error('Connection error:', err));

   // Middleware
   app.use(bodyParser.json());
   app.use(bodyParser.urlencoded({ extended: true }));

   app.listen(PORT, () => {
       console.log(`Server is running on http://localhost:${PORT}`);
   });
   ```

## Creating Our Model
Define a Mongoose model for the products. This model will represent the structure of the product documents in the MongoDB collection.

### Example of Product Model
```javascript
const productSchema = new mongoose.Schema({
    name: { type: String, required: true },
    price: { type: Number, required: true },
    category: { type: String, required: true },
    description: String
});

const Product = mongoose.model('Product', productSchema);
```

## Products Index
Create a route to display all products. This route will retrieve all product documents from the database and send them as a response.

### Example of Products Index Route
```javascript
app.get('/products', (req, res) => {
    Product.find()
        .then(products => res.json(products))
        .catch(err => res.status(500).json({ error: err.message }));
});
```

## Product Details
Create a route to display details of a specific product based on its ID. This route will retrieve a single product document.

### Example of Product Details Route
```javascript
app.get('/products/:id', (req, res) => {
    Product.findById(req.params.id)
        .then(product => {
            if (!product) {
                return res.status(404).json({ error: 'Product not found' });
            }
            res.json(product);
        })
        .catch(err => res.status(500).json({ error: err.message }));
});
```

## Creating Products
Create a route to handle the creation of new products. This route will accept product data from the request body and save it to the database.

### Example of Creating Products Route
```javascript
app.post('/products', (req, res) => {
    const newProduct = new Product(req.body);
    newProduct.save()
        .then(() => res.status(201).json(newProduct))
        .catch(err => res.status(400).json({ error: err.message }));
});
```

## Updating Products
Create a route to update an existing product. This route will accept the product ID and the updated data.

### Example of Updating Products Route
```javascript
app.put('/products/:id', (req, res) => {
    Product.findByIdAndUpdate(req.params.id, req.body, { new: true })
        .then(updatedProduct => {
            if (!updatedProduct) {
                return res.status(404).json({ error: 'Product not found' });
            }
            res.json(updatedProduct);
        })
        .catch(err => res.status(400).json({ error: err.message }));
});
```

## Tangent on Category Selector
When creating or updating products, you may want to include a category selector in your forms. This can be implemented in the front-end to allow users to select a category from predefined options.

### Example of Category Selector in HTML
```html
<select name="category">
    <option value="electronics">Electronics</option>
    <option value="clothing">Clothing</option>
    <option value="books">Books</option>
</select>
```

## Deleting Products
Create a route to delete a product based on its ID. This route will remove the specified product from the database.

### Example of Deleting Products Route
```javascript
app.delete('/products/:id', (req, res) => {
    Product.findByIdAndDelete(req.params.id)
        .then(deletedProduct => {
            if (!deletedProduct) {
                return res.status(404).json({ error: 'Product not found' });
            }
            res.json({ message: 'Product deleted successfully' });
        })
        .catch(err => res.status(500).json({ error: err.message }));
});
```

## Filtering by Category
Create a route to filter products by category. This route will accept a category parameter and return products that match the specified category.

### Example of Filtering by Category Route
```javascript
app.get('/products/category/:category', (req, res) => {
    Product.find({ category: req.params.category })
        .then(products => res.json(products))
        .catch(err => res.status(500).json({ error: err.message }));
});
```
