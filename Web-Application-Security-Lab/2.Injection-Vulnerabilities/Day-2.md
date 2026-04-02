# ⚡ Cross-Site Scripting (XSS) – OWASP Juice Shop

## 📌 Overview
In this task, I performed Cross-Site Scripting (XSS) attacks on OWASP Juice Shop.  
The goal was to identify input handling issues, test payloads, bypass filters, and understand secure mitigation techniques.

---

## 🎯 Target
- Application: OWASP Juice Shop  
- URL: http://localhost:3000  

<img width="1713" height="802" alt="Js-1" src="https://github.com/user-attachments/assets/431a2d48-5afa-4fa0-b261-252032964805" />

---

# 🔸 1. Reflected XSS

## 🛠️ Steps

### 🔹 Step 1: Navigate
- Open Juice Shop  
- Use the search bar  

---

### 🔹 Step 2: Initial Payload (Blocked)

```html
<script>alert('XSS')</script>
```

---

### 🔹 Step 3: Bypass Payload (Successful)
```html
<img src=x onerror=alert('XSS')>
```

---

### Result
- Alert popup executed successfully
- JavaScript executed in browser
- Reflected XSS confirmed

<img width="1715" height="796" alt="js-2" src="https://github.com/user-attachments/assets/4f0eb6a9-f0a5-4350-b36d-292d5d4ee21d" />

---

