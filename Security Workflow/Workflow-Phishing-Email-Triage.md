# Security Workflow: Phishing Email Triage

## Purpose
Provide a consistent, repeatable process for analyzing, validating, and responding to suspected phishing emails reported by users or detected by security tools.

## Trigger
Use this workflow when:
- A user reports a suspicious email
- Proofpoint / Defender flags a phishing attempt
- SIEM generates an email-based alert
- Anomalous email activity is detected

---

## 1. Collect the Email Safely
Request the user to:
- Forward the message as an attachment (.eml or .msg)
- Avoid clicking links or opening attachments
- Provide context (Did they interact with it? When did they receive it?)

Store the sample in a secure analysis folder.

---

## 2. Analyze Email Headers
Review:
- Sender address and domain
- Return‑Path
- SPF, DKIM, DMARC results
- Source IP and geolocation
- Reply‑To address
- Message‑ID anomalies

Red flags include:
- Domain spoofing
- Mismatched sender vs. return‑path
- Failed SPF/DKIM/DMARC
- Newly registered domains

---

## 3. Inspect Email Body
Check for:
- Urgent or threatening language
- Requests for credentials or MFA codes
- Suspicious links or QR codes
- Unexpected attachments
- Branding inconsistencies

If links exist:
- Hover to inspect URL
- Use a safe URL decoder (no live clicking)

If attachments exist:
- Do NOT open locally
- Use sandbox or security tool analysis

---

## 4. Check User Interaction
Ask the user:
- Did you click any links?
- Did you enter credentials?
- Did you download/open attachments?
- Did you reply to the sender?

Document their answers.

If the user interacted, proceed to **Account Containment**.

---

## 5. Containment (If User Interacted)
Perform immediately:
- Reset user password
- Reset MFA (Duo / PingID)
- Terminate active sessions
- Revoke OAuth tokens
- Review mailbox rules for forwarding
- Check for unauthorized app grants

If attachments were opened:
- Validate device compliance in Intune
- Check Defender for Endpoint alerts
- Run a quick scan or full scan

---

## 6. Block and Report
Depending on tools available:
- Block sender domain in Barracuda / Defender / Microsoft Tenant
- Add URL to blocklist
- Submit sample to security vendor
- Update anti‑phishing policies
- Tag email as malicious in SIEM

---

## 7. Notify and Educate User
Send a brief message:
- Confirming the email was malicious or safe
- Advising next steps
- Reinforcing safe email practices

If user interacted:
- Provide additional security awareness guidance

---

## 8. Document Findings
Record:
- Email details
- Header analysis
- User interaction
- Containment actions
- Indicators of compromise
- Recommendations
- Escalation (if needed)

---

## Expected Outcome
Phishing attempts are identified, contained, and remediated quickly with minimal user impact.

## Escalation
Escalate to Security if:
- Multiple users received the same email
- User credentials were compromised
- Malware was executed
- Lateral movement indicators appear
