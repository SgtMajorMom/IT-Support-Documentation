# Security Workflow: Endpoint Investigation

## Purpose
Provide a structured, repeatable process for investigating endpoint alerts, suspicious activity, or potential compromise on managed devices using Intune, Defender for Endpoint, and identity logs.

## Trigger
Use this workflow when:
- Defender for Endpoint generates an alert
- Intune shows a device as non‑compliant
- A user reports unusual device behavior
- SIEM correlates identity + device anomalies
- Malware or suspicious processes are detected

---

## 1. Validate the Alert
Review the alert details in Defender for Endpoint:
- Alert title and severity
- Detection source (behavioral, signature, cloud)
- Affected device and user
- Timestamp and event chain
- Related alerts or correlated incidents

Check if the alert is:
- New  
- Repeated  
- Part of a larger incident  

---

## 2. Identify the User and Device
Confirm:
- Device owner (from Intune)
- Device compliance status
- OS version and patch level
- Recent configuration changes
- Whether the device is corporate or personal (BYOD)

Cross‑check identity logs:
- Recent logins
- MFA success/failure (Duo / PingID)
- Impossible travel or unusual locations
- OAuth app grants

---

## 3. Analyze Device Activity
In Defender for Endpoint:
- Review process tree
- Check for suspicious executables
- Look for unusual parent/child processes
- Review network connections
- Check for file modifications
- Inspect command‑line arguments

Red flags include:
- PowerShell spawned by Office apps
- Unknown executables in temp folders
- Connections to known malicious IPs
- Persistence mechanisms (registry, scheduled tasks)

---

## 4. Check for Malware or Indicators of Compromise
Perform:
- Quick scan
- Full scan (if needed)
- Review quarantine items
- Check threat history

If malware detected:
- Confirm remediation status
- Validate no additional payloads remain

---

## 5. Validate Intune Compliance
Check:
- Device compliance = **Compliant / Non‑Compliant**
- Encryption status (BitLocker/FileVault)
- Security baseline applied
- Endpoint protection policies applied
- Pending OS or app updates

If non‑compliant:
- Identify root cause
- Trigger sync
- Reapply configuration profiles

---

## 6. Containment (If Suspicious or Malicious Activity Confirmed)
Perform immediately:
- Isolate device in Defender for Endpoint
- Terminate malicious processes
- Block malicious IPs or domains
- Reset user password
- Reset MFA (Duo / PingID)
- Revoke active sessions and tokens

If lateral movement suspected:
- Escalate to Security immediately

---

## 7. Remediation
Depending on findings:
- Remove malicious files
- Uninstall suspicious applications
- Apply OS or app patches
- Reapply Intune configuration profiles
- Re‑enroll device if corrupted
- Restore from backup if necessary

---

## 8. Validate Post‑Remediation Health
Confirm:
- No new alerts in Defender
- Device returns to **Compliant** in Intune
- No suspicious processes running
- No unauthorized persistence mechanisms
- User can authenticate normally
- MFA functioning correctly

---

## 9. Document Findings
Record:
- Alert details
- Device and user involved
- Investigation steps
- Indicators of compromise
- Containment actions
- Remediation steps
- Final status (Resolved / Escalated)

---

## Expected Outcome
Endpoint threats are identified, contained, and remediated quickly, ensuring device integrity and preventing further compromise.

## Escalation
Escalate to Security if:
- Privileged accounts involved
- Malware persists after remediation
- Lateral movement indicators appear
- Multiple devices show similar alerts
