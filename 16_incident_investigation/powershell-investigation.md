# PowerShell Incident Investigation

## Status

**Status:** Completed  
**Primary Event ID:** 4688  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Alert Summary

PowerShell process execution was observed on the endpoint.

PowerShell is a legitimate administration tool, but it is also commonly reviewed by SOC analysts because attackers may use it for execution, discovery and defense evasion.

---

## KQL Query

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName
| sort by TimeGenerated desc
```

---

## Findings

PowerShell execution was observed from expected lab and security tooling context.

Observed parent process examples included:

- `splunkd.exe`
- Azure Connected Machine Agent activity

---

## Analysis

PowerShell launched by Splunk or Azure monitoring components can be expected in a lab or monitoring environment.

Suspicious parent processes to review in production include:

- Microsoft Office applications
- Browsers
- Windows Script Host processes
- DLL execution utilities

No suspicious parent-child process relationship was identified in the lab evidence.

---

## Encoded PowerShell Context

A safe encoded PowerShell test was performed during the lab to validate process visibility. The lab confirmed that PowerShell process execution was visible, while command-line argument visibility was limited in the current telemetry configuration.

---

## Severity

**Severity:** Informational

---

## Classification

**Classification:** Legitimate administrative / lab activity

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|---|---|
| Execution | T1059.001 PowerShell |

---

## Closure Notes

PowerShell execution was detected and reviewed. Parent processes matched expected lab/security tooling behavior. No malicious PowerShell activity was identified. Incident closed as benign.
