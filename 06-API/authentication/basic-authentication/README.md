# 🔐 Basic Authentication

**Basic Authentication** is a simple authentication method built into the HTTP protocol.  
It allows clients to send a username and password with each request to verify their identity.

---

## 📖 How It Works

1. The client sends an HTTP request with an **`Authorization` header** that includes a **Base64-encoded** string containing the `username:password`.

2. The server decodes and verifies the credentials on every request.

3. If the credentials are valid, the request is processed. Otherwise, it returns a `401 Unauthorized` response.

---

## 🧾 Example

```http
GET /protected-resource HTTP/1.1
Host: example.com
Authorization: Basic YWRtaW46cGFzc3dvcmQ=
```

In this example:

- admin:password is encoded to Base64 → YWRtaW46cGFzc3dvcmQ=
- The server will decode it back and verify the username and password

---

## 🔓 Response If Unauthorized

If no or invalid credentials are provided:

```http
HTTP/1.1 401 Unauthorized
WWW-Authenticate: Basic realm="Access to the site"
```

---
