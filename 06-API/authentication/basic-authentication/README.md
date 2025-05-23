# 🔐 Basic Authentication

**Basic Authentication** is a simple authentication method built into the HTTP protocol.  
It allows clients to send a username and password with each request to verify their identity.

---

## 📖 How It Works

1. The client sends an HTTP request with an **`Authorization` header** that includes a **Base64-encoded** string containing the `username:password`.

2. The server decodes and verifies the credentials on every request.

3. If the credentials are valid, the request is processed. Otherwise, it returns a `401 Unauthorized` response.

---
