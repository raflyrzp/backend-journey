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
