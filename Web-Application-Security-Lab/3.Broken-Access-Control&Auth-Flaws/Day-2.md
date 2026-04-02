# 🔐 Why Server-Side Authorization Checks Are Essential (IDOR)

## 📌 Overview
While working on IDOR in OWASP Juice Shop, I understood that just being logged in is not enough to ensure security. The real protection comes from how the server validates access to resources.

This write-up explains why server-side authorization checks are critical in preventing IDOR vulnerabilities.

---

## 🔍 What I Observed

During testing, I noticed that many API requests contain object identifiers like:

- `/rest/basket/2`
- `/rest/orders/{orderId}`

At first glance, it looks like changing these IDs might give access to other users' data.

However, when I tried accessing:
`/rest/basket/2`

I received:
`401 Unauthorized (No Authorization header)`

