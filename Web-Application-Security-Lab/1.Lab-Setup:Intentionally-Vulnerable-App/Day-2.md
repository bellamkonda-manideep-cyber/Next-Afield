### Burp Suite Configuration (HTTP Proxy)
- Burp Setup
- Launched Burp Suite Community Edition
- Enabled Proxy Intercept
<img width="1598" height="837" alt="image" src="https://github.com/user-attachments/assets/ea3f21b2-20e7-45ff-93ec-b5954283ee83" />

---

### Browser Proxy Configuration (Firefox)
- Manual Proxy Configuration:
    - HTTP Proxy: 127.0.0.1
    - Port: 8080
- Enabled proxy for all protocols
<img width="759" height="688" alt="image" src="https://github.com/user-attachments/assets/a6870021-94b4-402e-b6a1-4938f20c1a28" />

---

### Installing Burp CA Certificate
- Opened: http://burp in browser
- Downloaded CA certificate
<img width="1718" height="795" alt="image" src="https://github.com/user-attachments/assets/7e93e126-54d2-405c-bda1-040994506f9c" />

- Imported into Firefox:
    - Settings → Privacy & Security → Certificates → Import

---

### Verification
- Opened DVWA in browser
- Intercepted HTTP request successfully in Burp
<img width="1597" height="477" alt="image" src="https://github.com/user-attachments/assets/b460a908-2177-40bb-8387-81a074a5f802" />
