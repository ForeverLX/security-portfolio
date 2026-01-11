# Server Configuration Override via .htaccess

## 🎯 Objective
Bypass comprehensive file upload restrictions by overriding server configuration.

## 🔍 Vulnerability Analysis
- **Type**: File upload with server configuration vulnerability
- **Target**: `smashing-raphael.apac01.hackviser.space`
- **Flaw**: `.htaccess` file processing enabled in upload directory
- **Impact**: Complete control over file execution behavior

## 💥 Exploitation
1. **Configuration File**: Created `.htaccess` defining custom extension as PHP
2. **File Upload**: Uploaded PHP web shell with custom extension
3. **Execution**: Server processed custom extension as PHP, enabling code execution

## 🛡️ Mitigation Strategies
1. **Disable .htaccess**: Set `AllowOverride None` in upload directories
2. **Directory Restrictions**: Limit Apache configuration override capabilities
3. **File Type Validation**: Implement content-based validation, not just extension
4. **Security Hardening**: Regular server configuration audits

## 📊 Skills Demonstrated
- **Server Configuration**: Understanding Apache `.htaccess` functionality
- **Configuration Override**: Modifying server behavior via uploaded files
- **Comprehensive Bypass**: Overcoming multiple layers of file validation

*Conducted in controlled environment for educational purposes*
