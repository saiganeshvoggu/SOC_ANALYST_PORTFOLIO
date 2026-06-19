# PowerShell Hunting

## Status

**Status:** Completed  
**Data Source:** `SecurityEvent`  
**Primary Event ID:** 4688  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Objective

Hunt for PowerShell execution activity and identify which accounts and parent processes launched PowerShell.

PowerShell is a legitimate administration tool but is also commonly used by attackers for execution, discovery, credential access and defense evasion.

---

## Event IDs

| Event ID | Description |
|---:|---|
| 4688 | A new process has been created |
| 4103 | PowerShell module logging |
| 4104 | PowerShell script block logging |

---

## Hunt Query

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName
| sort by TimeGenerated desc
```

---

## Hunt Questions

- Who executed PowerShell?
- Which parent process launched PowerShell?
- Was PowerShell launched by a user, service, agent or suspicious process?
- Was encoded PowerShell used?

---

## Lab Findings

PowerShell activity was observed from:

- Lab user account
- Splunk service activity
- Azure Connected Machine Agent activity

Observed activity was expected in the lab environment.

---

## Suspicious Parent Processes To Review

PowerShell execution may require deeper investigation when launched from:

- `winword.exe`
- `excel.exe`
- `outlook.exe`
- `chrome.exe`
- `msedge.exe`
- `wscript.exe`
- `cscript.exe`
- `rundll32.exe`
- `regsvr32.exe`

---

## Encoded PowerShell Query

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| where CommandLine has_any ("EncodedCommand", "-enc", "-e")
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

---

## MITRE ATT&CK Mapping

| Tactic | Technique | Technique ID |
|---|---|---|
| Execution | PowerShell | T1059.001 |

---

## Conclusion

PowerShell process execution was visible through Event ID 4688. No malicious PowerShell parent-child relationship was identified during the hunt. Activity was consistent with administrative and lab-generated behavior.
