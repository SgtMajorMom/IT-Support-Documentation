# Security Workflow: Suspicious Login Investigation

## Purpose
Provide a consistent, repeatable process for investigating suspicious login activity detected through IdP alerts, SIEM events, or user reports.

## Trigger
Use this workflow when:
- Impossible travel alerts occur
- Login from unusual location or device
- MFA bypass or repeated MFA failures
- User reports unauthorized access
- SIEM flags abnormal authentication behavior

---

## 1. Validate the Alert
Check identity provider logs (Okta, Entra ID, Google):
- IP address and geolocation
- Device fingerprint
- Browser/user agent
- MFA status (success, fail, bypass)
- Session creation time
- Previous successful logins

If using SIEM:
- Review correlated events
- Check for multiple failed attempts
- Look for lateral movement indicators

---

## 2. Contact the User
Ask the user:
- Did you attempt this login?
- Were you traveling?
- Did you use a VPN?
- Did you recently change devices?

Document their response.

---

## 3. Secure the Account (If User Did NOT Initiate Login)
Perform the following immediately:
- Reset password
- Reset MFA (Duo / PingID)
- Terminate active sessions
- Revoke refresh tokens
- Remove suspicious devices from account

In Entra ID:
- Mark user as “High Risk” if applicable
- Trigger risk-based remediation

---

## 4. Review Account Activity
Check for:
- Email forwarding rules
- OAuth app grants
- Admin role assignments
- File access anomalies
- Recent password changes
- Device join events
- Conditional Access policy failures

---

## 5. Validate Device Health
If the login came from a known device:
- Check Intune compliance
- Confirm Defender for Endpoint status
- Review recent alerts
- Validate encryption and security baselines

If the device is unknown:
- Flag for further investigation
- Consider blocking device ID

---

## 6. Document Findings
Record:
- Alert details
- User confirmation
- Actions taken
- Indicators of compromise (if any)
- Next steps or monitoring required

---

## Expected Outcome
Suspicious login is validated, user account is secured, and any unauthorized access is contained.

## Escalation
Escalate to Security if:
- Privileged account involved
- Multiple suspicious logins detected
- Evidence of compromise found
- Lateral movement indicators appear
