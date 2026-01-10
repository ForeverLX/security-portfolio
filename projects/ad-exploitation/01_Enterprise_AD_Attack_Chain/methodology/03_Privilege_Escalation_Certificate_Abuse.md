# Phase 3: Privilege Escalation via ADCS Abuse
## Objective
Escalate privileges from a compromised domain user to Domain Administrator.
## Core Technique: Exploiting Certificate Template Vulnerabilities (ESC1)
Exploits templates that allow low-privileged users to enroll and specify an arbitrary Subject Alternative Name (SAN), enabling impersonation of any domain user.
## Professional Context & Impact
*   **Severity:** Often a **critical** finding leading to immediate domain compromise.
*   **Detection Difficulty:** Certificate-based authentication is trusted and may blend with legitimate traffic.
*   **Business Impact:** Direct path to complete domain takeover and access to all network assets.
