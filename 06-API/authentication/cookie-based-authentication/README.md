# 🍪 Cookie-Based Authentication

**Cookie-Based Authentication** is a traditional and widely-used method to manage user sessions.  
After the user logs in, the server creates a **session** and sends back a **cookie** that uniquely identifies the session. This cookie is automatically included in future requests by the browser.

---

## 🧠 How It Works

1. **User Logs In**  
   Client sends login credentials to the server (e.g., `POST /login`).

2. **Server Creates Session**  
   If credentials are valid, the server:

   - Creates a session (usually in memory or a database)
   - Stores session data (e.g., user ID, roles)
   - Generates a unique session ID

3. **Server Sends Cookie**  
   The session ID is sent to the client inside a `Set-Cookie` header.

   ```http
   Set-Cookie: sessionId=abc123; HttpOnly; Secure; SameSite=Strict
   ```

4. **Browser Stores Cookie**
   The browser automatically stores the cookie.

5. **Client Makes Authenticated Requests**
   For every future request, the browser automatically includes the cookie:
   ```http
   Cookie: sessionId=abc123
   ```
6. **Server Validates Session**
   The server finds the session using the session ID and checks if it’s valid.

---

## 📦 Example Flow

```http
POST /login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "123456"
}

```

**Response:**

```http
Set-Cookie: sessionId=xyz789; HttpOnly; Secure
```

Then, on every request:

```http
GET /dashboard
Cookie: sessionId=xyz789
```

---

## 🔒 Security Best Practices

| Setting           | Purpose                                           |
| ----------------- | ------------------------------------------------- |
| `HttpOnly`        | Prevents JavaScript access (mitigates XSS)        |
| `Secure`          | Ensures cookie is sent only over HTTPS            |
| `SameSite=Strict` | Prevents CSRF (cross-site request forgery)        |
| Short expiry      | Sessions should have expiration (e.g., 1–2 hours) |

---

## ✅ Pros & Cons

| Pros                                   | Cons                                             |
| -------------------------------------- | ------------------------------------------------ |
| ✅ Automatic handling by browsers      | ❌ More difficult to use with APIs/mobile        |
| ✅ Built-in support in many frameworks | ❌ Requires server-side session store            |
| ✅ Easy for traditional web apps       | ❌ Vulnerable to CSRF if not configured properly |
