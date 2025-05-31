# 🖥️ Server-Side Caching

**Server-side caching** refers to the practice of storing processed or frequently requested data **on the server**, so it can be quickly returned to clients without repeatedly querying the database or recalculating results.

This approach significantly improves **response time**, reduces **database load**, and increases **scalability**.

---

## 🧠 Why Server-Side Caching?

Without caching, every client request must be computed or queried from scratch, which is slow and resource-heavy.

With server-side caching:

- Frequently accessed data is **stored temporarily in memory or storage**.
- Future requests can **reuse the cached result**, avoiding redundant operations.

---

## 🏗️ Where Caching Happens on the Server?

| Layer                       | Description                                                   |
| --------------------------- | ------------------------------------------------------------- |
| 🔄 **Database Query Cache** | Store result of frequent SQL queries                          |
| 📦 **Object/Data Cache**    | Cache processed objects (e.g., user profiles, dashboard data) |
| 🧠 **Page Fragment Cache**  | Cache parts of rendered pages (e.g., sidebar, header)         |
| 🌍 **Full Page Cache**      | Cache entire HTML output (used in SSR or CMS sites)           |

---
