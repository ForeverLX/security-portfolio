# Basic SSRF - improved-wolfpack.apac01.hackviser.space

## 🎯 Objective
Exploit a Server-Side Request Forgery vulnerability to read internal system files and gather server information.

## 🔍 Vulnerability Analysis
- **Type:** Server-Side Request Forgery (SSRF)
- **Endpoint:** `GET /fetch.php`
- **Parameter:** `url`
- **Detection:** URL parameter passed directly to file retrieval function without protocol validation
- **Impact:** Internal file disclosure and service enumeration

## 💥 Exploitation
```http
GET /fetch.php?url=file:///etc/hostname HTTP/1.1
Host: improved-wolfpack.apac01.hackviser.space
Result: Successfully extracted server hostname through file protocol SSRF, revealing internal system information.

🛡️ Mitigation Strategies
Input Validation: Implement strict URL validation and protocol whitelisting

Network Segmentation: Restrict server access to internal networks

Allow Lists: Use domain/IP allow lists instead of blocking specific protocols

Outbound Proxies: Route all outbound requests through controlled proxies with filtering

📊 Skills Demonstrated
Protocol Handling: Exploiting file:// protocol for local file access

Internal Reconnaissance: Using SSRF for internal network and system enumeration

Impact Assessment: Understanding data exposure risks from internal file access

Bypass Techniques: Leveraging different URL schemes for SSRF exploitation

Conducted in controlled environment for educational purposes
