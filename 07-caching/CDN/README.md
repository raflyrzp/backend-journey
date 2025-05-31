# 🌍 CDN — Content Delivery Network

A **CDN (Content Delivery Network)** is a globally distributed network of servers that delivers static content (like images, CSS, JavaScript, videos) to users from the **closest geographical server**.

The goal of a CDN is to **reduce latency**, **increase speed**, and **improve scalability** for websites and web applications.

---

## 🧭 How a CDN Works

1. A user visits your website.
2. The browser requests assets like images, fonts, or scripts.
3. Instead of going to your origin server, the request is routed to the nearest CDN edge server.
4. If the content is cached there, it's served directly (cache hit).
5. If not, the CDN fetches it from the origin server, delivers it to the user, and caches it for next time.

---
