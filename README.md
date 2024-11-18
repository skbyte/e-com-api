# E-commerce API (Express & Node.js)

## Overview

This is a RESTful server application built with Node.js and Express.js. It manages users, products, orders, and reviews, integrating features like authentication, database operations, and file uploads. The application follows a modular architecture for scalability and ease of maintenance.

---

## Features

1. **User Management**:
   - User authentication and authorization (JWT-based).
   - CRUD operations for users.
   - Password update functionality.

2. **Product Management**:
   - Create, read, update, and delete products.
   - Image uploads with validation.

3. **Order Management**:
   - Create orders with tax and shipping calculations.
   - View and update order details.
   - Filter orders by user.

4. **Security**:
   - Implemented secure headers using `helmet`.
   - Input sanitization with `xss-clean` and `express-mongo-sanitize`.
   - Rate limiting to prevent abuse.
   - Cross-Origin Resource Sharing (CORS) support.

5. **Performance Enhancements**:
   - Middleware-based modularity.
   - Async error handling.

6. **Database**:
   - MongoDB integration using Mongoose.

---

## Installation

1. Clone the repository:
```bash
   git clone <repository-url>
   cd <repository-folder>
```  
2. Install dependencies:
```bash
  npm install
```

3. Create a .env file with the following environment variables:
```env
PORT=5000
MONGO_URL=<your-mongo-db-url>
JWT_SECRET=<your-jwt-secret>
JWT_LIFETIME=<jwt-lifetime>
```
4. Start the server:

```bash
npm start
```
## API Endpoints
### Authentication
- POST `/api/v1/auth/register` - Register a new user.
- POST `/api/v1/auth/login` - Log in an existing user.
- GET `/api/v1/auth/logout` - Log out a user.
### Users
- GET `/api/v1/users` - Get all users (admin only).
- GET `/api/v1/users/:id` - Get a specific user by ID.
- PATCH `/api/v1/users/update` - Update user details.
- PATCH `/api/v1/users/update-password` - Update user password.
### Products
- POST `/api/v1/products` - Create a new product.
- GET `/api/v1/products` - Retrieve all products.
- GET `/api/v1/products/:id` - Retrieve a specific product.
- PATCH `/api/v1/products/:id` - Update product details.
- DELETE `/api/v1/products/:id` - Delete a product.
- POST `/api/v1/products/upload` - Upload product images.
### Orders
- POST `/api/v1/orders` - Create a new order.
- GET `/api/v1/orders` - Retrieve all orders.
- GET `/api/v1/orders/:id` - Retrieve a specific order.
- PATCH `/api/v1/orders/:id` - Update an order.
### Middleware Used
- Security: helmet, xss-clean, express-mongo-sanitize
- File Handling: express-fileupload
- Logging: morgan
- Error Handling: Custom error-handling middleware.
## Development Setup
- Run the server locally:
```bash
npm run dev
```
- Access the API at `http://localhost:<PORT>`.
## Future Enhancements
- Integration with a real payment gateway.
- Advanced filtering and sorting for products.
- Improved test coverage.
