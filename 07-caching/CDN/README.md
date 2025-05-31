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

## 🖼️ What Content is Cached?

- 🖼 Images, icons
- 📄 CSS and JavaScript files
- 📹 Videos or media files
- 📚 Static HTML pages
- 🗂 Fonts and PDFs

---

## 🚀 Benefits of Using a CDN

| Benefit                | Description                                                                |
| ---------------------- | -------------------------------------------------------------------------- |
| ⚡ Faster Load Times   | Content is delivered from the closest edge server to the user              |
| 🌍 Global Reach        | Consistent performance across different regions                            |
| 🛡️ DDoS Protection     | Many CDNs provide basic security, traffic filtering, and attack mitigation |
| 📉 Reduced Server Load | Less traffic hits your origin server                                       |
| 📦 Bandwidth Savings   | Edge servers serve cached content more efficiently                         |

---

## 🧪 Popular CDN Providers

| Provider              | Notes                                          |
| --------------------- | ---------------------------------------------- |
| **Cloudflare**        | Free tier available, includes DNS and security |
| **Amazon CloudFront** | Integrated with AWS infrastructure             |
| **Akamai**            | One of the largest and oldest CDNs             |
| **Fastly**            | Great for real-time caching and APIs           |
| **Vercel / Netlify**  | Include CDN automatically for frontend apps    |

---

## 🔧 Example URL via CDN

```html
<!-- jQuery from CDN -->
<script src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js"></script>
```

CDNs also cache your own static assets:

```text
https://cdn.yoursite.com/assets/logo.png
```

---

## ⚠️ Notes

- **Not for dynamic data** — CDN is best for static or semi-static files.
- Combine with client-side caching (`Cache-Control`, `ETag`, etc.) for best performance.
- Version your files (e.g., `app.v1.js`) to invalidate cache when updating content.

---
