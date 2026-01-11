# CSRF - Social Media Follow Exploitation

## 🎯 Objective
Demonstrate Cross-Site Request Forgery by forcing user actions without consent through crafted web requests.

## 🔍 Vulnerability Analysis
- **Type:** Cross-Site Request Forgery (CSRF)
- **Endpoint:** `GET /index.php`
- **Parameter:** `follow`
- **Detection:** State-changing actions accessible via GET requests without anti-CSRF tokens
- **Impact:** Unauthorized user actions leading to social engineering and account compromise

## 💥 Exploitation
```html
<!-- Malicious page hosted on attacker server -->
<img src="http://seabirdsocial.hv/index.php?follow=attacker" width="0" height="0" />
When a logged-in user visits a page containing this image, the browser automatically sends the follow request with the user's session cookies.

Result: Victim follows attacker account, revealing secret keyword: Sunflowers

🛡️ Mitigation Strategies
Anti-CSRF Tokens: Implement unique tokens for all state-changing requests

SameSite Cookies: Use SameSite=Strict or Lax cookie attributes

Request Method Validation: Restrict state-changing actions to POST requests only

Referrer Validation: Check request origin where applicable

📊 Skills Demonstrated
CSRF Payload Crafting: Creating effective CSRF proof-of-concept exploits

Session Understanding: Leveraging browser cookie behavior for attack delivery

Impact Analysis: Assessing real-world consequences of CSRF vulnerabilities

Defense Bypass: Understanding limitations of partial CSRF protections

Conducted in controlled environment for educational purposes
