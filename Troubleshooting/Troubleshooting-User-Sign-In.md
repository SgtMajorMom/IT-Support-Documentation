# Troubleshooting: User Cannot Sign In

## Purpose
Provide a structured process for diagnosing and resolving user login issues related to identity, MFA, password, device compliance, or account lockouts.

## When to Use This Guide
Use this troubleshooting workflow when a user reports:
- Unable to sign in to any system
- MFA prompts not appearing or failing
- Password not accepted
- Account locked or disabled
- “Access denied” or “Authentication failed” errors
- Conditional Access blocking sign-in

---

## 1. Identify the Error
Ask the user for:
- Exact error message
- Screenshot (if possible)
- Whether MFA prompt appears
- Whether password is accepted
- Whether this is a new device or location

---

## 2. Check Account Status (Okta / Entra ID / Google)
Verify:
- Account is **active**
- Account is **not locked**
- No suspicious activity flags
- No recent password reset failures
- No forced password change pending

If locked:
- Unlock the account
- Ask user to try again

If disabled:
- Confirm with manager or HR before re-enabling

---

## 3. Validate Password
Ask:
- “Did you recently change your password?”
- “Are you using an old saved password?”

Steps:
- Have user manually type password (no autofill)
- If still failing, perform a password reset
- Confirm user can sign in to the identity portal

---

## 4. Check MFA Status (Duo / PingID / Authenticator)
Verify:
- MFA device is enrolled
- No duplicate or stale devices
- Push notifications are enabled
- User is not on a new phone without re-enrollment

If MFA is broken:
- Reset MFA
- Have user re-enroll their device
- Test authentication

---

## 5. Check Conditional Access or Security Policies
Common blocks:
- Sign-in from new or risky location
- Device not compliant
- Unsupported OS or browser
- Legacy authentication blocked

Actions:
- Review sign-in logs
- Confirm policy applied
- Validate device compliance (Intune)

---

## 6. Check Device Compliance (Intune)
Verify:
- Device is compliant
- OS is up to date
- Encryption enabled (BitLocker/FileVault)
- No security baseline failures
- No pending reboot required

If non-compliant:
- Trigger device sync
- Resolve compliance issues
- Retry login

---

## 7. Check SaaS Application Status
If identity login works but app login fails:
- Confirm license assigned
- Confirm app role assigned
- Check for expired sessions
- Revoke sessions and have user sign in again

---

## 8. Test Authentication
Have the user:
- Sign in via identity portal (Okta / Entra / Google)
- Approve MFA
- Access a known working app (Outlook, Drive, etc.)

If successful:
- Issue resolved

If still failing:
- Continue to escalation

---

## 9. Escalation
Escalate to Security or Identity Team if:
- Multiple failed MFA attempts from unknown locations
- Impossible travel alerts
- Suspicious IP addresses
- Repeated lockouts
- User reports unauthorized access

---

## Expected Outcome
User can successfully authenticate using correct password, MFA, and compliant device, with no policy or identity blocks preventing access.

