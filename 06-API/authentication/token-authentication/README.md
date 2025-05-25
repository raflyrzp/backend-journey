# 🔐 Token Authentication

**Token Authentication** is a stateless authentication method where the server issues a **token** to the client after a successful login.  
The client then includes that token with each request to access protected routes or resources.

---

## 📖 How It Works

1. **User Logs In**  
   The client sends credentials (e.g., email & password) to the server via a login endpoint.

2. **Server Issues Token**  
   If credentials are valid, the server generates a **token** (e.g., random string or JWT) and sends it back to the client.

3. **Client Stores Token**  
   The client stores the token (commonly in memory, `localStorage`, or `cookies`).

4. **Client Sends Token**  
   The client includes the token in each subsequent request, typically using the `Authorization` header:

   ```http
   Authorization: Bearer <token>
   ```

5. **Server Verifies Token**
   The server checks if the token is valid and not expired, then grants or denies access to protected resources.

---

## 🧪 Example Flow

```http
POST /login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "123456"
}
```

**Response:**

```json
{
  "token": "abc123tokenxyz"
}
```

Then used in the header for future requests:

```http
GET /dashboard
Authorization: Bearer abc123tokenxyz
```

---

## 🧰 Common Token Types

| Token Type       | Description                                                    |
| ---------------- | -------------------------------------------------------------- |
| **Random Token** | Server-generated, stored in database or memory to validate     |
| **JWT**          | Self-contained, signed token with claims (no DB lookup needed) |

---

## ✅ Advantages

- 🔁 Stateless – No session data stored on the server
- 🌍 Cross-platform – Works well with web, mobile, IoT, etc.
- 🔐 Secure – Tokens can be short-lived and rotated
- 💡 Flexible – Can contain scopes, roles, or metadata

---

## ⚠️ Best Practices

- Always use **HTTPS** to protect tokens in transit
- Use **short expiration** for access tokens
- Implement **refresh tokens** if needed
- Store tokens securely (e.g., avoid `localStorage` for sensitive apps)
- Invalidate tokens on logout or breach (if not using JWT)

---

## 🔐 Token vs Session

| Feature         | Token-Based Auth        | Session-Based Auth         |
| --------------- | ----------------------- | -------------------------- |
| State on Server | Stateless (no session)  | Stateful (session stored)  |
| Scalability     | Easy to scale           | Harder to scale            |
| Storage         | Stored client-side      | Session stored server-side |
| Used In         | APIs, SPAs, mobile apps | Traditional web apps       |

---

## 🧠 Summary

- **Token Authentication** lets clients prove identity with a token instead of repeating credentials.
- It is lightweight, secure, and works across platforms.
- It’s commonly used in modern APIs and SPAs, especially with JWTs.
