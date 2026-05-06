# Active Directory Group Management

## Purpose
Provide a consistent, secure, and auditable process for creating, modifying, reviewing, and removing Active Directory security and distribution groups.

## Trigger
Use this runbook when:
- A new group is requested  
- Membership changes are needed  
- Permissions must be updated  
- A group is no longer required  
- Audit or compliance reviews identify issues  

## Steps

### 1. Validate the Request
- Confirm the requester is authorized (manager, system owner, or application owner).
- Verify the business justification.
- Determine whether a new group is needed or an existing group can be used.

### 2. Determine Group Type
- **Security Group** — used for permissions, access control, RBAC.
- **Distribution Group** — used for email distribution only.
- **Mail-enabled Security Group** — hybrid use case.

### 3. Apply Naming Standards
Follow organizational naming conventions such as:
- `SEC-APP-RoleName`
- `DL-Department-Location`
- `APP-Access-Environment`

### 4. Create or Modify the Group
- Use ADUC, PowerShell, or Entra ID (if synced).
- Set group scope (Global, Universal, Domain Local).
- Add or remove members based on the request.
- Document the owner/approver.

### 5. Validate Permissions
If the group controls access:
- Test access with a non-admin account.
- Confirm the group is applied to the correct resource (folder, app, SaaS platform).
- Ensure no excessive permissions are granted.

### 6. Document the Change
Record:
- Requester  
- Approver  
- Group name  
- Purpose  
- Members added/removed  
- Permissions applied  
- Date/time  

### 7. Schedule Review
Groups must be reviewed:
- Quarterly (recommended)
- Immediately after role changes
- During access reviews

## Expected Outcome
Groups are created and maintained securely, consistently, and with full audit traceability.

## Escalation
Escalate to:
- Identity team for complex RBAC issues  
- Security team for privilege concerns  
- Application owners for unclear access requirements  
