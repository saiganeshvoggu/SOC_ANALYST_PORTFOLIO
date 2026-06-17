# Security Log Cleared Detection Lab

## Status

**Status:** Completed  
**Category:** Defense Evasion / Log Tampering  
**Platform:** Windows Event Viewer and Microsoft Sentinel / Azure Log Analytics  
**Primary Event ID:** 1102

---

## Objective

Detect clearing of the Windows Security audit log.

Attackers may clear logs after compromise to remove evidence of failed logins, successful logons, privilege escalation, persistence, or command execution.

---

## Event Details

| Field | Value |
|---|---|
| Event ID | 1102 |
| Description | The audit log was cleared |
| Log Source | Security |
| Severity Recommendation | High |

---

## MITRE ATT&CK Mapping

| Tactic | Technique | Technique ID |
|---|---|---|
| Defense Evasion | Clear Windows Event Logs | T1070.001 |

---

## Test Command

Run from Administrator CMD:

```cmd
wevtutil cl Security
```

---

## Event Viewer Validation

Path:

```text
Event Viewer
Windows Logs
Security
```

Filter:

```text
1102
```

Expected event:

```text
1102 - The audit log was cleared.
```

---

## Sentinel KQL Detection

```kql
SecurityEvent
| where EventID == 1102
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Detection Logic

Trigger when:

- Event ID equals `1102`
- Windows Security audit log is cleared

This should be treated as high severity because it may indicate an attacker attempting to remove forensic evidence.

---

## Analyst Investigation Notes

When Event ID 1102 appears, review:

- Account that cleared the log
- Computer where the log was cleared
- Time of log clear
- Activity before the log clear event
- Recent failed logons
- Recent privileged logons
- Recent service or scheduled task creation
- Recent PowerShell activity

---

## False Positive Considerations

Possible benign causes:

- Administrator maintenance
- Lab activity
- Troubleshooting
- Log rotation or manual cleanup

Even if benign, log clearing should be documented and reviewed.

---

## Lab Outcome

Event ID 1102 was generated locally using `wevtutil cl Security`, verified in Windows Event Viewer, and successfully detected in Microsoft Sentinel / Azure Log Analytics using KQL.
