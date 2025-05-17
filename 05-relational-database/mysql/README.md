# 🐬 MySQL

**MySQL** is one of the most widely used relational database management systems in the world. It is fast, reliable, and open-source — commonly used in web applications, especially those built with PHP (e.g., WordPress, Laravel), Node.js, and Python.

---

## 📖 What is MySQL?

MySQL stores data in **tables**, using **rows and columns** to structure information. It supports standard **SQL (Structured Query Language)** for querying and managing relational data.

---

## 📌 Why Use MySQL?

| Feature                  | Description                                               |
| ------------------------ | --------------------------------------------------------- |
| ✅ Fast & lightweight    | Great for web apps and data-driven platforms              |
| ✅ Open-source           | Free to use, with active community                        |
| ✅ Cross-platform        | Available on Windows, macOS, Linux                        |
| ✅ Standard SQL support  | Compatible with most database tools and ORMs              |
| ✅ Reliable transactions | Supports ACID, indexing, foreign keys, and constraints    |
| ✅ Integrates easily     | Works well with PHP, Node.js, Python, and many frameworks |

---

## 🔧 Installing MySQL

### Windows / macOS:

Download and install from the official site:  
👉 https://dev.mysql.com/downloads/

### Ubuntu:

```bash
sudo apt update
sudo apt install mysql-server
```

---

## ⚙️ GUI Tools for MySQL

| Tool                | Description                           |
| ------------------- | ------------------------------------- |
| **MySQL Workbench** | Official MySQL GUI by Oracle          |
| **DBeaver**         | Cross-platform multi-database client  |
| **TablePlus**       | Lightweight GUI with modern interface |

---

## 🧪 Example: Anime Character Database (MySQL)

Let’s create a simple anime app to store anime series and their characters.

### 1. 📦 Create Tables

```sql
CREATE TABLE anime_series (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(100),
  genre VARCHAR(50)
);

CREATE TABLE characters (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  role VARCHAR(50),
  anime_id INT,
  FOREIGN KEY (anime_id) REFERENCES anime_series(id)
);
```

### 2. ➕ Insert Sample Data

```sql
INSERT INTO anime_series (title, genre) VALUES
  ('Naruto', 'Shounen'),
  ('Attack on Titan', 'Action');

INSERT INTO characters (name, role, anime_id) VALUES
  ('Naruto Uzumaki', 'Main', 1),
  ('Sasuke Uchiha', 'Rival', 1),
  ('Eren Yeager', 'Main', 2);
```

### 3. 🔍 Query with JOIN

```sql
SELECT c.name AS character, c.role, a.title AS anime
FROM characters c
JOIN anime_series a ON c.anime_id = a.id;
```

📌 Output:
| character | role | anime |
| -------------- | ----- | --------------- |
| Naruto Uzumaki | Main | Naruto |
| Sasuke Uchiha | Rival | Naruto |
| Eren Yeager | Main | Attack on Titan |

---

## ⚙️ Integrating MySQL with Node.js (Using mysql2)

### 1. Install Package:

```bash
npm install mysql2
```

### 2. Example Code:

```js
const mysql = require("mysql2/promise");

async function main() {
  const connection = await mysql.createConnection({
    host: "localhost",
    user: "root",
    database: "anime_db",
    password: "your_password",
  });

  const [rows] = await connection.execute(`
    SELECT c.name, a.title
    FROM characters c
    JOIN anime_series a ON c.anime_id = a.id
  `);

  console.log(rows);
}

main();
```

---

## ✅ Best Practices

- Use foreign keys for data consistency
- Always define primary keys
- Use indexes on frequently searched columns
- Avoid unnecessary `SELECT *`, choose only required columns
- Normalize your tables to avoid data duplication

---

## 🧠 Summary

- MySQL is a reliable, fast, and open-source relational database.
- Ideal for small to large-scale web applications.
- It supports all standard SQL operations.
- Easy to integrate with most backend stacks (Node.js, PHP, Python, etc.).
