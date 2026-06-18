# SOC-2026-003 - Service and Scheduled Task Activity Review

## Case Status

**Status:** Closed  
**Severity:** Low in lab / High if unexpected in production  
**Classification:** Authorized lab-generated activity  
**Escalation:** Not required

---

## Ticket Details

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-003 |
| Alert Name | Service and Scheduled Task Activity Review |
| Alert Source | Microsoft Sentinel |
| Event IDs | 4697, 4698 |
| Host | SaiGaneshVoggu |

---

## Initial Triage

Service installation and scheduled task creation events were observed. These events require review when they are unexpected.

---

## Evidence Reviewed

```kql
SecurityEvent
| where EventID in (4697, 4698)
| project TimeGenerated, Account, Computer, EventID, Activity
| sort by TimeGenerated desc
```

---

## Investigation Notes

- Event ID 4697 indicated that a service was installed.
- Event ID 4698 indicated that a scheduled task was created.
- Activity was performed as part of controlled lab testing.
- No unauthorized service or scheduled task activity was identified.

---

## Severity Decision

**Low** for lab activity.

In production, unexpected service installation or scheduled task creation should usually be reviewed as Medium or High depending on account, host, binary path and related activity.

---

## Closure Notes

Investigation completed. Service and scheduled task events were reviewed and confirmed as authorized lab-generated activity. Ticket closed.
