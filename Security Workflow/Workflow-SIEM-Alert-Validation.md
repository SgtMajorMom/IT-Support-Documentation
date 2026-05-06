# Security Workflow: SIEM Alert Validation

## Purpose
Provide a consistent, repeatable process for validating SIEM alerts, determining severity, and deciding whether escalation or containment is required.

## Trigger
Use this workflow when:
- A SIEM generates an alert (Defender, Sentinel, Splunk, etc.)
- Anomalous activity is detected in identity, endpoint, or network logs
- Alerts are assigned to IT/Security for triage

---

## 1. Review the Alert Details
Check the SIEM alert metadata:
- Alert name and category
- Severity level
- Timestamp
- Affected user or device
- Detection source (identity, endpoint, email, network)
- Correlated events or related alerts

Confirm whether this is:
- A single event  
- A repeated pattern  
- Part of a larger incident  

---

## 2. Validate the Entity (User or Device)
### User Validation
Check:
- Recent login activity
- MFA success/failure (Duo / PingID)
- Impossible travel or unusual locations
- Password reset history
- Group membership changes
- OAuth app grants

### Device Validation
Check:
- Intune compliance
- Defender for Endpoint alerts
- Recent configuration changes
- Unknown or unmanaged devices

---

## 3. Analyze Event Context
Depending on alert type:

### Identity Alerts
- Failed logins
- MFA bypass attempts
- Privilege escalation
- Unusual access patterns

### Endpoint Alerts
- Malware detections
- Suspicious processes
- Lateral movement attempts
- File modifications

### Email Alerts
- Phishing indicators
- Malicious attachments
- URL clicks

### Network Alerts
- Unusual outbound traffic
- Port scanning
- VPN anomalies

---

## 4. Determine User Intent
If the alert involves a user account:
- Contact the user
- Ask if they performed the action
- Document their response

If the user denies the activity, treat as **potential compromise**.

---

## 5. Containment (If Alert Appears Malicious)
Perform immediately:
- Reset user password
- Reset MFA (Duo / PingID)
- Terminate active sessions
- Revoke OAuth tokens
- Block suspicious IPs or devices
- Isolate endpoint (if malware or lateral movement suspected)

---

## 6. Correlate with Other Alerts
Check SIEM for:
- Related identity alerts
- Endpoint alerts on same device
- Email alerts for same user
- Network anomalies
- Multiple users affected

If multiple alerts correlate, escalate severity.

---

## 7. Document Findings
Record:
- Alert details
- Validation steps
- User confirmation
- Indicators of compromise
- Containment actions
- Whether escalation is required

---

## Expected Outcome
SIEM alerts are validated quickly, false positives are dismissed, and true positives are contained or escalated appropriately.

## Escalation
Escalate to Security if:
- Privileged accounts involved
- Malware or lateral movement detected
- Multiple correlated alerts appear
- Evidence of compromise is confirmed
