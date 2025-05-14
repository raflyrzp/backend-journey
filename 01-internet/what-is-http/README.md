## 📖 What is HTTP?

**HTTP** stands for **HyperText Transfer Protocol**. It is the protocol used by web browsers and servers to communicate over the Internet.

- It is a **stateless** protocol, meaning each request is independent.
- It uses a **request-response model**.
- It runs on top of **TCP/IP**.

Example:
When you visit `https://example.com`, your browser sends an HTTP request to the server, and the server sends back an HTTP response containing the webpage.

---

## 📤 HTTP Request

An **HTTP Request** is sent from the client (like your browser or Postman) to the server. It typically contains:

### ✉️ Request Structure:

- **Method** – Type of action (GET, POST, PUT, DELETE, etc.)
- **URL** – The endpoint being requested
- **Headers** – Extra information (e.g., authentication, content-type)
- **Body** – Data sent (for POST, PUT, etc.)

### 🧪 Common HTTP Methods:

| Method | Description              |
| ------ | ------------------------ |
| GET    | Request data (read-only) |
| POST   | Send new data            |
| PUT    | Replace existing data    |
| PATCH  | Partially update data    |
| DELETE | Remove data              |

Example:

```http
GET /users HTTP/1.1
Host: example.com
```
