# Incident Response: Hexar Ransomware Infrastructure Takedown

## 🎯 Objective
Investigate and infiltrate a ransomware group's infrastructure to gather intelligence, hijack administrative control, and recover decryption capabilities.

## 🔍 Initial Intelligence Gathering
- **Threat Artifact**: Ransom note file
- **Payment Portal**: Identified through victim ID analysis
- **First Flag**: Payment address obtained via portal interaction

## 💥 Exploitation Chain

### Phase 1: XSS in Support Chat
- **Vulnerability**: Unrestricted input in chat message parameter
- **Detection**: Server accepted both HTTP methods for same endpoint
- **Payload**: JavaScript cookie exfiltration to attacker-controlled server
- **Result**: Captured admin session cookie via HTTP listener

### Phase 2: Session Hijacking & Pivot
- **Challenge**: Admin panel required specific session context
- **Solution**: Manual cookie injection with proper path setting
- **Bypass**: Clear existing session, inject admin cookie, navigate to admin path

### Phase 3: Infrastructure Discovery
- **Secondary System**: File management interface
- **Access Method**: Default credentials identified
- **Intelligence Recovered**: Victim database and operational flags

## 🛡️ Mitigation Strategies
1. **Input Validation**: HTML entity encoding for all user-controlled outputs
2. **Session Security**: Security flags on all authentication cookies
3. **Method Enforcement**: Reject unsafe HTTP methods for state-changing operations
4. **Credential Management**: Eliminate default passwords for administrative tools

## 📊 Skills Demonstrated
- **Threat Intelligence Analysis**: Extracting actionable IOCs from ransomware artifacts
- **Web Application Exploitation**: Weaponizing stored XSS for session compromise
- **Operational Security**: Maintaining access through multiple authentication layers
- **Incident Response**: Proactive counter-intelligence against attacker infrastructure

*Conducted in controlled environment for educational purposes. All sensitive information (IPs, credentials, session tokens) has been sanitized for security.*
