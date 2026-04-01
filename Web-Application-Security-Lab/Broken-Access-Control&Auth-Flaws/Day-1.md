## 🔓 Insecure Direct Object Reference (IDOR)

### What is IDOR?

IDOR is a type of access control vulnerability where an application exposes internal object identifiers (like user IDs, order IDs, file names) and fails to properly verify whether the user is authorized to access that object.

---

### In simple terms:

User changes an ID → gets someone else’s data

---

### How IDOR Happens
Applications use identifiers like:
- /user/1
- /orders/123
- /file/report.pdf
The server trusts the ID sent by the user
But does not check ownership

---

### Result:

- User can change ID → access unauthorized data
### Example
- GET /orders/101   → Your order
- GET /orders/102   → Another user's order (IDOR)

---

### Why IDOR Occurs
- Missing server-side authorization checks
- Over-reliance on client-side controls
- Predictable identifiers (1,2,3…)
- Developers assume users won’t manipulate requests

---

### Impact

IDOR can lead to:

-  Unauthorized data access
-  Data leakage (personal, financial data)
-  Data modification
-  Account takeover (in some cases)

---

### Types of IDOR
#### 1. Direct IDOR
- Changing numeric IDs
- Example: `/user/1 → /user/2`
#### 2. Indirect IDOR
- Using encoded or hashed IDs
- Still vulnerable if no auth check
#### 3. Authenticated IDOR
- Requires login
- Attack happens after authentication
#### 4. Blind IDOR
- No direct response
- Still exploitable (status-based, timing-based)
