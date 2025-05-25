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
