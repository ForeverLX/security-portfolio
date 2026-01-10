# Phase 2: Initial Access via Kerberos Abuse
## Objective
Transition from an unauthenticated external actor to possessing valid domain credentials.
## Core Technique: AS-REP Roasting
Targets user accounts with "Do not require Kerberos preauthentication" enabled. Allows an attacker to request an encrypted authentication response that can be taken offline for cracking.
## Professional Context & Impact
*   **Stealth:** Does not generate traditional failed login attempts.
*   **Critical Finding:** Indicates legacy configuration or oversight.
*   **Business Impact:** Compromised credentials, especially for service accounts, can lead to unauthorized access to critical systems.
