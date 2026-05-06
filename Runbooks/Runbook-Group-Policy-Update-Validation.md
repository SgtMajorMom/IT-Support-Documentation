# Runbook: Group Policy Update & Validation

## Purpose
Ensure Group Policy Objects (GPOs) are updated, applied, and validated across domain-joined devices.

## Trigger
Use this runbook when:
- A new GPO is created
- A GPO is modified
- A user reports policy not applying
- A scheduled GPO review occurs

## Steps

### 1. Identify the GPO
- Confirm GPO name and purpose
- Review linked OUs
- Validate security filtering

### 2. Force Policy Update
On the affected device:
- Run `gpupdate /force`
- Reboot if required

### 3. Validate Policy Application
Run:
- `gpresult /r`
- `gpresult /h report.html`

Check:
- Applied GPOs
- Denied GPOs
- Loopback settings
- Security filtering

### 4. Review GPO Settings
In Group Policy Management:
- Confirm correct settings
- Check inheritance
- Validate WMI filters
- Confirm replication (SYSVOL)

### 5. Document Changes
Record:
- GPO name
- Change details
- Who approved it
- Validation results

## Expected Outcome
GPO applies successfully and devices reflect updated settings.

## Escalation
Escalate to:
- Systems team for replication issues
- Security for policy conflicts
