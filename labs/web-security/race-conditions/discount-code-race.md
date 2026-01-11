# Race Condition: Discount Code Redemption

## 🎯 Objective
Exploit time-of-check-time-of-use (TOCTOU) vulnerability to apply discount multiple times.

## 🔍 Vulnerability Analysis
- **Type**: Race Condition (TOCTOU)
- **Target**: `poetic-thunderball.apac01.hackviser.space`
- **Flaw**: Non-atomic discount code validation and application
- **Impact**: Financial loss through stacked discounts

## 💥 Exploitation
1. **Logic Analysis**: Identified discount validation before application
2. **Concurrent Requests**: Sent multiple simultaneous redemption requests
3. **Timing Exploitation**: Exploited window between validation and application
4. **Result**: Successfully applied single-use discount multiple times

## 🛡️ Mitigation Strategies
1. **Atomic Operations**: Use database transactions with proper locking
2. **Pessimistic Locking**: Implement row-level locks for critical operations
3. **Optimistic Concurrency**: Use versioning to detect race conditions
4. **Request Deduplication**: Implement idempotency tokens

## 📊 Skills Demonstrated
- **Concurrency Analysis**: Understanding timing vulnerabilities in web applications
- **Automated Testing**: Using scripts to trigger race conditions
- **Business Logic Security**: Identifying flaws in financial transaction logic

*Conducted in controlled environment for educational purposes*
