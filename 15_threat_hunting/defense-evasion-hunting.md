# Defense Evasion Hunting

## Status

**Status:** Completed  
**Data Source:** `SecurityEvent`  
**Primary Event ID:** 1102  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Objective

Hunt for defense evasion activity where an attacker may attempt to remove evidence by clearing Windows Security logs.

---

## Event ID

| Event ID | Description |
|---:|---|
| 1102 | The audit log was cleared |

---

## Hunt Query

```kql
SecurityEvent
| where EventID == 1102
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Hunt Questions

- Was the Security audit log cleared?
- Which account cleared the log?
- Which host was affected?
- What happened before the log was cleared?
- Were there recent failed logins, privileged logons, PowerShell executions or persistence events?

---

## Lab Finding

Security log clearing activity was detected:

```text
1102 - The audit log was cleared.
```

This was generated as part of controlled lab testing.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | Technique ID |
|---|---|---|
| Defense Evasion | Clear Windows Event Logs | T1070.001 |

---

## Analyst Notes

Event ID 1102 should generally be treated as high severity because attackers may clear logs after compromise to hide activity.

Review related events before and after log clearing:

- Failed logons
- Successful logons
- Privileged logons
- PowerShell execution
- New services
- Scheduled tasks
- User creation
- Group membership changes

---

## Conclusion

Defense evasion hunting successfully identified Security log clearing activity through Event ID 1102 in Microsoft Sentinel.
