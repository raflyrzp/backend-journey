# ⚡ Caching in Backend Systems

Caching is the process of **storing frequently accessed data in temporary storage** (called a cache) to make future data retrieval faster and reduce load on the primary database.

---

<div align="center">
  <img src="./database-caching-diagram.png" alt="Database Caching Diagram" width="70%" />
</div>

> _Figure: Applications check the cache first. If not found (cache miss), they query the database._  
> Source: [ScyllaDB Glossary – Database Caching](https://www.scylladb.com/glossary/database-caching/)

---

## 🧠 How Caching Works

1. **Client Requests Data**
2. **Application checks the cache**
   - If the data is found (**cache hit**), it returns immediately.
   - If not found (**cache miss**), the app queries the database.
3. **If cache miss**, data is fetched from the database, returned to the client, and **stored in the cache** for next time.

---
