# 🧠 Redis — In-Memory Data Store

**Redis (REmote DIctionary Server)** is an open-source, lightning-fast, in-memory key-value store.  
It is commonly used for **caching**, **session storage**, **rate limiting**, **real-time data**, and **pub/sub messaging** in backend systems.

---

# 🚀 Why Use Redis?

| Feature             | Description                                                            |
| ------------------- | ---------------------------------------------------------------------- |
| ⚡ Extremely Fast   | Data is stored in memory (RAM), making it much faster than databases   |
| 🧠 Versatile        | Can store strings, hashes, lists, sets, sorted sets, streams, and more |
| ⏱️ TTL Support      | Keys can expire automatically after a set time (great for caching)     |
| 🔐 Lightweight      | Easy to install, configure, and use across platforms                   |
| 🌐 Language Support | Works with Node.js, Python, PHP, Go, Java, etc.                        |

---

## 🗂️ Common Use Cases

| Use Case                 | Example                                              |
| ------------------------ | ---------------------------------------------------- |
| ✅ **Caching**           | Store results of expensive DB queries or API calls   |
| ✅ **Session Storage**   | Store user session tokens or login status            |
| ✅ **Rate Limiting**     | Count user requests per minute/hour to prevent abuse |
| ✅ **Pub/Sub Messaging** | Enable real-time communication between services      |
| ✅ **Queue System**      | Store background tasks for workers                   |

---

## 🔧 Basic Redis Commands

| Command              | Description                              |
| -------------------- | ---------------------------------------- |
| `SET key value`      | Set a string value                       |
| `GET key`            | Get the value of a key                   |
| `DEL key`            | Delete a key                             |
| `EXPIRE key seconds` | Set expiration time for a key            |
| `TTL key`            | Check remaining time-to-live             |
| `INCR key`           | Increment a number (useful for counters) |

🧪 Example:

```bash
SET user:1 "Naruto Uzumaki"
GET user:1
EXPIRE user:1 60
```

---

## 📦 Integration with Backend (Node.js Example)

```js
const redis = require("redis");
const client = redis.createClient();

client.connect();

await client.set("greeting", "Hello Redis");
const value = await client.get("greeting");
console.log(value); // "Hello Redis"
```

---

## 📊 Redis as a Cache

Example: caching expensive database queries

```js
const getUserProfile = async (id) => {
  const cached = await redis.get(`user:${id}`);
  if (cached) return JSON.parse(cached);

  const user = await db.users.findById(id);
  await redis.set(`user:${id}`, JSON.stringify(user), "EX", 3600);
  return user;
};
```
