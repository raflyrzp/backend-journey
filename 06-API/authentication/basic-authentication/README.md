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

- `admin:password` is encoded to Base64 → `YWRtaW46cGFzc3dvcmQ=`
- The server will decode it back and verify the username and password

---

## 🔓 Response If Unauthorized

If no or invalid credentials are provided:

```http
HTTP/1.1 401 Unauthorized
WWW-Authenticate: Basic realm="Access to the site"
```

---

## ⚠️ Security Considerations

| Issue                  | Explanation                                                     |
| ---------------------- | --------------------------------------------------------------- |
| 🔒 Credentials Visible | The username and password are only **encoded**, not encrypted   |
| ❌ No Token Support    | No sessions or tokens — credentials sent every time             |
| 🚫 Not Secure Alone    | Should **only be used over HTTPS** to prevent data interception |

---

## ✅ When to Use

| Suitable For                 | Not Suitable For                         |
| ---------------------------- | ---------------------------------------- |
| Quick internal tools         | Public-facing production applications    |
| Simple development testing   | Apps that need session, roles, or logout |
| Scripts or automated systems | APIs requiring fine-grained access       |

---

## 🔐 Alternative: Use Token-Based Auth or OAuth for production

While Basic Auth is simple and built-in, it’s recommended to use more secure and flexible methods like:

- JWT (JSON Web Token)
- OAuth 2.0
- API keys with scoped access

---

## 🧠 Summary

- Basic Auth uses `Authorization: Basic <Base64(username:password)>`
- It’s part of the HTTP standard and requires no extra libraries
- Only safe when used over HTTPS
- Best used for quick testing, not for secure or complex applications
