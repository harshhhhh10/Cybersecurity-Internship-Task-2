# 🎣 Task 2 – Phishing Email Analysis

![Internship](https://img.shields.io/badge/Elevate%20Labs-Cybersecurity%20Internship-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Email%20Forensics-red?style=for-the-badge&logo=gmail&logoColor=white)
![Method](https://img.shields.io/badge/Method-Manual%20Analysis-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 📌 Objective

Analyze a sample phishing email to identify common warning signs, understand attacker techniques, and develop a defensive mindset against social engineering attacks.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Sample phishing email** (`.txt`) | Primary analysis target |
| **Raw email header file** | Authentication & routing analysis |
| **Manual URL inspection** | Identifying deceptive links (without clicking) |

---

## 📧 Email Scenario

The email **claims to be from the PayPal Security Team**, warning about an unusual login attempt and pressuring the recipient to verify their account within 24 hours or face suspension.

The message contains:
- A suspicious sender address
- Urgent warning language
- A verification link
- A PDF attachment requesting sensitive data

---

## 🚩 Phishing Indicators Identified

### 1️⃣ Spoofed Sender Address — Typosquatting
```
Fake:       security-alert@paypa1-verification.com
Legitimate: @paypal.com
```
The number **`1`** replaces the letter **`l`** in "paypal" — a classic **typosquatting** trick designed to fool users who glance quickly.

---

### 2️⃣ Email Authentication Failures

| Check | Result | Meaning |
|-------|--------|---------|
| **SPF** | ❌ Fail | Sender not authorized by domain |
| **DKIM** | ❌ None | No cryptographic signature |
| **DMARC** | ❌ Fail | Domain policy violated |

All three authentication mechanisms failed — a strong indicator of **email spoofing**.

---

### 3️⃣ Suspicious Originating IP
The email originated from an IP **unrelated to PayPal's mail infrastructure**, further confirming the sender is not who they claim to be.

---

### 4️⃣ Mismatched Reply-To Address
```
Reply-To: support@secure-check-login.ru
```
Completely different domain from the claimed sender — replies would go directly to the attacker.

---

### 5️⃣ Deceptive URL Structure
```
https://www.paypal.com.security-check-user-verification.ru/login
```
The **actual domain** is `security-check-user-verification.ru` — not PayPal.  
Attackers place the trusted brand name as a **subdomain** to mislead users.

---

### 6️⃣ Urgency & Psychological Pressure
The email uses fear-based language to rush the victim:
- *"Immediate action required"*
- *"Verify within 24 hours"*
- *"Account will be suspended"*

> Phishing often relies more on **psychological manipulation** than technical sophistication.

---

## 🎯 Likely Attack Objective

This is a **credential phishing attack**. The goal is to redirect users to a fake login page or collect financial details via the attached form.

If successful, the attacker could:
- Gain unauthorized account access
- Perform fraudulent transactions
- Steal personal and financial information

---

## 📸 Screenshots

All screenshots are in the [`/screenshots`](./screenshots) folder:

| File | Description |
|------|-------------|
| `01_phishing_email.png` | Full phishing email view |
| `02_sender_address.png` | Spoofed sender domain closeup |
| `03_email_header.png` | Raw header with SPF/DKIM/DMARC failures |
| `04_suspicious_url.png` | Deceptive link breakdown |

---

## 🧠 Key Learnings

- How to read and interpret raw email headers
- What SPF, DKIM, and DMARC are and why they matter
- How typosquatting and subdomain tricks work
- Why urgency is one of the most effective phishing weapons
- How to safely inspect URLs without clicking them

---

## 📁 Repository Structure

```
Cybersecurity-Internship-Task-2/
├── README.md
├── phishing_email_sample.txt
├── email_header.txt
└── screenshots/
    ├── 01_phishing_email.png
    ├── 02_sender_address.png
    ├── 03_email_header.png
    └── 04_suspicious_url.png
```
---

> 🔒 *This analysis was performed on a sample phishing email for educational purposes only as part of the Elevate Labs Cybersecurity Internship.*
