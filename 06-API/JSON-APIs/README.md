# 📦 JSON APIs

A **JSON API** is an API that uses **JSON (JavaScript Object Notation)** as the primary format for data exchange between client and server.

It is not a specific protocol like REST or GraphQL, but a **data format convention** used widely in modern web APIs—especially in RESTful APIs.

---

## 🧾 What is JSON?

**JSON** is a lightweight data format that is:

- Easy to read and write (human-friendly)
- Easy to parse and generate (machine-friendly)
- Language-independent, but widely supported

Example:

```json
{
  "id": 1,
  "name": "Maki Zenin",
  "email": "makizenin@example.com"
}
```

---

## 🔄 What is a JSON API?

A JSON API is any API that:

- Accepts JSON as input (in the request body)
- Returns JSON as output (in the response body)

It is commonly used with REST APIs but can also be used in GraphQL, gRPC, or even custom protocols.

---

## 📤 Example JSON Request

```http
POST /users HTTP/1.1
Content-Type: application/json

{
  "name": "Maki Zenin",
  "email": "makizenin@example.com"
}
```

---

## 📥 Example JSON Response

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": 1,
  "name": "Naruto Uzumaki",
  "email": "naruto@example.com",
  "created_at": "2025-05-21T10:15:00Z"
}
```

---

## 🧠 Why Use JSON?

| Benefit               | Description                                                    |
| --------------------- | -------------------------------------------------------------- |
| 🌍 Universal          | Works across languages and platforms                           |
| 🧑‍💻 Developer-friendly | Easy to read and debug                                         |
| 🚀 Lightweight        | Smaller payloads than XML                                      |
| 📦 Native in JS       | JSON is built into JavaScript (and easily supported in others) |

---

## 🧱 Structure Guidelines

While JSON itself is flexible, well-designed APIs often follow best practices:
| Key | Guideline |
| -------------- | --------------------------------------------------------------------------------------- |
| **Key names** | Use `snake_case` or `camelCase` consistently |
| **Timestamps** | Use ISO 8601 format (e.g., `"2025-05-21T10:15:00Z"`) |
| **Errors** | Wrap in consistent structure: `{ "error": { "code": 400, "message": "Invalid data" } }` |
| **Arrays** | Use for lists: `[{ "id": 1, "name": "..." }, ...]` |
| **Nulls** | Return `null` for empty optional values instead of omitting them |

---

## 📚 JSON:API Specification (Optional Standard)

There is a formal specification at https://jsonapi.org called JSON:API.
It defines strict rules for structuring requests and responses, including pagination, filtering, and relationships.

> You don’t need to use JSON:API to build a JSON API, but it’s useful for standardizing complex APIs.

---

## 🧠 Summary

- JSON API refers to any API that uses JSON as the data format.
- It’s the default for modern web APIs and works naturally with REST.
- Clean and consistent JSON responses help frontend apps and mobile apps consume your API more easily.
