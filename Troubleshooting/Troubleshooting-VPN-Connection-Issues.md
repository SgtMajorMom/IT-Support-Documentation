# Troubleshooting: VPN Connection Issues (AnyConnect / OpenVPN / GlobalProtect)

## Purpose
Provide a structured process for diagnosing and resolving VPN connection issues related to authentication, network connectivity, certificates, MFA, or endpoint compliance.

## When to Use This Guide
Use this troubleshooting workflow when a user reports:
- Unable to connect to VPN
- VPN stuck on “Connecting…”
- Authentication or MFA failures
- “No valid certificate” or “Connection timed out”
- VPN connects but no internal resources are reachable
- Frequent disconnects or unstable connection

---

## 1. Identify the Error
Ask the user for:
- Exact error message
- Screenshot (if possible)
- Whether MFA prompt appears
- Whether this is a new device or network
- Whether VPN worked previously

This determines if the issue is:
- Network-related
- Identity-related
- Certificate-related
- Client-related
- Policy-related

---

## 2. Check Network Connectivity
Verify:
- User has internet access
- No captive portal (hotel, airport, guest Wi-Fi)
- Try switching networks (home Wi-Fi → hotspot)
- Try wired vs. wireless if available

If internet is unstable:
- VPN will fail or disconnect frequently

---

## 3. Check Identity & Authentication
Verify:
- User account is active
- Password is correct
- MFA is functioning
- No lockouts or suspicious activity flags

If MFA is failing:
- Reset MFA
- Have user re-enroll device
- Retry VPN connection

---

## 4. Check VPN Client Status
### AnyConnect
- Restart the client
- Check for “Service not running”
- Reinstall if corrupted

### OpenVPN
- Confirm correct `.ovpn` profile
- Ensure no duplicate profiles
- Run as administrator (Windows)

### GlobalProtect
- Check portal address
- Click “Refresh Connection”
- Restart the GlobalProtect service

---

## 5. Check Certificates (If Required)
Verify:
- User certificate is installed
- Certificate is not expired
- Device has correct root/intermediate certs
- No duplicate certificates

If certificate is missing:
- Reinstall via MDM or IT provisioning
- Restart VPN client

---

## 6. Check Device Compliance (Intune / Endpoint Security)
Some VPNs require:
- Device compliance
- Encryption enabled
- OS up to date
- No malware alerts
- No security baseline failures

Steps:
- Trigger device sync
- Resolve compliance issues
- Retry VPN connection

---

## 7. Check Firewall or Security Software
Verify:
- Local firewall not blocking VPN client
- No third-party antivirus blocking tunnels
- Split-tunnel vs. full-tunnel settings

If blocked:
- Add VPN client to allowed list
- Restart device

---

## 8. Check DNS & Routing
If VPN connects but internal resources fail:
- Flush DNS
- Restart network adapter
- Check for conflicting routes
- Verify DNS servers assigned by VPN

Commands (Windows):
- `ipconfig /flushdns`
- `ipconfig /release`
- `ipconfig /renew`

Commands (Linux/macOS):
- Restart network service
- Clear DNS cache

---

## 9. Reinstall or Reset VPN Client
If corruption suspected:
- Uninstall VPN client
- Reboot
- Reinstall latest version
- Re-import VPN profile (OpenVPN)

---

## 10. Escalation
Escalate to Network/Security if:
- Multiple users affected
- VPN gateway unreachable
- Certificate authority issues
- Authentication server down
- Routing or firewall misconfiguration

---

## Expected Outcome
User can successfully connect to the VPN, authenticate with MFA, and access internal resources without errors or disconnections.
