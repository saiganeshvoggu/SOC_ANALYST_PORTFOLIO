# SOC-2026-005 - New User Account Created

## Case Status

**Status:** Closed  
**Severity:** Low in lab / High if unexpected in production  
**Classification:** Authorized lab-generated activity  
**Escalation:** Not required

---

## Ticket Details

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-005 |
| Alert Name | New User Account Created |
| Alert Source | Microsoft Sentinel |
| Event ID | 4720 |
| Host | SaiGaneshVoggu |

---

## Initial Triage

A new user account creation event was detected. The investigation reviewed who created the account, when it was created, and whether it was followed by group membership changes or successful logon activity.

---

## Evidence Reviewed

```kql
SecurityEvent
| where EventID == 4720
| project TimeGenerated, Account, Computer, TargetAccount, Activity
| sort by TimeGenerated desc
```

---

## Investigation Notes

- Event ID 4720 indicates a user account was created.
- Account creation was performed as part of controlled lab testing.
- No unauthorized account activity was identified.

---

## Related Checks

The following events should be reviewed when Event ID 4720 is observed:

- 4732 - Member added to local group
- 4624 - Successful logon
- 4672 - Special privileges assigned
- 4688 - Process creation

---

## Severity Decision

**Low** for lab activity.  
**High** if a new account is unexpected, privileged or followed by suspicious activity.

---

## Closure Notes

Investigation completed. User creation activity was confirmed as authorized lab activity. No unauthorized account persistence was identified. Ticket closed.
