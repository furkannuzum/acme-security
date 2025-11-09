---
name: Lab Submission
about: Submit your security incident lab analysis
title: '[SUBMISSION] Furkan Üzüm - Security Incident Lab'
labels: submission
assignees: ''
---

## 👤 Candidate Information

**Full Name:** Furkan Üzüm
**Email:** [Your Email Here]
**LinkedIn:** [https://www.linkedin.com/in/furkannuzum/](https://www.linkedin.com/in/furkannuzum/)
**Location:** Mamak/Ankara
**Submission Date:** 16.10.2024

---

## 📎 Submission Files

**Option A: Attached Files**
- **Report PDF:** [Attach here]
- **Video Link:** [YouTube / Vimeo / Loom link]

**Option B: External Links**
- **Report:** [Google Drive / Dropbox link]
- **Video:** [YouTube / Vimeo / Loom link]

---

## ⏱️ Time Tracking

**Total time spent:** 30 hours

**Breakdown:**
- **Log analysis:** 14 hours
- **Architecture design:** 3 hours
- **Report writing:** 4 hours
- **Video creation:** 3 hours

---

## 🎯 Summary

### Attack Vectors Identified

1.  **Broken Object Level Authorization (BOLA/IDOR) in the Trading API:** Exploitation of a systemic authorization flaw allowing an authenticated user to access and exfiltrate data from other users' accounts.
2.  **Web Application SQL Injection via WAF Bypass:** Successful injection of malicious SQL commands by using an obfuscated payload to evade the signature-based, misconfigured Web Application Firewall.
3.  **Employee Spear-Phishing via a Typosquatted Domain:** Use of social engineering and a fraudulent domain to attempt credential harvesting, which supported the overall attack chain.

### Key Findings

-   **Critical Authorization Failure:** The root cause was a systemic failure to enforce authorization. The system correctly validated user *authentication* (the 'who') but completely failed to verify *authorization* (the 'what'), enabling both the BOLA and SQLi attacks.
-   **Ineffective Perimeter Defense:** The Web Application Firewall (WAF) was critically misconfigured in a passive `DETECT-only` mode. This transformed a primary security control from an active shield into a passive observer, rendering it useless against the advanced SQLi attack.
-   **Insecure by Design:** The current architecture allows direct, unfiltered database queries from the web application. This is a fundamental design flaw that structurally enables injection attacks and eliminates any possibility of layered defense at the data level.

### Top 3 Recommendations

1.  **Implement Centralized Authorization & Decouple Database Access:** Redesign the architecture to enforce mandatory ownership checks at the API Gateway and introduce a Data Access Layer (DAL). This will fix the BOLA flaw at the perimeter and structurally eliminate all SQL injection risks.
2.  **Harden the Security Perimeter (WAF & Email):** Immediately reconfigure the WAF to an active `BLOCK` mode with an advanced rule set. Simultaneously, enforce DMARC (`p=reject`) on the Email Gateway to prevent domain spoofing and neutralize the phishing vector.
3.  **Enhance Identity Security & Proactive Monitoring:** Mandate Multi-Factor Authentication (MFA) for all customer and employee accounts to mitigate credential theft. Concurrently, centralize all security logs into a SIEM with automated alerting for correlated attack patterns to ensure real-time detection.

---

## 🛠️ Tools Used

**Analysis:**
- Excel
- Python

**Diagrams:**
- Mermaid Chart

**Video:**
- OBS Studio
- YouTube

**Other:**
- N/A

---

## ✅ Checklist

Please confirm:

- [x] Report is max 5 pages
- [x] Video is 10-15 minutes
- [x] All log files were analyzed
- [x] Timeline is timezone-corrected
- [x] Framework mappings included (MITRE ATT&CK, OWASP)
- [x] Architecture diagram included
- [x] Video link is tested and working
- [x] No plagiarism / proper attribution
- [x] Original work, not AI-generated

---

## 💬 Optional Feedback

**What did you think of this lab?**
[Your feedback here]

**Any suggestions for improvement?**
[Your suggestions here]

**Would you recommend this to others?**
- [x] Yes
- [ ] No
- [ ] Maybe

---

## 📧 Contact Preference

**Preferred contact method:**
- [x] Email
- [x] LinkedIn
- [x] GitHub

**Best time to reach you:**
all time...

---

## ⚖️ Declaration

I declare that this submission is my original work and I have followed all guidelines.

**Name:** Furkan Üzüm
**Date:** 16.10.2024
---

_Thank you for your submission! We'll review it and get back to you within 1 week._
