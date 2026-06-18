# SOC Case Management Playbook

## Purpose

This playbook documents the basic SOC case handling lifecycle for alerts, incidents and investigation tickets.

---

## Standard Ticket Lifecycle

```text
Alert Received
  -> Ticket Created
  -> Initial Triage
  -> Evidence Collection
  -> Investigation
  -> Severity Assignment
  -> Escalation Decision
  -> Closure / Escalation
```

---

## Step 1 - Alert Intake

Capture:

- Alert name
- Alert source
- Event ID
- Affected host
- Affected account
- Timestamp
- Severity from SIEM/tool

---

## Step 2 - Initial Triage

Ask:

- What happened?
- Who is affected?
- Which host is involved?
- When did it happen?
- Is this expected activity?

---

## Step 3 - Evidence Collection

Use SIEM queries to collect supporting evidence.

Examples:

```kql
SecurityEvent
| where EventID == 4625
| sort by TimeGenerated desc
```

```kql
SecurityEvent
| where EventID in (4624, 4625, 4672, 4688, 4697, 4698, 1102)
| sort by TimeGenerated desc
```

---

## Step 4 - Correlation

Check related activity:

- Failed logons
- Successful logons
- Privileged logons
- PowerShell execution
- Service installation
- Scheduled task creation
- Account creation
- Group membership change
- Log clearing

---

## Step 5 - Severity Classification

Classify as:

- Informational
- Low
- Medium
- High
- Critical

Severity depends on impact, confidence and context.

---

## Step 6 - Escalation Decision

Escalate if:

- Compromise is suspected
- Evidence is unclear but risky
- Privileged account is involved
- Persistence is unauthorized
- Multiple hosts are affected
- Logs were cleared unexpectedly

---

## Step 7 - Closure Notes

A good closure note includes:

- What was reviewed
- What was found
- Why it was benign or malicious
- Whether escalation was required
- Final classification

---

## Example Closure Note

```text
Investigation completed. Alert activity was reviewed using Microsoft Sentinel SecurityEvent logs. Related authentication, execution, privilege and persistence events were checked. Activity matched known lab/authorized behavior. No evidence of compromise was identified. Ticket closed as benign.
```

---

## Analyst Checklist

- [ ] Alert reviewed
- [ ] Host identified
- [ ] Account identified
- [ ] Event ID understood
- [ ] Related events checked
- [ ] Severity assigned
- [ ] Escalation decision documented
- [ ] Closure note written
