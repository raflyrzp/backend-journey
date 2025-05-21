# 🔑 OAuth — Open Authorization

**OAuth** is an open standard protocol that allows users to **grant third-party applications limited access** to their resources **without sharing their credentials** (like passwords).

It is widely used by platforms such as Google, Facebook, GitHub, and Twitter to let users log in to other apps securely via **“Login with…”** buttons.

---

## 🧠 Why OAuth?

Traditional authentication methods require users to share their username and password with every app they use — this is **insecure and unscalable**.

**OAuth solves this** by letting users:

- Log in via a trusted identity provider (e.g., Google)
- Approve access to specific data (e.g., email, profile picture)
- Without revealing their password to the third-party app

---

## 🔄 OAuth Flow (Authorization Code Grant)

This is the most common OAuth 2.0 flow used in web applications:

1. **User Clicks Login with Google**  
   Your app redirects the user to Google's OAuth server.

2. **User Grants Permission**  
   The user logs in (if not already), and approves access to requested scopes (e.g., profile, email).

3. **Authorization Code**  
   Google redirects the user back to your app with an **authorization code**.

4. **Access Token Exchange**  
   Your server sends the code to Google's token endpoint to receive an **access token** (and optionally a **refresh token**).

5. **Use Access Token**  
   Your app uses the access token to fetch user data from Google APIs (e.g., profile info).

---

## 📦 Example Real-Life Use

- You click **“Login with GitHub”** on a website.
- GitHub asks for your permission to share email and profile.
- You approve.
- The website now receives a token that allows it to read only your GitHub name and email — **not your password**.

---

## 🧪 Access Token vs Refresh Token

| Token Type        | Purpose                        | Lifetime              |
| ----------------- | ------------------------------ | --------------------- |
| **Access Token**  | Used to access APIs            | Short-lived (minutes) |
| **Refresh Token** | Used to get a new access token | Long-lived (days)     |

---

## 🔐 OAuth Scopes

Scopes define what data or actions the application is allowed to access.

For example:

- `email`: Access your email address
- `profile`: Access your basic profile information
- `repo`: Access your GitHub repositories

Applications should **request the minimal scopes necessary**.

---

## ✅ OAuth vs JWT

| Feature          | OAuth                                 | JWT                                       |
| ---------------- | ------------------------------------- | ----------------------------------------- |
| Purpose          | Delegate access via trusted providers | Authenticate and authorize users directly |
| Token Issuer     | Third-party provider (e.g., Google)   | Your own backend                          |
| Stateless?       | Yes                                   | Yes                                       |
| User Interaction | Often involves a consent screen       | None (handled by your own login flow)     |

---

## ⚠️ Security Tips

- Always use **HTTPS** to protect token exchanges.
- Store **refresh tokens** securely (e.g., in HTTP-only cookies).
- Validate **state** parameters to prevent CSRF.
- Use **PKCE** for public clients (e.g., mobile apps).

---

## 🧠 Summary

- **OAuth** allows secure third-party access to user data without sharing passwords.
- It's commonly used for “Login with…” flows.
- Involves exchanging authorization codes for access tokens.
- Access is limited and scoped, keeping users in control.

Next: Learn how to implement **OAuth login using Passport.js** or other libraries in your backend.
