# Onboarding Guide: New Hire Day 1 Setup

## Purpose
Ensure every new hire is fully provisioned, secure, and productive on Day 1 with correct accounts, access, devices, and communication channels.

## Trigger
Use this guide when:
- A new employee is starting
- A contractor is being onboarded
- A role transfer requires full re-provisioning

## Steps

### 1. Validate HR Information
- Confirm start date
- Confirm manager
- Confirm department and role
- Confirm employment type (FTE, contractor, intern)

### 2. Create Identity Provider Account
In Okta / Entra ID / Google Workspace:
- Create user account
- Assign username format
- Set temporary password
- Enforce MFA enrollment on first login

### 3. Assign Required Groups & Roles
Add user to:
- Department groups
- Application access groups
- Security groups
- Distribution lists
- Shared mailboxes (if applicable)

### 4. Provision SaaS Applications
Assign licenses for:
- Slack / Teams
- Zoom
- Google Workspace / M365
- Zoho / Jira / Confluence
- Any role-specific tools

### 5. Prepare Device (Intune)

For Windows or macOS devices managed through Microsoft Intune:

- Assign the device to the correct user in Intune
- Confirm the device is enrolled and compliant
- Verify required configuration profiles are applied:
  - Security baselines
  - Compliance policies
  - Device restrictions
  - Endpoint protection settings
- Confirm required applications are installed:
  - M365 Apps
  - Browser (Edge/Chrome)
  - VPN client (if applicable)
  - Security agent (Defender for Endpoint)
- Validate that the device appears in:
  - Azure AD / Entra ID devices
  - Intune device list
  - Compliance dashboard

### 6. Configure MFA (Duo / PingID)

Depending on the organization’s MFA provider:

#### **Duo**
- Ensure Duo user is created or synced
- Assign user to correct Duo group/policy
- Confirm enrollment link is sent
- Validate successful activation

#### **PingID**
- Ensure PingID profile is created
- Assign user to correct authentication policy
- Confirm first-time enrollment instructions are provided
- Validate successful activation


### 6. Configure Email & Calendar
- Verify mailbox creation
- Confirm calendar availability
- Add to team calendars if needed

### 7. Send Welcome Email to User
Include:
- Login instructions
- MFA setup steps
- Device pickup or shipping details
- Support contact information

### 8. Notify Manager
Send confirmation that:
- Accounts are created
- Access is provisioned
- Device is ready
- User is Day 1 ready

## Expected Outcome
New hire can log in, access required systems, communicate with their team, and begin work without delays.

## Escalation
Escalate to:
- HR for missing or incorrect employee data
- Security for access anomalies
- Systems team for device enrollment failures

