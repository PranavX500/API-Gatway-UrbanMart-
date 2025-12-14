# 🌐 API Gateway (Ecommerce Microservices)

The **API Gateway** acts as the **single entry point** for all client requests in the Ecommerce Microservices architecture.

It forwards requests to respective backend services and performs **JWT-based request validation** before routing secured APIs.

---

# 🚀 Tech Stack

* **Spring Boot**
* **Spring Cloud Gateway**
* **JWT Authentication**
* **Spring Cloud Eureka**
* **Microservices Architecture**

---

# 📌 Responsibilities

* Central access point for frontend
* Route requests to appropriate microservices
* Validate JWT for secured endpoints
* Block unauthorized requests at gateway level
* Integrate with Eureka for service discovery

---

# 🔗 API Endpoints (Gateway Routes)

All client requests must go through the **API Gateway**.

---

## 👤 User Service Routes

Handled by **USER-SERVICE**

| Endpoint Pattern | Description                              |
| ---------------- | ---------------------------------------- |
| `/auth/**`       | User signup, login, logout, profile APIs |

Examples:

```
/auth/signup
/auth/login
/auth/logout
/auth/me
```

---

## 📦 Product Service Routes

Handled by **PRODUCT-SERVICE**

| Endpoint Pattern | Description                         |
| ---------------- | ----------------------------------- |
| `/Product/**`    | Product listing, details, filtering |

Examples:

```
/Product/getAll
/Product/{id}
```

---

## 🔐 OTP Service Routes

Handled by **OTP-SERVICE**

| Endpoint Pattern | Description                   |
| ---------------- | ----------------------------- |
| `/OTP/**`        | OTP generation & verification |

Examples:

```
/OTP/send
/OTP/verify
```

---

## 🛒 Cart Service Routes

Handled by **CART-SERVICE**

| Endpoint Pattern | Description                    |
| ---------------- | ------------------------------ |
| `/Cart/**`       | Cart add, update, remove, view |

Examples:

```
/Cart/add
/Cart/getCart
/Cart/remove/{id}
```

---

## 📑 Order Service Routes

Handled by **ORDER-SERVICE**

| Endpoint Pattern | Description                    |
| ---------------- | ------------------------------ |
| `/Order/**`      | Order creation & order history |

Examples:

```
/Order/place
/Order/getOrders
```

---

## 💳 Payment Service Routes

Handled by **PAYMENT-SERVICE**

| Endpoint Pattern | Description                       |
| ---------------- | --------------------------------- |
| `/payment/**`    | Payment initiation & verification |

Examples:

```
/payment/create
/payment/verify
```

---

# 🔐 Security Notes

* JWT validation is enforced at **API Gateway**
* Public endpoints (like `/auth/login`, `/auth/signup`) are allowed without token
* All secured routes require a valid JWT in:

  ```
  Authorization: Bearer <token>
  ```

  or via **HTTP-only cookies**

---

# 🧩 Architecture Flow

```
Frontend
   ↓
API Gateway
   ↓
Microservices (User / Product / Cart / Order / Payment)
```

---

# 🎯 Future Enhancements

### ⏳ Rate Limiting

Prevent abuse by limiting API requests per user.

### ⏳ Centralized Request Logging

Track all incoming requests at gateway level.

### ⏳ Role-based Route Access

Restrict specific routes for Admin/User roles.

---

## 👨‍💻 Author

**Pranav Sharma**
Microservices | Spring Boot | API Gateway | Security

---
