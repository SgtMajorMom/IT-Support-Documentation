# Onboarding Guide: New Hire Access Provisioning Checklist

## Purpose
Provide a consistent, secure, and complete checklist for provisioning all required accounts, access, and permissions for new hires.

## Trigger
Use this checklist when:
- A new employee is starting
- A contractor or intern is joining
- A role transfer requires full access reassignment

---

## 1. Identity Provider Setup (Okta / Entra ID / Google Workspace)
- [ ] Create user account
- [ ] Assign username and email address
- [ ] Set temporary password
- [ ] Enforce MFA enrollment on first login
- [ ] Add user to required identity groups

---

## 2. MFA Enrollment (Duo / PingID)
### Duo
- [ ] Confirm Duo user exists or is synced
- [ ] Assign to correct Duo group/policy
- [ ] Send enrollment link
- [ ] Verify activation

### PingID
- [ ] Confirm PingID profile created
- [ ] Assign authentication policy
- [ ] Provide enrollment instructions
- [ ] Verify activation

---

## 3. SaaS Application Provisioning
Assign licenses and access for:

### Communication & Collaboration
- [ ] Slack / Teams
- [ ] Zoom
- [ ] Email (Google Workspace / M365)

### Productivity
- [ ] Google Drive / OneDrive
- [ ] M365 Apps
- [ ] Shared drives or folders

### Department-Specific Tools
- [ ] CRM (Zoho, Salesforce, etc.)
- [ ] Ticketing system (Jira, Zendesk, Freshservice)
- [ ] Security tools (Proofpoint, Defender, etc.)
- [ ] Any role-specific SaaS platforms

---

## 4. Group Memberships & Permissions
- [ ] Department groups
- [ ] Distribution lists
- [ ] Security groups
- [ ] Application access groups
- [ ] Shared mailbox access (if needed)
- [ ] Calendar access (team calendars, resource calendars)

---

## 5. Device Assignment (Intune)
- [ ] Assign device to user in Intune
- [ ] Confirm enrollment
- [ ] Validate compliance status
- [ ] Confirm configuration profiles applied
- [ ] Confirm required apps installed
- [ ] Verify device appears in Entra ID

---

## 6. Access Validation
- [ ] User can sign in successfully
- [ ] MFA works
- [ ] Email accessible
- [ ] Required SaaS apps accessible
- [ ] Shared resources accessible
- [ ] Device compliant and functional

---

## 7. Manager Notification
- [ ] Confirm provisioning complete
- [ ] Provide login instructions for the user
- [ ] Provide device pickup/shipping details
- [ ] Confirm Day 1 readiness

---

## Expected Outcome
New hire has all required access, accounts, and tools to begin work on Day 1 without delays.

## Escalation
Escalate to:
- HR for missing employee data
- Security for MFA or identity issues
- Systems team for device enrollment failures
