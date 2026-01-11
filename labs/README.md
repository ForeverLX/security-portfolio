# Offensive Security Lab Portfolio

This directory contains detailed write-ups and methodologies for over 60 hands-on security labs completed across multiple platforms. These exercises demonstrate practical, offensive security skills across the OWASP Top 10, binary exploitation, and real-world attack scenarios.

## 🎯 Executive Summary
This portfolio validates a methodical, attacker-minded approach through controlled exploitation of common and critical vulnerabilities. The labs progress from foundational web concepts to advanced binary exploitation and competitive capture-the-flag (CTF) challenges.

## 🔗 Navigation by Security Category
- **Web Application Security**: [`./web-security/`](./web-security/)
- **Reverse Engineering & Binary Exploitation**: [`./reverse-engineering/`](./reverse-engineering/)
- **Penetration Testing Scenarios**: [`./penetration-testing/`](./penetration-testing/)

## 📊 OWASP Top 10 Skills Mapping
| OWASP Top 10 Category | Labs & Techniques Demonstrated | Core Skills Validated |
| :--- | :--- | :--- |
| **A01: Broken Access Control** | IDOR (Parameter & Cookie Manipulation), CSRF (Social Media, Money Transfer), File Upload Bypasses. | Bypassing horizontal/vertical privilege checks, exploiting insecure direct object references (IDOR), and authorization flaws. |
| **A02: Cryptographic Failures** | JWT "none" algorithm attack, sensitive data exposure via SSTI/SSRF. | Identifying missing encryption, exploiting weak crypto, and accessing sensitive data. |
| **A03: Injection** | **SQLi:** Boolean/Time/Error-Based, Union-based data extraction.<br>**SSTI:** Flask/Jinja2, Twig template injection.<br>**Command Injection:** System command execution via web parameters. | Exploiting interpreter trust vulnerabilities, crafting context-aware payloads, and bypassing input filters. |
| **A04: Insecure Design** | Race Conditions (Discount Code, File Upload), Business Logic Flaws. | Identifying and exploiting time-of-check-time-of-use (TOCTOU) flaws and logic errors. |
| **A05: Security Misconfiguration** | SSRF accessing internal services, Default configurations leading to data leaks. | Leveraging verbose errors, default credentials, and unprotected files. |
| **A06: Vulnerable & Outdated Components** | Exploitation of known CVEs (Joomla CVE-2023-23752, ExifTool CVE-2021-22204). | Researching public exploits and weaponizing them against unpatched systems. |
| **A07: Identification & Authentication Failures** | Broken Authentication (Predictable Tokens), Login Brute-forcing, Session Hijacking via XSS. | Testing for weak login mechanisms and broken session management. |
| **A08: Software & Data Integrity Failures** | Insecure deserialization (conceptual), supply chain attacks. | Understanding trust boundaries in data and update mechanisms. |
| **A09: Security Logging & Monitoring Failures** | Evasion techniques, stealthy persistence in multi-step scenarios. | Operating with an awareness of defensive logging. |
| **A10: Server-Side Request Forgery (SSRF)** | Basic & Advanced SSRF labs, reading internal files and accessing hidden services. | Abusing server trust to probe internal networks and access cloud metadata. |

## 💼 Real-World Application & Impact
| Lab Category | Real-World Attack Scenario | Business Impact Demonstrated |
| :--- | :--- | :--- |
| **SSTI / Code Injection** | Compromising CI/CD pipelines or admin panels that use templates. | Data breach, source code theft, and ransomware deployment. |
| **SSRF** | Attacking cloud infrastructure by accessing internal metadata services. | Cloud account compromise, financial loss, and regulatory penalties. |
| **Race Conditions** | Exploiting fintech or e-commerce logic (e.g., "double-spend", coupon stacking). | Direct **financial loss** and inventory corruption. |
| **File Upload Bypasses** | Gaining initial foothold on a web server. | Website defacement, malware distribution, and lateral movement. |
| **Binary Exploitation** | Exploiting memory corruption in exposed services or for privilege escalation. | **Remote Code Execution (RCE)**, often with high privileges. |

## 🗺️ Skills Navigation Guide
**For a Web Application Penetration Tester Role:**
1.  Review all labs in `./web-security/`.
2.  Pay special attention to **SSTI**, **SSRF**, and **Race Conditions**.
3.  Study the **File Upload Bypass** techniques for practical initial access.

**For a Red Team / AD Specialist:**
1.  The `./penetration-testing/` scenarios demonstrate the initial exploit phase.
2.  The methodology in **Command Injection** and **Filter Bypass** labs is applicable to living-off-the-land tactics.

**For a Reverse Engineer / Vulnerability Researcher:**
1.  Focus on `./reverse-engineering/stacksmash/`.
2.  Analyze the **competitive problem-solving approach** in the write-ups.

## 🚀 Professional Value Statement
This portfolio provides **verifiable evidence** of:
*   **Methodical Execution:** A repeatable process of reconnaissance, analysis, exploitation, and documentation.
*   **Adaptive Problem-Solving:** Successfully bypassing filters, evading detection, and chaining vulnerabilities.
*   **Depth & Breadth:** Mastery of high-severity web vulnerabilities combined with competitive-grade low-level exploitation skills.
*   **Professional Communication:** Complex findings distilled into clear, actionable write-ups.

---
*All documented activities were performed in authorized, controlled lab environments for education and skill development.*
