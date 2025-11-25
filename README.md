# Vulpy (BAD Version) – Vulnerable Web Application

## Project Overview

Vulpy (BAD Version) is the intentionally vulnerable version of the Secure Vulpy project. It serves as the **baseline insecure application** used for analysis, testing, and hardening in the Secure Web Development CA2 assessment.

This version contains multiple known and deliberate vulnerabilities across authentication, session handling, database queries, access control, and user input processing. It is used **only for educational and testing purposes**.

---

## Insecure Features & Known Vulnerabilities

The BAD version includes the following intentionally insecure behaviors:

### Authentication & Password Issues

* Plaintext password storage
* No password complexity requirements
* Direct SQL queries without sanitization
* No credential lockout or brute-force protection

### Session Management Flaws

* Sessions stored in Base64 without integrity protection
* Session tokens not invalidated on logout
* No HttpOnly, Secure, or SameSite cookie flags
* Session fixation vulnerabilities

### SQL Injection Vulnerabilities

* All SQL queries are built using string formatting
* Easily exploitable via `' OR '1'='1` attacks

### Cross-Site Scripting (XSS)

* User-generated posts are rendered with unsafe Jinja filters
* Input is never sanitized
* No Content Security Policy (CSP)

### Broken Access Control / IDOR

* Any user can access `/posts/<username>`
* No role separation (admin ≠ user)
* Admin dashboard unprotected

### Missing CSRF Protection

* All POST endpoints accept forged requests
* No CSRF tokens in forms

### Summary of Critical Weaknesses

* SQL Injection (CWE-89)
* XSS (CWE-79)
* CSRF (CWE-352)
* IDOR / Broken Access Control (CWE-639)
* Insecure Session Handling (CWE-384)
* Plaintext Passwords (CWE-256)
* Missing Security Headers (CWE-693)

---

## Project Structure (BAD Version)

```
vulpy-bad/
│
├── bad/
│   ├── vulpy.py               # Main application, no security headers
│   ├── libuser.py           # Insecure login, plaintext passwords
│   ├── libposts.py          # SQL injection vulnerabilities
│   ├── libsession.py        # Weak session handling
│   ├── templates/           # Unsafe templates (XSS)
│   ├── static/              # Styles and assets
│   └── db_users.sqlite      # Insecure database with weak schema
└── README.md
```

---

## Setup (BAD Version)

### 1. Clone Repository

```bash
git clone <your_old_repo_url>
cd vulpy-bad
```

### 2. Create Virtual Environment

```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run Application

```bash
python bad/app.py
```

### 5. Access

```
http://127.0.1.1:5000
```

---

## 📚 References & Credits

* Original Vulnerable Repo: [https://github.com/fportantier/vulpy](https://github.com/fportantier/vulpy)
* Flask framework
* W3.CSS styling

---
