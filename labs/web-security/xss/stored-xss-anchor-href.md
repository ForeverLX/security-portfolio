# Stored XSS via Anchor Href Attribute

## 🎯 Objective
Exploit stored XSS vulnerability within an anchor tag's `href` attribute.

## 🔍 Vulnerability Analysis
- **Type**: Stored Cross-Site Scripting (XSS)
- **Target**: News submission form with link field
- **Parameter**: `link` field stored in anchor `href` attribute
- **Flaw**: Direct insertion of user input into `href` without validation
- **Impact**: Persistent JavaScript execution for all users viewing the link

## 💥 Exploitation
**Attack Vector**: `javascript:` pseudo-protocol

**Payload**:
javascript:alert(document.domain)

text

**Execution**:
1. Submitted news item with malicious `href` value
2. Payload stored in database
3. Other users viewing news page see link with malicious `href`
4. Clicking link executes JavaScript in user's context

## 🛡️ Mitigation Strategies
1. **URL Validation**: Strict validation of URL schemes (allow only http/https)
2. **Attribute Encoding**: Proper encoding for HTML attributes
3. **Content Security Policy**: Restrict use of dangerous protocols
4. **User Education**: Warning about untrusted links

## 📊 Skills Demonstrated
- **Protocol Handler Exploitation**: Using `javascript:` pseudo-protocol
- **Stored XSS**: Understanding persistence in database-driven applications
- **User Interaction**: Leveraging required user action for execution

*Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.*
