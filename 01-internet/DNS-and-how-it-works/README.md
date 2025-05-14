# 🌐 Understanding DNS

When you visit a website like `google.com`, you're using something called a **domain name**. But what exactly is a domain? And how does it help your browser find the right website? This section explains domain names and how the Domain Name System (DNS) works.

---

## 📖 What is a Domain?

A **domain name** is a **human-friendly address** used to access websites on the Internet.

Example:

- `google.com`
- `wikipedia.org`
- `yourproject.dev`

Instead of remembering complex numbers (IP addresses), we use domain names.

---

## 🧠 Why Do We Need Domains?

Computers communicate using **IP addresses** like `142.250.190.78`, but these numbers are hard for humans to remember.

So, we use domains like `google.com`, which is easier to type and recall. Behind the scenes, that domain is mapped to an IP address using a system called **DNS**.

---

## 🌍 Domain Structure

A domain name typically has several parts:

www.google.com

| parts  | Description               |
| ------ | ------------------------- |
| www    | Subdomain                 |
| google | Second-Level Domain (SLD) |
| com    | Top-Level Domain (TLD)    |

### 📚 Common Top-Level Domains (TLDs)

- `.com` – commercial
- `.org` – organization
- `.net` – network
- `.id`, `.my`, `.jp` – country codes
- `.dev`, `.io`, `.app` – tech-related

---

## 🧭 What is DNS?

**DNS (Domain Name System)** is like the Internet’s **phonebook**. It translates domain names into IP addresses so that browsers can load websites.

### 🔄 How DNS Works — Step by Step

Let’s say you type `youtube.com` into your browser:

1. **Browser checks local cache** — “Do I already know the IP for this?”
2. **Asks the DNS resolver (usually your ISP)** — “What’s the IP of `youtube.com`?”
3. **Resolver asks root servers**, then TLD servers, then the authoritative server.
4. **Gets the IP address** — for example, `142.250.190.206`
5. **Browser sends an HTTP request** to that IP and loads the site.

All of this happens in **milliseconds**.

---

## 📚 Types of DNS Records

| Record Type | Description                                              |
| ----------- | -------------------------------------------------------- |
| `A`         | Points a domain to an IPv4 address                       |
| `AAAA`      | Points to an IPv6 address                                |
| `CNAME`     | Canonical name (alias) to another domain                 |
| `MX`        | Mail exchange – used for email servers                   |
| `TXT`       | Stores plain text, often for verification (e.g., Google) |
| `NS`        | Nameservers that control DNS for the domain              |

---

## 🛠 Tools to Check DNS

- 🔍 [dnschecker.org](https://dnschecker.org) — View global DNS propagation
- 🧪 Terminal:
  - `nslookup google.com`
  - `dig youtube.com`
- 🧰 Browser Dev Tools → Network tab → See domain resolution

---

## 🏗️ How to Get Your Own Domain

You can register your own domain name via a **domain registrar** like:

- [Namecheap](https://namecheap.com)
- [Google Domains](https://domains.google)
- [GoDaddy](https://godaddy.com)
- [Porkbun](https://porkbun.com)
- [Niagahoster](https://niagahoster.co.id) _(Indonesia)_

Once registered, you can:

- Set up custom DNS records
- Point your domain to your server
- Use it with your backend or frontend project

---

## 📦 Real-World Analogy

**Domain name** = Name of a contact (like “Rafly” in your phone)

**IP address** = Rafly’s actual phone number

**DNS** = Your phone’s contact list, which helps you call Rafly by name instead of memorizing his number

---

## ✅ Summary

- A **domain** is a human-readable address for a website.
- Behind every domain is an **IP address** that the computer connects to.
- **DNS** helps translate between domain names and IPs.
- You can buy your own domain and point it to any backend or frontend project.
