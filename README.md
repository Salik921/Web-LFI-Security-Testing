# Web-LFI-Security-Testing
Lab-based Local File Inclusion (LFI) exploitation in DVWA demonstrating vulnerable parameter identification, sensitive file disclosure, /proc/self/environ abuse, User-Agent injection via Burp Suite, and reverse shell execution. Performed strictly in a controlled environment for educational and ethical purposes.
# LFI Exploitation using DVWA (Lab-Based Project)

## 📌 Overview
This project demonstrates the exploitation of a **Local File Inclusion (LFI)** vulnerability in a **DVWA (Damn Vulnerable Web Application)** lab environment.

The attack chain covers:
- Vulnerable parameter identification
- Sensitive file disclosure
- `/proc/self/environ` abuse
- User-Agent injection using Burp Suite
- Reverse shell execution

> ⚠️ All activities were performed in a **controlled lab environment strictly for educational purposes**.

---

## 🧪 Lab Environment
- Application: DVWA
- Server-side Language: PHP
- Operating System: Linux
- Tools Used:
  - Browser
  - Burp Suite

---

## 🔍 Step-by-Step Exploitation

### 1️⃣ LFI Vulnerable Parameter Identified
A file inclusion vulnerability was identified in the `page` parameter.

**Example page=/../../../../../etc/passwd


📸 **Result:** Sensitive system files were disclosed.

![LFI passwd](screenshots/lfi-passwd.png)

---

### 2️⃣ Sensitive File Disclosure via LFI
Using directory traversal, additional files were accessed:

- `/etc/passwd`
- `/proc/self/environ`

📸 **Result:** PHP version and environment variables were exposed.

![proc environ](screenshots/proc-environ.png)

---

### 3️⃣ User-Agent Injection using Burp Suite
- HTTP request was intercepted using Burp Suite
- A malicious payload was injected into the **User-Agent** header
- The request was forwarded to the server

📸 **Result:** Payload execution confirmed through LFI.

![Burp User-Agent Injection](screenshots/burp-user-agent.png)

---

### 4️⃣ Reverse Shell Execution
After triggering the injected payload via LFI, a reverse shell was successfully obtained on the attacker machine (lab setup).

📸 **Result:** Shell access achieved.

![Reverse Shell](screenshots/reverse-shell.png)

---

## 🚨 Impact
- Sensitive information disclosure
- Environment variable leakage
- Remote Code Execution (RCE)
- Complete system compromise (lab environment)

---

## 🛡️ Mitigation Techniques
- Avoid dynamic file inclusion
- Validate and sanitize user input
- Disable unnecessary PHP configurations
- Implement least privilege on server files
- Apply secure coding practices

---

## 🧠 OWASP Top 10 Mapping
- **A01:2021 – Broken Access Control**
- **A05:2021 – Security Misconfiguration**
- **A09:2021 – Security Logging and Monitoring Failures**

---

## ⚠️ Disclaimer
This project is intended **strictly for educational and ethical purposes**.  
Do not attempt these techniques on systems you do not own or have explicit permission to test.

---

## 👤 Author
**Salik Karimkhan**  
Cybersecurity | Penetration Testing

