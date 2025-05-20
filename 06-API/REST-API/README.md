# 🔄 REST API (Representational State Transfer)

**REST API** is an architectural style for designing networked applications.  
It uses standard HTTP methods and stateless communication to allow clients and servers to exchange data in a structured and predictable way.

---

## 📖 What Is a REST API?

A **RESTful API** treats everything as a **resource** (like users, posts, or products) and allows interaction with those resources using **HTTP methods**:

| Method | Action                | Example                                |
| ------ | --------------------- | -------------------------------------- |
| GET    | Retrieve data         | `GET /users` → list all users          |
| POST   | Create new data       | `POST /users` → create new user        |
| PUT    | Replace existing data | `PUT /users/1` → update user with ID 1 |
| PATCH  | Update part of data   | `PATCH /users/1` → update field(s)     |
| DELETE | Delete data           | `DELETE /users/1` → remove user        |

---

## 🧱 RESTful Principles

| Principle             | Description                                                                   |
| --------------------- | ----------------------------------------------------------------------------- |
| **Stateless**         | Each request must contain all the information needed — no session storage.    |
| **Client–Server**     | Separation of concerns — UI and data logic are independent.                   |
| **Cacheable**         | Responses can be cached to improve performance.                               |
| **Uniform Interface** | Consistent structure: URIs, methods, headers, and response formats.           |
| **Layered System**    | The client doesn’t need to know if the server uses load balancers or proxies. |

---

## 🧩 Example: User API

Assume we are building a RESTful API for managing users:

| HTTP Method | Endpoint    | Description             |
| ----------- | ----------- | ----------------------- |
| GET         | `/users`    | Get all users           |
| GET         | `/users/42` | Get user with ID 42     |
| POST        | `/users`    | Create a new user       |
| PUT         | `/users/42` | Replace user with ID 42 |
| PATCH       | `/users/42` | Modify user with ID 42  |
| DELETE      | `/users/42` | Delete user with ID 42  |

---

## 📦 Example Response

```json
{
  "id": 42,
  "name": "Maki Zenin",
  "email": "makizenin@example.com"
}
```

---

## ⚠️ Common Status Codes

| Code | Meaning               |
| ---- | --------------------- |
| 200  | OK                    |
| 201  | Created               |
| 204  | No Content            |
| 400  | Bad Request           |
| 401  | Unauthorized          |
| 403  | Forbidden             |
| 404  | Not Found             |
| 500  | Internal Server Error |

---

## 📚 REST vs Other API Styles

| Feature     | REST               | GraphQL               | gRPC                  |
| ----------- | ------------------ | --------------------- | --------------------- |
| Structure   | Multiple endpoints | One endpoint          | Method-based contract |
| Flexibility | Fixed responses    | Client chooses fields | Binary & fast         |
| Format      | JSON / XML         | JSON                  | Protobuf (binary)     |
| Use Case    | Simpler APIs, CRUD | Complex queries       | Microservices, speed  |

---

## ✅ REST API Best Practices

- Use plural nouns in endpoints: `/users`, `/products`
- Return proper status codes
- Keep URLs resource-based, not action-based: use `POST /users` not `POST /createUser`
- Implement pagination: `GET /users?page=1&limit=10`
- Handle errors with clear, consistent messages
- Use OpenAPI (Swagger) to document your API

---

## 🧠 Summary

REST APIs are one of the most widely adopted ways to expose data and functionality over the web.
They are simple, scalable, and follow standard HTTP conventions, making them easy to understand and integrate.
