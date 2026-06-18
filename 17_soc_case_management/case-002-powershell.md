# SOC-2026-002 - PowerShell Execution Review

## Case Status

**Status:** Closed  
**Severity:** Low  
**Classification:** Legitimate administrative / lab activity  
**Escalation:** Not required

---

## Ticket Details

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-002 |
| Alert Name | PowerShell Execution Review |
| Alert Source | Microsoft Sentinel |
| Event ID | 4688 |
| Host | SaiGaneshVoggu |

---

## Initial Triage

PowerShell execution was detected. The investigation focused on identifying the account, host, parent process and whether the activity was expected.

---

## Evidence Reviewed

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName
| sort by TimeGenerated desc
```

---

## Investigation Notes

- PowerShell process execution was observed.
- Parent processes included expected lab/security tooling such as Splunk and Azure Connected Machine Agent activity.
- No unusual parent-child process pattern was identified.
- No evidence of persistence, privilege abuse or compromise was observed.

---

## Severity Decision

**Low**

Reason: PowerShell activity was expected and associated with known lab/security tooling behavior.

---

## Closure Notes

Investigation completed. PowerShell execution was reviewed and determined to be legitimate administrative/lab activity. No unauthorized behavior was identified. Ticket closed.
