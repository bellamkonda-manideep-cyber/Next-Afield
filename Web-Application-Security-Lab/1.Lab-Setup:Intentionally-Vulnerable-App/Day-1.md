# 🔐 Web Application Security Lab
## 📌 Project Overview
I built a hands-on web application security lab using intentionally vulnerable applications to understand real-world security issues. The goal of this project is to learn how vulnerabilities work, how to exploit them safely, and how to think like both an attacker and a defender.
All testing is performed in a controlled local environment using Docker.

---

### Lab Setup
- Environment
  - OS: Kali Linux
- Tools Used:
    - Docker & Docker Compose
    - Burp Suite (installed)
    - SQLMap (installed)
      
---

### Applications Deployed

Using Docker Compose, I deployed the following vulnerable applications:
- DVWA (Damn Vulnerable Web Application)
- OWASP Juice Shop
- OWASP WebGoat

---

Docker Setup
```bash
mkdir web-security-lab
cd web-security-lab

```

Created `docker-compose.yml`: <br>
services: <br>
dvwa: <br>
image: vulnerables/web-dvwa <br>
ports: <br>
- "8081:80" <br>
juice-shop: <br>
image: bkimminich/juice-shop <br>
ports: <br>
- "3000:3000" <br>
webgoat: <br>
image: webgoat/webgoat-8.0 <br>
ports: <br>
- "8082:8080" <br>
### Run containers:
```bash
docker compose up -d
```

<img width="1696" height="128" alt="image" src="https://github.com/user-attachments/assets/8eec7283-1831-456c-a776-141124661fab" />

---

### Access URLs
- DVWA → http://localhost:8081
- Juice Shop → http://localhost:3000
- WebGoat → http://localhost:8082/WebGoat

---

### Verification Steps
Checked running containers:
```bash
docker ps
```
<img width="1691" height="102" alt="image" src="https://github.com/user-attachments/assets/2bf1e480-c11a-42dd-8800-3bbe9ab5db57" />

---

### Key Learnings
- Understanding Docker port mapping (host vs container ports)
- Debugging container issues using logs
- Identifying service startup problems
- Fixing real-world configuration mistakes
