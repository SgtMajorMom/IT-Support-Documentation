# Troubleshooting: SSO Login Issues (Okta / Entra ID / SAML / OIDC)

## Purpose
Provide a structured process for diagnosing and resolving Single Sign-On (SSO) authentication issues across identity providers such as Okta, Entra ID, and Google, including SAML and OIDC-based applications.

## When to Use This Guide
Use this troubleshooting workflow when a user reports:
- Unable to sign in to an SSO-enabled application
- Redirect loop or stuck at login screen
- “You do not have access to this application”
- “Authentication failed” or “Invalid SAML response”
- MFA prompt not appearing during SSO
- App works directly but not through SSO

---

## 1. Identify the Error
Ask the user for:
- Exact error message
- Screenshot (if possible)
- Whether they can sign in to the identity portal (Okta / Entra / Google)
- Whether this is a new device or location
- Whether other SSO apps work

This determines if the issue is:
- User-specific  
- App-specific  
- IdP-wide  
- Policy-related  

---

## 2. Verify Identity Provider Login
Have the user sign in directly to:
- **Okta:** https://company.okta.com  
- **Entra ID:** https://myaccount.microsoft.com  
- **Google:** https://accounts.google.com  

If they **cannot** sign in:
- Follow standard sign-in troubleshooting  
- Reset password if needed  
- Reset MFA if needed  

If they **can** sign in:
- Issue is app-specific or policy-related

---

## 3. Check User Assignment (Okta / Entra / Google)
Verify the user is assigned to the application:
- Okta: Application → Assignments  
- Entra ID: Enterprise Applications → Users and Groups  
- Google: App Access Control  

If not assigned:
- Assign the user  
- Have them retry login  

If assigned:
- Confirm correct role or license is applied

---

## 4. Check SSO Protocol Errors (SAML / OIDC)
### Common SAML Errors
- **Invalid SAML response** → Certificate mismatch or expired  
- **App not configured for user** → Missing assignment  
- **Signature validation failed** → Wrong signing certificate  
- **Clock skew** → Device time incorrect  

### Common OIDC Errors
- **Invalid client ID/secret**  
- **Redirect URI mismatch**  
- **Token expired or invalid**  

If errors persist:
- Review IdP logs for detailed failure reason

---

## 5. Check MFA and Conditional Access
Verify:
- MFA is enrolled and functioning  
- No CA policies blocking access  
- No location-based restrictions  
- No device compliance requirements unmet  

If blocked by policy:
- Review sign-in logs  
- Adjust policy or add exception (if approved)

---

## 6. Check Device Compliance (If Required)
If the app requires a compliant device:
- Verify Intune compliance  
- Check OS version  
- Check encryption  
- Trigger device sync  
- Resolve compliance issues  

Retry SSO after compliance is restored.

---

## 7. Clear Browser and Session Issues
Have the user:
- Sign out completely  
- Close all browser windows  
- Clear cookies for the IdP domain  
- Try an incognito/private window  
- Try a different browser  

SSO failures often stem from stale sessions or cached tokens.

---

## 8. Test Authentication Flow
Perform controlled testing:
- Log in as a test user  
- Check if the app works for others  
- Review IdP logs for:
  - MFA failures  
  - Policy blocks  
  - Token issues  
  - SAML/OIDC errors  

If the issue is isolated to one user:
- Reassign the app  
- Reset MFA  
- Reset session tokens  

---

## 9. Escalation
Escalate to Identity/Security if:
- SAML certificate expired  
- App metadata changed  
- Redirect URIs changed  
- Multiple users affected  
- Federation configuration corrupted  
- App requires re-integration  

---

## Expected Outcome
User can successfully authenticate to the SSO-enabled application using the correct identity provider, with no policy, assignment, or protocol errors blocking access.
