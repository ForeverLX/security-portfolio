# Reflected XSS via HTML Attribute Manipulation

## 🎯 Objective
Trigger a reflected XSS attack where user input is placed inside an HTML attribute.

## 🔍 Vulnerability Analysis
- **Type**: Reflected Cross-Site Scripting (XSS)
- **Target**: Search functionality with reflected input
- **Parameter**: `q` (search query)
- **Flaw**: Input reflected inside HTML attribute without proper encoding
- **Impact**: JavaScript execution in victim's browser context

## 💥 Exploitation
**Challenge**: Angle brackets (`<`, `>`) were filtered/encoded

**Payload Development**:
" onfocus="alert(document.domain)" autofocus="

text

**How It Works**:
1. Closes the existing `value` attribute with `"`
2. Adds `onfocus` event handler with malicious JavaScript
3. Uses `autofocus` to trigger the event automatically
4. Remaining `"` closes the added attribute

**Result**: Successful XSS execution when victim interacts with the page

## 🛡️ Mitigation Strategies
1. **Context-Aware Encoding**: Different encoding for HTML vs. attributes vs. JavaScript
2. **Content Security Policy**: Restrict script execution sources
3. **Input Validation**: Whitelist-based validation for special characters
4. **Framework Security**: Use framework features that auto-escape output

## 📊 Skills Demonstrated
- **Context Analysis**: Understanding where input will be rendered
- **Filter Bypass**: Working within character restrictions
- **Event Handler Exploitation**: Using legitimate HTML attributes for malicious purposes

*Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.*
