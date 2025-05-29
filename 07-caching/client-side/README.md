# 🧠 Client-Side Caching

**Client-Side Caching** refers to storing data directly in the **user's browser or device**, so that repeated requests for the same resource can be served locally — without hitting the server.

This improves performance, reduces server load, and gives users a faster experience.

---

## 🌐 Where Does Client-Side Caching Happen?

| Layer                             | Description                                                            |
| --------------------------------- | ---------------------------------------------------------------------- |
| **Browser Cache**                 | Stores static assets (images, CSS, JS) based on HTTP headers           |
| **Service Workers**               | Intercepts network requests and serves from local cache (used in PWAs) |
| **LocalStorage / SessionStorage** | Stores custom app data (e.g., user settings, temporary tokens)         |
| **IndexedDB**                     | Client-side NoSQL database, used for offline apps                      |

---

## 📦 Example: Browser Cache

When a web page loads assets like stylesheets or images, the browser may store them in its cache based on the server's **cache-control** or **expires** headers.

```http
Cache-Control: max-age=3600
```

🔁 The next time the page loads, the browser doesn’t re-download the file — it uses the one stored in cache.

---
