# 🛡️ Web Security

**Web Security** is the practice of protecting websites, web applications, and APIs from attacks, data breaches, and unauthorized access.  
Understanding common vulnerabilities and applying secure coding practices is essential for every backend developer.

---

## 🔐 Why Web Security Matters

- Protects sensitive user data (e.g., passwords, credit cards)
- Maintains system integrity and availability
- Builds user trust
- Prevents financial, legal, and reputational damage

---

## 🔍 Common Web Security Threats

| Threat                                | Description                                                      |
| ------------------------------------- | ---------------------------------------------------------------- |
| **XSS (Cross-Site Scripting)**        | Injecting malicious scripts into a trusted site                  |
| **SQL Injection (SQLi)**              | Inserting malicious SQL queries into input fields                |
| **CSRF (Cross-Site Request Forgery)** | Tricks user into submitting unwanted actions                     |
| **Clickjacking**                      | Tricking users into clicking on invisible or disguised elements  |
| **Broken Authentication**             | Poorly managed login/session systems                             |
| **Sensitive Data Exposure**           | Transmitting data without encryption or storing it improperly    |
| **Security Misconfiguration**         | Using default credentials, verbose error messages, or open ports |

---

## 🧰 Best Practices

### 1. 🔒 Use HTTPS

Encrypt all communication using SSL/TLS.

### 2. 🔐 Sanitize User Input

Always validate and escape inputs to prevent SQLi and XSS.

### 3. 🧠 Use Parameterized Queries

Avoid building SQL manually. Use safe ORM or prepared statements.

### 4. 🚫 Disable Verbose Errors

Avoid exposing stack traces or database errors to the client.

### 5. 🧾 Secure Cookies

Set `HttpOnly`, `Secure`, and `SameSite` flags on cookies.

### 6. 🧼 Store Passwords Securely

Never store plain passwords — use strong hashing algorithms (e.g., bcrypt).

### 7. 🧑‍💻 Rate Limit Requests

Prevent brute-force and DDoS attacks with rate limiting (e.g., via Redis or middleware).

### 8. 🧭 Use Environment Variables

Store secrets (API keys, DB credentials) in `.env` files, not in code.

---

## 🛡️ Useful HTTP Headers

| Header                      | Purpose                                         |
| --------------------------- | ----------------------------------------------- |
| `Content-Security-Policy`   | Prevent XSS by restricting script sources       |
| `X-Frame-Options`           | Prevent clickjacking (`DENY` or `SAMEORIGIN`)   |
| `X-Content-Type-Options`    | Avoid MIME type sniffing                        |
| `Strict-Transport-Security` | Enforce HTTPS for future requests               |
| `Referrer-Policy`           | Control what info is sent in the Referer header |

---
