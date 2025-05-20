# 🌐 HTTP Overview

![HTTP Connection Overview](./http-img.gif)

> _Figure: Basic HTTP communication between client and server using request-response model._  
> Source: [GeeksforGeeks – HTTP Full Form](https://www-geeksforgeeks-org.translate.goog/http-full-form/?_x_tr_sl=en&_x_tr_tl=id&_x_tr_hl=id&_x_tr_pto=imgs)

---

## 📖 What is HTTP?

**HTTP** stands for **HyperText Transfer Protocol**.  
It is the foundation of data communication for the Web, allowing browsers, mobile apps, and APIs to talk with servers.

- It is a **stateless** protocol — each request is independent.
- It follows a **request–response** model.
- It operates over **TCP/IP**.

🔍 **Example**:  
When you visit `https://example.com`, your browser sends an HTTP request to the server, and the server responds with HTML, CSS, or JSON content.

---

## 📤 HTTP Request

An **HTTP Request** is sent from a client (like a browser, Postman, or mobile app) to a server. It consists of:

### ✉️ Request Structure:

| Part        | Description                                            |
| ----------- | ------------------------------------------------------ |
| **Method**  | Action type: `GET`, `POST`, `PUT`, `DELETE`, etc.      |
| **URL**     | Target endpoint (e.g., `/api/users`)                   |
| **Headers** | Metadata (e.g., `Authorization`, `Content-Type`)       |
| **Body**    | Payload data (for methods like `POST`, `PUT`, `PATCH`) |

---

## 🧪 Common HTTP Methods

| Method   | Description               |
| -------- | ------------------------- |
| `GET`    | Retrieve data (read-only) |
| `POST`   | Send new data             |
| `PUT`    | Replace entire resource   |
| `PATCH`  | Partially update resource |
| `DELETE` | Remove resource           |

🧾 **Example Request**:

```http
GET /users HTTP/1.1
Host: example.com
Accept: application/json
```

---

## 🧠 Summary

- HTTP enables structured communication between client and server.
- It uses methods like GET and POST to perform actions.
- Every interaction is stateless and follows a clear structure.
- Understanding HTTP is essential before building APIs or web apps.
