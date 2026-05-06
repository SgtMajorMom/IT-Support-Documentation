# SOP: User Offboarding

## Purpose
Provide a consistent, secure, and compliant process for removing access, recovering assets, and deactivating accounts when an employee, contractor, or intern leaves the organization.

## Trigger
Use this SOP when:
- HR submits a termination request
- A contractor’s engagement ends
- A user is involuntarily or voluntarily separated
- A role change requires full deprovisioning

---

## 1. Validate Offboarding Request
- Confirm request came from HR or authorized manager
- Verify offboarding date and time
- Confirm whether access removal should be immediate or scheduled
- Check for any legal or HR holds

---

## 2. Disable Identity Access
### Identity Provider (Okta / Entra ID / Google)
- Disable user sign-in
- Revoke active sessions
- Reset password (if required by policy)
- Remove from all groups
- Revoke OAuth tokens
- Remove MFA devices (Duo / PingID)

### Conditional Access
- Ensure no policies still reference the user

---

## 3. Disable SaaS and Application Access
- Remove licenses (M365, Google Workspace, Zoom, Slack, etc.)
- Remove from shared drives and folders
- Disable CRM/HRIS/Finance access
- Remove from ticketing systems
- Remove from any admin roles

---

## 4. Secure Email and Data
- Convert mailbox to shared mailbox (if required)
- Grant manager access (if approved)
- Set auto-reply (optional)
- Archive mailbox per retention policy
- Export important files if requested and approved

---

## 5. Recover Assets
- Laptop or desktop
- Mobile devices
- Security tokens or badges
- Accessories (dock, charger, peripherals)
- Software or hardware licenses assigned to user

Document asset condition and serial numbers.

---

## 6. Device Actions (Intune / Endpoint Security)
- Mark device as “Retired” or “Wipe Pending”
- Remove from user assignment
- Trigger remote wipe if device is not returned
- Validate encryption status before wipe
- Remove from Defender for Endpoint

---

## 7. Remove Access from Internal Systems
- VPN
- Wi-Fi certificates
- File shares
- Internal portals
- Knowledge base or wiki accounts
- GitHub / GitLab / Bitbucket access

---

## 8. Validate Completion
Confirm:
- All accounts disabled
- All licenses removed
- All devices recovered or wiped
- All data archived
- All admin roles removed
- No active sessions remain

---

## 9. Document and Close
Record:
- Offboarding date
- Actions taken
- Assets recovered
- Exceptions or delays
- Final status (Complete / Pending / Escalated)

---

## Expected Outcome
User access is fully removed, assets are secured, and all identity, device, and data risks are eliminated.

## Escalation
Escalate to Security if:
- User is high-risk or privileged
- Device is lost or not returned
- Suspicious activity is detected during offboarding
- Legal hold is required

