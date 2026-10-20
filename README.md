## 📡 API Endpoints

**Base URL:** `https://YOUR-RENDER-URL.onrender.com`

All endpoints use the **GET** HTTP method and return JSON responses.

### Products

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/products` | Get all products |
| `GET` | `/products/:id` | Get a single product by its UUID |
| `GET` | `/products?category=Men%27s%20Sneaker` | Filter products by category |
| `GET` | `/products?name%3Acontains=ultraboost` | Search products by name containing `ultraboost` |
| `GET` | `/products?_page=1&_per_page=10` | Get the first page of products (10 per page) |
| `GET` | `/products?_sort=price` | Sort products by price in ascending order |
| `GET` | `/products?_sort=-price` | Sort products by price in descending order |

### Example Requests

**1. Get all products**
```http
GET /products
```

**2. Get a product by ID**

Replace `YOUR_PRODUCT_UUID` with an actual product ID from the API.

```http
GET /products/YOUR_PRODUCT_UUID
```

**3. Filter by category**
```http
GET /products?category=Men%27s%20Sneaker
```

**4. Search by product name**
```http
GET /products?name%3Acontains=ultraboost
```

**5. Pagination**
```http
GET /products?_page=1&_per_page=10
```

**6. Sort by price**
```http
GET /products?_sort=price
```

### Response Format

A successful request returns JSON data. For example:

```json
[
  {
    "id": "your-product-uuid",
    "name": "Example Product",
    "category": "Men's Sneaker",
    "price": 1299
  }
]
```

*The response fields depend on the product records stored in `db.json`.*

### Error Handling

| Status | Meaning |
|---|---|
| `200 OK` | Request succeeded |
| `404 Not Found` | The requested resource was not found |
| `500 Internal Server Error` | An unexpected server error occurred |

### Tech Stack

- Node.js
- JSON Server
- JSON-based product data
- Render (deployment)
- GitHub (version control)

### Notes

- This API is intended for practice, learning, and frontend development.
- Product data is loaded from `db.json`.
- The API currently provides read-only GET endpoints for frontend use.
- Render's free service may take some time to respond after a period of inactivity.
