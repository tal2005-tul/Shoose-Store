# Shoose Store

A full-stack online shoe store, built as a final project during my studies.
Customers can browse products by category, add items to a cart and place orders.
An admin can add, edit and remove products.

## Tech stack

**Backend:** Node.js, Express, MySQL (mysql2), JWT, bcryptjs
**Frontend:** React 18, Vite, Redux Toolkit, React Router, React Hook Form, Material UI, Axios

## Features

- User registration and login, with passwords hashed using bcrypt
- JWT authentication with token expiration
- Role-based access: only an admin can add, update or delete products and view users
- Product catalog with categories and pagination
- Shopping cart managed with Redux Toolkit
- Checkout and order creation, including an estimated delivery date
- Soft delete for products (deactivated instead of removed from the database)

## Project structure

    Shoose-Store/
    ├── backend/
    │   ├── app.js         # Express server setup
    │   ├── router/        # Route definitions
    │   ├── controller/    # Request handling and business logic
    │   ├── db/            # MySQL connection pool
    │   └── utils/         # JWT helpers and auth middleware
    └── fronted/           # React + Vite client

## Running locally

Requires Node.js and a MySQL database with the tables
`users`, `products`, `category`, `orders` and `prodfororder`.

**Backend**

    cd Shoose-Store/backend
    npm install

Create a `.env` file in the `backend` folder:

    PORT=5003
    DB_HOST=localhost
    DB_USER=your_user
    DB_PASSWORD=your_password
    DB_NAME=your_database
    SECRET_KEY=your_secret

Then run:

    node app.js

**Frontend**

    cd Shoose-Store/fronted
    npm install
    npm run dev

## Planned improvements

- Use parameterized queries (prepared statements) in all SQL calls, to prevent SQL injection
- Protect the order routes with authentication middleware
- Return the correct 403 status code from the admin middleware
- Add a `schema.sql` file so the database can be created in one step
