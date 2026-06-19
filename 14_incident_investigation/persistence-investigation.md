# Persistence Incident Investigation

## Status

**Status:** Completed  
**Event IDs:** 4697 and 4698  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Alert Summary

Persistence-related activity was observed through service installation and scheduled task creation events.

---

## KQL Query

```kql
SecurityEvent
| where EventID in (4697, 4698)
| project TimeGenerated, Account, Computer, EventID, Activity
| sort by TimeGenerated desc
```

---

## Findings

Observed events included:

| Event ID | Description |
|---:|---|
| 4697 | A service was installed in the system |
| 4698 | A scheduled task was created |

The events were observed on host `SaiGaneshVoggu` and were consistent with controlled lab testing.

---

## Analysis

Service installation and scheduled task creation are common persistence techniques. In this lab, the activity was intentionally generated and later reviewed as part of SOC investigation practice.

A production investigation should review:

- Account that created the service or task
- Timestamp
- Service or task name
- Executable or command path
- Parent process
- Whether activity occurred during expected admin work
- Related PowerShell or CMD activity

---

## Severity

**Severity:** Informational in lab / High if unexpected in production

---

## Classification

**Classification:** Authorized lab-generated persistence simulation

---

## MITRE ATT&CK Mapping

| Activity | Technique |
|---|---|
| Service installation | T1543.003 Windows Service |
| Scheduled task creation | T1053.005 Scheduled Task |

---

## Closure Notes

Persistence events were reviewed and matched known lab activity. No unauthorized persistence was identified. Incident closed as benign.
