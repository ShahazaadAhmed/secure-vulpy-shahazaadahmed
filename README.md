# 🔐 Secure Vulpy – Baseline Vulnerable Version

## Description

The **Secure Vulpy – Baseline Version** is the intentionally vulnerable starting point for the CA2 Web Security project. This version contains the original insecure code from:

🔗 **[https://github.com/fportantier/vulpy](https://github.com/fportantier/vulpy)** (BAD insecure version)

As required by CA2, this repository acts as the **baseline commit before any security patches** are applied. It also includes **additional features** such as RBAC (Role-Based Access Control) and admin-only navigation visibility, which were added *before* applying any security fixes.

This ensures a clear progression from:

❌ **Vulnerable →** ⚙️ **Modified (Features Added) →** 🛡️ **Secure Version**

Your live project repo:
👉 **[https://github.com/ShahazaadAhmed/secure-vulpy-shahazaadahmed](https://github.com/ShahazaadAhmed/secure-vulpy-shahazaadahmed)**

---

## 🧩 CA2 Project Requirements Fulfilled

This baseline repository fulfills the following CA2 requirements:

### ✔ Baseline Vulnerable Web Application

* Contains the original **BAD Vulpy code**, intentionally insecure.
* No security fixes applied in this stage.

### ✔ Additional Features Added *Before* Security Patching

The assignment requires adding at least one new feature **before** starting security fixes. Added features include:

#### 🔑 Role-Based Access Control (RBAC)

* Introduced user roles: **Admin** and **Normal User**.
* Role stored in the database/session.

#### 🧭 Admin-Only Navigation Bar Options

* Navigation items visible **ONLY** for admin users.
* Hidden from normal users.
* Demonstrates UI-level access control.

These features are intentionally introduced **into the vulnerable app**, as required by CA2 instructions.

### ✔ Commit-Based Development

Your GitHub commit history shows:

1. **Initial vulnerable baseline commit**
2. **Feature commits** (RBAC + Admin-only nav)
3. **Upcoming secure version commits** (patched vulnerabilities)

This commit flow clearly demonstrates the evolution from insecure → secure.

---

## 🚀 Features in This Baseline Version

### 🛑 Intentionally Vulnerable Components

* SQL injection points
* Weak authentication
* Missing input validation
* XSS vulnerabilities
* Insecure session handling
* Hardcoded secrets (as inherited from BAD version)

### 🆕 Added Features (Still Vulnerable)

These were added **before** any security patches:

* **RBAC** (Admin & User roles)
* **Admin-only navigation menu**
* **Extended backend logic for role checking**
* **Commit tracking & documentation for assessment**

These will be secured in later stages.

---

## 📦 Installation

```bash
git clone https://github.com/ShahazaadAhmed/secure-vulpy-shahazaadahmed
cd secure-vulpy-shahazaadahmed
pip install -r requirements.txt
python app.py
```

⚠️ **Warning:**
This is the baseline vulnerable version. Do NOT deploy it in a production environment.

---

## 📁 Project Structure

```
secure-vulpy-shahazaadahmed/
│
├── app.py                 # Main vulnerable web app
├── templates/             # HTML templates (some intentionally insecure)
├── static/                # CSS/JS
├── database.db            # SQLite DB with RBAC fields added
├── requirements.txt
└── README.md              # Project documentation
```

---

## 🧪 How to Test the Vulnerable Version

* Use Admin credentials (if included) to view admin-only UI
* Inspect RBAC logic introduced before patching
* Look for vulnerabilities (XSS, SQLi, IDOR, etc.)
* Navigate between admin/user views
* Test endpoint access with different roles

This version is purposely insecure for assessment and demonstration.

---

## 📘 How This Will Evolve

The next commits in the secure version will include:

* SQL injection prevention
* Input sanitization
* Output encoding
* Secure password hashing
* RBAC enforcement in backend
* Session protection (HttpOnly, Secure)
* CSRF protection
* Hardened templates & routes

Each fix will be documented in commit history + report.

---

## 🛡 Disclaimer

This project contains **intentionally vulnerable code** and is meant **only** for:

* Cybersecurity coursework (CA2)
* Ethical hacking practice
* Secure coding demonstrations

Do not use this code in real-world systems.

---

## 👨‍💻 Author

**Shahazaad Ahmed**
GitHub: [https://github.com/ShahazaadAhmed](https://github.com/ShahazaadAhmed)
