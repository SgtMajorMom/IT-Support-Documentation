# Onboarding Guide: New Hire Device Setup (Intune)

## Purpose
Provide a consistent process for preparing, enrolling, and validating new hire devices using Microsoft Intune.

## Trigger
Use this guide when:
- A new hire is starting
- A device is being reassigned
- A replacement device is issued

---

## 1. Pre‑Setup Validation
- Confirm device is assigned to the correct user in Intune
- Verify device is listed in Entra ID (Azure AD)
- Confirm hardware details match the asset record
- Ensure device is wiped or reset to Out‑of‑Box Experience (OOBE)

---

## 2. Device Enrollment (Windows or macOS)
### Windows Enrollment
- Boot device to OOBE
- Connect to network
- Sign in with new hire’s credentials
- Confirm automatic Intune enrollment begins
- Wait for initial configuration profiles to apply

### macOS Enrollment (if applicable)
- Boot device to setup assistant
- Connect to network
- Sign in with corporate Apple ID (if required)
- Confirm Intune Company Portal enrollment
- Approve required system extensions and profiles

---

## 3. Apply Configuration Profiles
Verify the following profiles are applied:
- Security baselines
- Compliance policies
- Device restrictions
- Endpoint protection
- BitLocker/FileVault encryption policies
- Wi‑Fi/VPN profiles (if applicable)

---

## 4. Required Application Installation
Confirm installation of:
- Microsoft 365 Apps
- Teams or Slack
- Browser (Edge/Chrome)
- VPN client (if used)
- Security agent (Microsoft Defender for Endpoint)
- Any department‑specific applications

---

## 5. MFA Setup (Duo / PingID)
### Duo
- Confirm Duo enrollment prompt appears on first login
- Assist user with device activation
- Validate successful push notification test

### PingID
- Confirm PingID activation link is sent
- Assist user with mobile app setup
- Validate successful authentication test

---

## 6. Compliance Validation
In Intune:
- Confirm device status = **Compliant**
- Validate:
  - Encryption enabled
  - Antivirus active
  - Firewall enabled
  - No outstanding policy conflicts

---

## 7. Final Device Checks
- User can sign in without issues
- MFA works consistently
- Email and calendar sync correctly
- Required apps launch successfully
- Device appears healthy in Intune dashboard

---

## Expected Outcome
New hire receives a fully configured, secure, and compliant device ready for Day 1 productivity.

## Escalation
Escalate to:
- Systems team for enrollment or profile failures
- Security team for MFA or compliance issues
