# Product Management API

A **Node.js & Express.js REST API** with **Role-Based Access Control (RBAC)**, JWT authentication, pagination, filtering, and CRUD operations for products.

---

## Features
- User Authentication (JWT)
- Role-Based Access Control: `admin`, `user`
- CRUD operations for products
- Pagination & filtering
- Password hashing (bcrypt)
- Middleware: logger, error handler, role check

---

## Project Structure
product-api/
├── package.json
├── README.md
└── src/
├── server.js
├── app.js
├── database/memory.js
├── models/
├── middleware/
│ ├── auth.js
│ ├── role.js
│ ├── logger.js
│ ├── 404handler.js
│ └── errorHandler.js
├── routes/
│ ├── userRoutes.js
│ └── productRoutes.js
└── controllers/
├── userController.js
└── productController.js


---

## Environment Variables


PORT=5000
JWT_SECRET=mysecret123


---

## API Endpoints

### Users
| Endpoint   | Method | Auth |
|------------|--------|------|
| /register  | POST   | No   |
| /login     | POST   | No   |
| /profile   | GET    | Yes  |

### Products
| Endpoint         | Method | Role           |
|-----------------|--------|----------------|
| /products       | GET    | admin, user    |
| /products/:id   | GET    | admin, user    |
| /products       | POST   | admin          |
| /products/:id   | PUT    | admin          |
| /products/:id   | DELETE| admin          |

---

## Pagination & Filtering
- Query params: `page`, `limit`, `category`, `minPrice`, `maxPrice`, `search`  
- Example: `/products?search=phone&category=mobile&page=2&limit=5`

---

## RBAC & Authentication
- **JWT Auth:** verifies user identity  
- **Role Middleware:** checks allowed roles, returns 403 if unauthorized  

---

## Middleware
- Logger: logs HTTP requests  
- 404 Handler: returns clean `404`  
- Error Handler: global error response

---

## Testing
- Manual: Postman / Thunder Client  
- Automated: Jest + Supertest  
- Covers controllers, auth, RBAC, pagination, filtering

---

## Setup
```bash
npm install
npm install --save-dev nodemon
npm run dev      # dev server
npm start        # production

GitHub Upload
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/product-api.git
git branch -M main
git push -u origin main


MIT License


This is compact enough to fit **on a single “slide” or GitHub page** while including all necessary details.  

If you want, I can also make an **even shorter “one-page cheat sheet version”** for quick reference. Do you want me to do that?
