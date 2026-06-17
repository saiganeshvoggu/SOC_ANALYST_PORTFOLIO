# Security Log Cleared Incident Investigation

## Status

**Status:** Completed  
**Event ID:** 1102  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Alert Summary

Security audit log clearing activity was detected.

| Field | Value |
|---|---|
| Event ID | 1102 |
| Activity | The audit log was cleared |
| Host | SaiGaneshVoggu |

---

## KQL Query

```kql
SecurityEvent
| where EventID == 1102
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Findings

Event ID 1102 was observed:

```text
1102 - The audit log was cleared.
```

The event was generated during controlled lab testing.

---

## Analysis

In production, Event ID 1102 should be treated as high severity because attackers may clear Windows Security logs to remove evidence.

A full investigation should review activity before and after the log clear event, including:

- Failed logons
- Successful logons
- Privileged logons
- PowerShell execution
- Service installation
- Scheduled task creation
- User creation
- Group membership changes

---

## Severity

**Severity:** Low in lab / High in production

---

## Classification

**Classification:** Authorized lab-generated defense evasion simulation

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|---|---|
| Defense Evasion | T1070.001 Clear Windows Event Logs |

---

## Closure Notes

Security log clearing was detected and reviewed. The event was expected lab activity. Incident closed as benign.
