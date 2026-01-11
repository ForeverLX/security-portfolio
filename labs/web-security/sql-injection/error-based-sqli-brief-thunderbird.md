# Error-Based SQL Injection

## 🎯 Objective
Extract database information by triggering and analyzing SQL error messages.

## 🔍 Vulnerability Analysis
- **Type**: Error-Based SQL Injection
- **Target**: Web application with an `img` parameter vulnerable to SQL injection
- **Flaw**: Improper error handling revealing database information
- **Impact**: Database structure disclosure and information extraction

## 💥 Exploitation

### Initial Challenge
- **First Attempt**: Direct error-based technique failed due to HTTP redirect
- **Issue**: 302 redirect prevented immediate error reflection

### Solution
- **Target Identification**: Final redirected URL containing vulnerable parameter
- **Tool Usage**: sqlmap without technique restriction for automatic detection
- **Command**:
  ```bash
  sqlmap -u "https://target/index.php?img=1" --batch --dbs
Result: Successfully extracted database information

🛡️ Mitigation Strategies
Error Handling: Generic error messages without database details

Input Validation: Parameterized queries and strict type checking

Security Headers: Prevent information disclosure through proper HTTP configurations

Regular Testing: Continuous vulnerability assessment

📊 Skills Demonstrated
Error Analysis: Interpreting SQL error messages for information extraction

Tool Proficiency: Adapting sqlmap usage based on application behavior

Persistence: Overcoming initial failed attempts with alternative approaches

Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.
