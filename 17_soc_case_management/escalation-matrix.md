# SOC Escalation Matrix

## Purpose

This matrix defines when a SOC analyst should close, monitor or escalate a case.

---

## Tier 1 - Close / Monitor

### Conditions

- Known benign activity
- Lab-generated activity
- Expected admin action
- Low-volume failed login activity
- No compromise evidence

### Action

- Document findings
- Close ticket or monitor

---

## Tier 1 to Tier 2 Escalation

### Conditions

- Multiple failed logins followed by successful login
- Unexpected privileged logon
- Unknown service or scheduled task created
- PowerShell from suspicious parent process
- User added to Administrators group unexpectedly
- Security log cleared without approval

### Action

- Collect evidence
- Add timeline
- Assign severity
- Escalate to Tier 2

---

## Tier 2 to Incident Response Escalation

### Conditions

- Confirmed compromise
- Malware execution
- Credential theft suspected
- Lateral movement suspected
- Multiple hosts impacted
- Data exposure suspected
- Ransomware indicators

### Action

- Preserve evidence
- Recommend containment
- Notify IR team
- Continue documentation

---

## Emergency Escalation

### Conditions

- Ransomware
- Domain admin compromise
- Active data exfiltration
- Business-critical system impacted
- Widespread compromise

### Action

- Immediate escalation
- Endpoint isolation
- IR team engagement
- Leadership notification according to process

---

## Analyst Reminder

A good escalation includes:

- Alert summary
- Evidence queries
- Timeline
- Accounts and hosts involved
- Severity justification
- Recommended next steps
