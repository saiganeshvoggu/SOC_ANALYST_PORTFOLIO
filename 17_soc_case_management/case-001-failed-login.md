# SOC-2026-001 - Multiple Failed Login Attempts

## Case Status

**Status:** Closed  
**Severity:** Low  
**Classification:** Benign lab-generated activity  
**Escalation:** Not required

---

## Ticket Details

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-001 |
| Alert Name | Multiple Failed Login Attempts |
| Alert Source | Microsoft Sentinel |
| Event ID | 4625 |
| Host | SaiGaneshVoggu |
| Primary Account | Administrator / test / unresolved account |

---

## Initial Triage

Multiple failed authentication events were observed. The alert was reviewed to determine whether the activity represented brute-force behavior, password guessing or expected lab activity.

---

## Evidence Reviewed

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count() by Account
| sort by FailedAttempts desc
```

Observed failed login counts:

| Account | Failed Attempts |
|---|---:|
| `-\\-` | 17 |
| `SAIGANESHVOGGU\\test` | 2 |
| `SAIGANESHVOGGU\\Administrator` | 2 |

---

## Investigation Notes

- Failed login activity was low-volume.
- No confirmed brute-force pattern was observed.
- No unauthorized successful login was identified.
- Activity matched controlled lab testing.

---

## Severity Decision

**Low**

Reason: Low-volume failed authentication activity with no evidence of account compromise.

---

## Closure Notes

Investigation completed. Failed authentication events were reviewed and determined to be benign lab-generated activity. No compromise, persistence or privilege escalation was identified. Ticket closed.
