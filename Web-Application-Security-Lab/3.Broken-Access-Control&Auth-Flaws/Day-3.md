# 🔐 JWT Token Decoding – WebGoat

## Overview
In this task, I explored how JWT (JSON Web Tokens) work and how they can expose sensitive information if not implemented securely.

The main goal was to decode a JWT token and analyze its structure.

---

## Target
- Application: WebGoat  
- Module: JWT  
- Tool Used: jwt.io  

---

## Steps Performed

### Step 1: Capture JWT Token Which in the WebGoat 
- Go to (A2) Broken Authentication in that select JWT tokens.
- Go to the fifth tab, We found like this in the below image :-
<img width="1715" height="744" alt="image" src="https://github.com/user-attachments/assets/3c6ecb58-e693-4bc5-9e8b-14ba486cbfe4" />


---

### Step 2: Decode Token
- Opened https://jwt.io  
- Pasted token  

<img width="1040" height="646" alt="image" src="https://github.com/user-attachments/assets/09c6c1dc-e8fa-4882-99d6-370981800108" />


---

### Step 3: Analyze Token

#### Header
```json
{
  "alg": "HS256"
}
```

---

#### Payload
```json
{
  "username": "WebGoat",
  "Email": "tom@webgoat.org",
  "Role": ["Manager", "Project Administrator"]
}
```

---

### Observations
- JWT is Base64 encoded, not encrypted
- Sensitive data like roles and email is visible
- Role-based access control depends on token
