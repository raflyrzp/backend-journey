# 📦 SQLite: Embedded Relational Database Engine

**SQLite** is a self‑contained, serverless, zero‑configuration, transactional SQL database engine.  
Instead of running as an external server process, SQLite reads and writes directly to ordinary disk files—making it lightweight and easy to embed inside applications.

---

## 🌟 Key Characteristics

| Feature                 | Details                                                                                                                  |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Serverless**          | No separate server daemon—your application links to a small library (`sqlite3`) and accesses the database file directly. |
| **Zero‑configuration**  | No setup, no user management, no networking—just include the library and go.                                             |
| **Single‑file Storage** | Entire database (schema + data + indexes) lives in one cross‑platform file.                                              |
| **ACID Transactions**   | Fully supports Atomicity, Consistency, Isolation, Durability—even with power loss or crashes.                            |
| **SQL‑92 compliant**    | Implements most of the SQL standard plus useful extensions (e.g., JSON functions).                                       |
| **Lightweight**         | Core library ≈ 700 KB; excellent for mobile, IoT, or desktop apps.                                                       |
| **Public Domain**       | Free for any use—commercial or open‑source.                                                                              |

---

## 🔧 When to Use SQLite

| Ideal Scenarios                                       | Consider Alternatives (e.g., MySQL/PostgreSQL) |
| ----------------------------------------------------- | ---------------------------------------------- |
| Mobile apps (iOS, Android)                            | High‑concurrency web services                  |
| Desktop software (Electron, .NET, etc.)               | Multi‑GB datasets with heavy write load        |
| Embedded / IoT devices (Raspberry Pi)                 | Complex multi‑user permission models           |
| Unit testing or prototyping                           | Horizontal scaling / clustering requirements   |
| Small‑to‑medium websites (with low write concurrency) | Real‑time replication & sharding needs         |

---

## 🚀 Getting Started

### 1. Installation

- **CLI** (macOS / Linux):

```bash
  # macOS (Homebrew)
  brew install sqlite

  # Ubuntu / Debian
  sudo apt-get update
  sudo apt-get install sqlite3
```

- **Node.js**

```bash
npm install better-sqlite3   # or sqlite3
```

- **Python** : Comes built‑in (import sqlite3).

### 2. Creating a Database

```bash
sqlite3 anime.db        # Opens a new or existing SQLite file
```

```sql
-- Inside the prompt
CREATE TABLE anime_series (
  id   INTEGER PRIMARY KEY AUTOINCREMENT,
  title TEXT,
  genre TEXT
);

CREATE TABLE characters (
  id   INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT,
  role TEXT,
  anime_id INTEGER REFERENCES anime_series(id)
);

```

## 3. Inserting & Querying Data

```sql
INSERT INTO anime_series (title, genre) VALUES
  ('Naruto', 'Shounen'),
  ('Attack on Titan', 'Action');

INSERT INTO characters (name, role, anime_id) VALUES
  ('Naruto Uzumaki', 'Main', 1),
  ('Sasuke Uchiha', 'Rival', 1),
  ('Eren Yeager', 'Main', 2);

SELECT c.name, a.title
FROM characters c
JOIN anime_series a ON c.anime_id = a.id;
```

---

## 🛠️ Using SQLite in Code (Node.js Example)

```js
const Database = require("better-sqlite3");
const db = new Database("anime.db");

// Query
const rows = db
  .prepare(
    `
  SELECT c.name, a.title
  FROM characters c
  JOIN anime_series a ON c.anime_id = a.id
`
  )
  .all();

console.log(rows);
```

---

## ✅ Best Practices

- Use prepared statements to prevent SQL injection.
- Keep the database file on a fast local disk; avoid network drives.
- For multi‑threaded apps, use serialized mode or a connection pool library.
- Backup simply by copying the `.db` file (ideally when writes are paused).
- Enable WAL mode `(PRAGMA journal_mode=WAL;)` for better read‑write concurrency.

---

## 🧠 Summary

- **SQLite** is an embedded, zero‑config RDBMS perfect for mobile, desktop, testing, and small‑scale server apps.
- Stores everything in a single file yet delivers full ACID transactions and rich SQL features.
- Choose SQLite for simplicity and portability; switch to a client‑server DB for high‑concurrency, multi‑user workloads.
