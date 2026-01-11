# Insecure Direct Object Reference (IDOR) Exploitation

## 🎯 Objective
Demonstrate multiple IDOR attack vectors to access unauthorized resources.

## 🔍 Vulnerability Analysis
- **Type**: Insecure Direct Object Reference (IDOR)
- **Common Flaw**: Using client-supplied identifiers without authorization checks
- **Impact**: Unauthorized data access and horizontal privilege escalation

## 💥 Exploitation Examples

### Example 1: Hidden Form Field Manipulation
- **Target**: Password change functionality
- **Parameter**: Hidden `user_id` field in HTML form
- **Attack**: Modify `user_id` value to target different user
- **Result**: Unauthorized password change for other users

### Example 2: Cookie Parameter Manipulation
- **Target**: User profile viewing
- **Parameter**: `id` value stored in browser cookie
- **Attack**: Modify cookie value to access different user profiles
- **Result**: Unauthorized access to other users' personal information

### Example 3: URL Parameter Manipulation
- **Target**: Various application endpoints
- **Parameter**: Numeric IDs in URL paths or query strings
- **Attack**: Increment/decrement ID values
- **Result**: Access to unauthorized objects and data

## 🛡️ Mitigation Strategies
1. **Authorization Checks**: Server-side verification of user permissions
2. **Indirect References**: Use unpredictable tokens instead of sequential IDs
3. **Session-Based Access**: Derive user identity from session, not client input
4. **Access Control Lists**: Implement proper ACLs for all resources

## 📊 Skills Demonstrated
- **Multiple Vector Identification**: Finding IDOR in forms, cookies, and URLs
- **Horizontal Privilege Escalation**: Accessing same-level user data
- **Authorization Bypass**: Circumventing access controls through parameter manipulation

*Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.*
