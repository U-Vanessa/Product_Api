# Product Catalog API
A RESTful API built with Node.js, Express, and MongoDB that allows you to manage products, their variants, pricing, and inventory. Ideal for e-commerce or inventory systems.

## Table of Contents
Features

- Installation

- Environment Variables

- Running the Server

- API Endpoints

- Product Schema

- Error Handling

- License

### Features
- Add, update, delete, and retrieve products

- Support for product variants (e.g., size, color)

- Inventory management for both base product and variants

- Proper HTTP status codes and error messages

- Middleware for logging, JSON parsing, and CORS

- Structured code with clear routing and controllers

### Installation
```bash
git clone https://github.com/yourusername/product-catalog-api.git
cd product-catalog-api
npm install
```

### Environment Variables
``` bash
Create a .env file in the root directory and add the following:
```
PORT=3000

MONGO_URI=mongodb://localhost:27017/product-catalog

NODE_ENV=development

### Running the Server

``` bash
npm run dev
```

#### OR start normally
``` bash 
npm start
```

The API will be running at:
http://localhost:3000/api/products

### Product Schema
Each product supports the following structure:

{
  name: String (required),

  description: String,
  
  price: Number (required if no variants),
  
  category: String,
  
  inStock: Boolean,
  
  quantity: Number,
  
  variants: [
  
    {
      name: String,
      
      price: Number,
      
      stock: Number,
      
      attributes: {
      
        size: String,
      
        color: String
      
      }
    }
  ]
}

### API Endpoints
- Method	Endpoint	Description
- GET	/api/products	Get all products
- GET	/api/products/:id	Get a single product
- POST	/api/products	Create new product
- PUT	/api/products/:id	Update a product
- DELETE	/api/products/:id	Delete a product

#### Example Create Request:

POST /api/products

{
  "name": "T-Shirt",
  
  "description": "Comfortable cotton t-shirt",
  
  "category": "Apparel",
  
  "price": 15,
  
  "variants": [
    
    {
      "name": "Red - Medium",
      
      "price": 16,
      
      "stock": 50,
      
      "attributes": {
      
        "size": "M",
      
        "color": "Red"
      }
    }
  ]
}

### Error Handling
All errors are returned in the following format:

{
  "message": "Product not found"
}
The API handles:

- 404 Not Found

- 500 Internal Server Error

- Validation errors

### Project Structure

project-root/

├── controllers/

│   └── productController.js

├── routes/

│   └── productRoutes.js

├── models/

│   └── product.js

├── middlewares/

│   └── errorMiddleware.js

├── app.js

├── server.js

└── .env

### Demo Presentation
https://www.loom.com/share/2043836fbc694081b37b038c9ec38fdd?sid=af4532c2-b037-4a8a-accf-96a010ea71e2

#### License
This project is open-source and free to use under the MIT License.

#### Author
Built by Vanessa UWONKUNDA
