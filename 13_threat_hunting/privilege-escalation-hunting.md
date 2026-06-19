# Privilege Escalation Hunting

## Status

**Status:** Completed  
**Data Source:** `SecurityEvent`  
**Primary Event ID:** 4672  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Objective

Hunt for privileged logon activity that may indicate elevated access, administrative usage or possible privilege escalation.

---

## Event ID

| Event ID | Description |
|---:|---|
| 4672 | Special privileges assigned to new logon |

---

## Hunt Query

```kql
SecurityEvent
| where EventID == 4672
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Frequency Query

```kql
SecurityEvent
| where EventID == 4672
| summarize PrivilegedLogons=count() by Account
| sort by PrivilegedLogons desc
```

---

## Hunt Questions

- Which accounts received special privileges?
- Was the activity from SYSTEM, Administrator or a normal user?
- Is the privileged logon expected?
- Did privileged logon occur before suspicious execution or persistence?

---

## Lab Findings

Privileged logon events were observed for expected accounts such as:

- `NT AUTHORITY\\SYSTEM`
- Lab user / Microsoft account activity

No unexpected privileged account activity was identified.

---

## Investigation Notes

Review more deeply when privileged logons involve:

- Unknown administrator accounts
- Recently created users
- Service accounts used interactively
- Privileged logons followed by PowerShell execution
- Privileged logons followed by service or scheduled task creation
- Odd time activity

---

## Conclusion

Privilege escalation hunting confirmed visibility into Event ID 4672. Observed activity matched expected lab and system behavior.
