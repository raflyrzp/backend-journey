# 🔐 JWT — JSON Web Token

## 📖 What Is JWT?

**JWT** (JSON Web Token) is a compact, self-contained way to securely transmit information between two parties.  
It is commonly used for:

- **Authentication** (verifying user identity)
- **Authorization** (granting access to protected routes/resources)

---

## 🔧 JWT Structure

A JWT looks like this:

  <img src="./jwt-structure.png" alt="Structure of JWT" />

> _Figure: JWT consists of three parts — Header, Payload, and Signature._  
> Source: [SuperTokens](https://supertokens.com/blog/what-is-jwt)

### 1. **Header**

Specifies metadata about the token.

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

- `alg`: Algorithm used to sign the token (e.g., HS256)
- `typ`: Type of token (always "JWT")

### 2. Payload (Claims)

Contains the data being transmitted (not encrypted, just encoded).

```json
{
  "sub": "1234567890",
  "name": "George White",
  "admin": true,
  "iat": 1516239022
}
```

Common fields:

- `sub`: Subject (usually user ID)
- `iat`: Issued at (timestamp)
- `exp`: Expiration time (timestamp)
- `custom claims`: e.g., roles, email, etc.

### 3. Signature

Used to verify that the token hasn’t been tampered with.

```scss
HMACSHA256(
  base64UrlEncode(header) + "." + base64UrlEncode(payload),
  secret
)
```

---

## 🔄 JWT Authentication Flow

The typical authentication flow using JWT looks like this:

1. **Login**  
   The user submits login credentials (e.g., `POST /login`).

2. **Server Issues Token**  
   If the credentials are valid, the server generates a JWT and sends it back to the client.

3. **Client Stores Token**  
   The client saves the JWT in a secure place, usually:

   - `localStorage` or `sessionStorage` (browser)
   - `cookie` (for web apps with automatic inclusion)

4. **Client Sends Token**  
    For protected API requests, the client includes the JWT in the request headers:

   ```http
   Authorization: Bearer <token>
   ```

5. **Server Verifies Token**
   The backend verifies the token using the secret key:

   - Checks the signature for integrity
   - Validates expiration time (exp) and other claims
   - Grants access if valid, rejects if invalid or expired

---

## 🧪 Sample Token

```http
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
```

Payload (decoded):

```json
{
  "sub": "user123",
  "role": "admin",
  "exp": 1716239022
}
```

---

## ✅ Benefits of JWT

| Advantage      | Description                                                    |
| -------------- | -------------------------------------------------------------- |
| Stateless      | No need to store session data on the server                    |
| Cross-platform | Works with web, mobile, IoT, etc.                              |
| Secure         | Signed tokens ensure data integrity                            |
| Compact        | Easy to send via headers, URLs, cookies                        |
| Self-contained | All user info is in the token (avoid DB lookups in some cases) |

---

## ⚠️ JWT Best Practices

- ✅ Use HTTPS to protect tokens in transit
- ✅ Store tokens securely (never in localStorage on sensitive apps)
- ✅ Use short expiration times (e.g., 15 mins)
- ✅ Issue refresh tokens separately for longer sessions
- ❌ Never store sensitive data in payload (e.g., passwords)
- ✅ Revoke tokens if necessary by using a blocklist (optional)

---

## 🧰 Example (Node.js Express)

```js
const jwt = require("jsonwebtoken");

// Sign Token
function generateToken(user) {
  return jwt.sign({ id: user.id, name: user.name }, process.env.JWT_SECRET, {
    expiresIn: "1h",
  });
}

// Middleware to protect routes
function authenticate(req, res, next) {
  const authHeader = req.headers.authorization;
  if (!authHeader?.startsWith("Bearer ")) {
    return res.status(401).json({ message: "Unauthorized" });
  }

  const token = authHeader.split(" ")[1];
  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = decoded;
    next();
  } catch (err) {
    return res.status(403).json({ message: "Forbidden" });
  }
}
```

---

## 🧠 Summary

- JWT is a widely used format for authentication in stateless APIs.
- It consists of three parts: Header, Payload, and Signature.
- The token is signed (not encrypted), so it can be read but not tampered with.
- Implemented properly, JWT makes authentication scalable and secure across platforms.
