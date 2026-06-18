# SOC-2026-006 - User Added To Privileged Group

## Case Status

**Status:** Closed  
**Severity:** Low in lab / High if unexpected in production  
**Classification:** Authorized lab-generated activity  
**Escalation:** Not required

---

## Ticket Details

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-006 |
| Alert Name | User Added To Privileged Group |
| Alert Source | Microsoft Sentinel |
| Event ID | 4732 |
| Host | SaiGaneshVoggu |

---

## Initial Triage

A local group membership change was detected. The investigation focused on identifying the user added, the target group, who performed the action and whether the action was authorized.

---

## Evidence Reviewed

```kql
SecurityEvent
| where EventID == 4732
| project TimeGenerated, Account, Computer, TargetAccount, Activity
| sort by TimeGenerated desc
```

---

## Investigation Notes

- Event ID 4732 indicates a member was added to a security-enabled local group.
- Adding a user to the Administrators group can indicate privilege escalation if unauthorized.
- In this lab, the activity was authorized and generated for testing.

---

## Related Checks

When Event ID 4732 is observed, review:

- 4720 - Was the account newly created?
- 4624 - Did the account log in?
- 4672 - Did the account receive elevated privileges?
- 4688 - Did the account execute commands?

---

## Severity Decision

**Low** for lab activity.  
**High** if a user is unexpectedly added to Administrators or another privileged group.

---

## Closure Notes

Investigation completed. Group membership change was confirmed as authorized lab-generated activity. No unauthorized privilege escalation was identified. Ticket closed.
