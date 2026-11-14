# WEB-DEV-3-ASSIGNMENT-3

# Lab 3 - Inventory Management System

A RESTful API built with **Node.js**, **Express**, and **MongoDB (Mongoose)** for managing product inventory.

---

## 🛠️ Tech Stack

- Node.js
- Express.js
- MongoDB + Mongoose
- dotenv
- nodemon (dev)

---

## 🚀 Getting Started

### 1. Install Dependencies

```bash
npm install
```

### 2. Create `.env` File

```env
MONGO_URI=your_mongodb_connection_string
PORT=5000
```

### 3. Run the Server

```bash
# Development (with auto-restart)
npm run dev

# Production
npm start
```

---

## 📦 API Endpoints

Base URL: `http://localhost:5000/api/products`

### Product CRUD

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/products` | Create a new product |
| GET | `/api/products` | Get all products (with filter, sort, pagination) |
| GET | `/api/products/:id` | Get product by ID |
| PUT | `/api/products/:id` | Update product by ID |
| DELETE | `/api/products/:id` | Delete product by ID |

### Stock Management

| Method | Endpoint | Description |
|--------|----------|-------------|
| PATCH | `/api/products/:id/stock` | Adjust stock (restock / sale) |

### Reports

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/products/reports/low-stock` | Get low stock products |
| GET | `/api/products/reports/category-summary` | Get category-wise inventory summary |

---

## 📋 Product Schema

```json
{
  "name": "Laptop",
  "sku": "LAP001",
  "category": "Electronics",
  "price": 55000,
  "quantity": 20,
  "reorderLevel": 5,
  "supplier": "Dell"
}
```

---

## 🔍 Query Parameters (GET All Products)

| Param | Description | Example |
|-------|-------------|---------|
| `category` | Filter by category | `?category=Electronics` |
| `sort` | Sort by price (`asc` / `desc`) | `?sort=asc` |
| `page` | Page number | `?page=1` |
| `limit` | Items per page | `?limit=10` |

---

## 📊 Stock Adjustment Body

```json
{
  "type": "restock",   // or "sale"
  "quantity": 10
}
```

---

## 🖼️ Testing Screenshots

Screenshots of API testing using Thunder Client are available in the `testing on thunderclient/` folder.
