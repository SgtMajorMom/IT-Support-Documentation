# Runbook: Quarterly Access Review Process

## Purpose
Ensure user access across SaaS platforms, identity systems, and internal applications is reviewed quarterly for compliance, least privilege, and audit readiness.

## Trigger
This runbook is executed at the start of each quarter or when requested by Compliance, Security, or Management.

## Steps

1. **Pull User Access Reports**
   - Export user lists from IdP (Okta, Entra ID, or Google Workspace).
   - Export access reports from SaaS platforms (Zoom, Slack, Zoho, M365, etc.).
   - Export group membership and admin role assignments.

2. **Validate Active Users**
   - Cross‑check HR roster vs. active accounts.
   - Flag terminated or inactive users.
   - Confirm contractors still require access.

3. **Review Elevated Permissions**
   - Identify users with admin, super admin, or privileged roles.
   - Validate business justification.
   - Document approvals or required removals.

4. **Send Manager Review Requests**
   - Provide each manager with a list of their direct reports and access levels.
   - Request confirmation or removal instructions.

5. **Apply Required Changes**
   - Remove unnecessary access.
   - Adjust group memberships.
   - Update admin roles.
   - Document all changes.

6. **Finalize Audit Log**
   - Save all exports, approvals, and change logs.
   - Store in the compliance folder for audit readiness.

## Expected Outcome
All user access is validated, unnecessary permissions are removed, and audit documentation is complete.

## Escalation
Escalate to:
- Security team for suspicious access patterns  
- Compliance for overdue approvals  
- Management for unresolved privileged access  
