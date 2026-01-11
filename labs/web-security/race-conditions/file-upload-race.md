# Race Condition - File Upload Validation Bypass

## 🎯 Objective
Exploit a file upload race condition to execute malicious code before validation completes.
# Race Condition: File Upload Validation Bypass

## 🎯 Objective
Exploit file upload race condition to execute malicious code before validation completes.

## 🔍 Vulnerability Analysis
- **Type**: Race Condition (file upload validation)
- **Target**: `possible-vision.apac01.hackviser.space`
- **Flaw**: Files saved temporarily before validation
- **Impact**: Remote code execution through uploaded files

## 💥 Exploitation
1. **Process Analysis**: Identified file save before validation
2. **Timing Attack**: Concurrent upload and access to uploaded file
3. **Execution Window**: Exploited narrow time window before validation
4. **Result**: Successfully executed code via uploaded file

## 🛡️ Mitigation Strategies
1. **Validation Before Save**: Validate files before writing to disk
2. **Atomic Operations**: Use atomic move operations after validation
3. **Secure Temporary Names**: Use cryptographically random temporary filenames
4. **File Type Verification**: Multiple validation methods (extension, MIME, content)

## 📊 Skills Demonstrated
- **Timing Analysis**: Identifying and exploiting narrow execution windows
- **File Upload Security**: Understanding file validation processes
- **Concurrent Execution**: Coordinating multiple simultaneous operations

*Conducted in controlled environment for educational purposes*
