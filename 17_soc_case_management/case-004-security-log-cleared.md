# SOC-2026-004 - Security Log Cleared

## Case Status

**Status:** Closed  
**Severity:** Low in lab / High in production  
**Classification:** Authorized lab-generated activity  
**Escalation:** Not required for lab activity

---

## Ticket Details

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-004 |
| Alert Name | Windows Security Log Cleared |
| Alert Source | Microsoft Sentinel |
| Event ID | 1102 |
| Host | SaiGaneshVoggu |

---

## Initial Triage

A Windows Security audit log clearing event was detected. This event should be treated seriously in production because it may indicate an attempt to remove investigation evidence.

---

## Evidence Reviewed

```kql
SecurityEvent
| where EventID == 1102
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Investigation Notes

- Event ID 1102 was observed.
- Related authentication, execution and service/task activity should be reviewed around the same timestamp.
- In this lab, the activity was generated intentionally for testing.

---

## Severity Decision

**Low** for lab activity.  
**High** in production unless confirmed as authorized maintenance.

---

## Closure Notes

Investigation completed. Security log clearing activity was confirmed as controlled lab testing. No unauthorized activity was identified. Ticket closed.
