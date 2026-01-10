# Phase 1: Reconnaissance & Enumeration Strategy
## Objective
Establish a comprehensive understanding of the target domain's structure, users, and critical assets with minimal network noise, prior to any exploitation attempt.
## Core Strategy & Techniques
1.  **Network & DNS Discovery:** Identify domain controllers and key servers by enumerating DNS records and testing for zone transfer (AXFR) vulnerabilities.
2.  **Active Directory Enumeration:** Map users, groups, and computers by querying LDAP services to identify high-value targets like service accounts.
3.  **Service & Attack Surface Mapping:** Conduct targeted port scans against identified critical servers to find potential entry points.
## Professional Considerations
*   **Stealth:** Preferring LDAP/DNS queries over broad, noisy port scans.
*   **Analysis:** Prioritizing targets (e.g., service accounts with SPNs) for higher probability of success.
