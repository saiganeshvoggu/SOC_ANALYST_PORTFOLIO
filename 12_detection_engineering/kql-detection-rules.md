# KQL Detection Rules Library

## Purpose

This document contains KQL detection queries created and validated during the Detection Engineering phase.

Data source used primarily:

```kql
SecurityEvent
```

---

## 1. Failed Login Detection

### Event ID

- 4625 - An account failed to log on

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count()
    by Account, Computer, bin(TimeGenerated, 5m)
| where FailedAttempts >= 5
| sort by TimeGenerated desc
```

### Detection Logic

Detects five or more failed login attempts within a five-minute window.

### MITRE ATT&CK

- T1110 - Brute Force

---

## 2. Successful Login After Failed Logins

### Event IDs

- 4625 - Failed login
- 4624 - Successful login

```kql
SecurityEvent
| where EventID in (4624, 4625)
| summarize
    FailedCount=countif(EventID == 4625),
    SuccessCount=countif(EventID == 4624),
    LastSuccess=maxif(TimeGenerated, EventID == 4624)
by Computer
| where FailedCount >= 5 and SuccessCount >= 1
| project Computer, FailedCount, SuccessCount, LastSuccess
| sort by LastSuccess desc
```

### Detection Logic

Detects systems with multiple failed login attempts followed by successful authentication activity.

### MITRE ATT&CK

- T1110 - Brute Force
- T1078 - Valid Accounts

---

## 3. New User Account Creation

### Event ID

- 4720 - A user account was created

```kql
SecurityEvent
| where EventID == 4720
| project TimeGenerated, Computer, Account, TargetAccount, Activity
| sort by TimeGenerated desc
```

### Detection Logic

Detects local account creation, which may indicate persistence.

### MITRE ATT&CK

- T1136.001 - Create Account: Local Account

---

## 4. Local Group Membership Change

### Event ID

- 4732 - A member was added to a security-enabled local group

```kql
SecurityEvent
| where EventID == 4732
| project TimeGenerated, Account, TargetAccount, Activity
| sort by TimeGenerated desc
```

### High-Value Filter

```kql
SecurityEvent
| where EventID == 4732
| where TargetAccount has "Administrators"
| project TimeGenerated, Account, TargetAccount, Activity
| sort by TimeGenerated desc
```

### Detection Logic

Detects users being added to local groups, especially Administrators.

### MITRE ATT&CK

- T1098 - Account Manipulation

---

## 5. Privileged Logon Detection

### Event ID

- 4672 - Special privileges assigned to new logon

```kql
SecurityEvent
| where EventID == 4672
| project TimeGenerated, Account, Computer
| sort by TimeGenerated desc
```

### Frequency View

```kql
SecurityEvent
| where EventID == 4672
| summarize Count=count() by Account
| sort by Count desc
```

### Detection Logic

Identifies accounts receiving elevated privileges during logon.

---

## 6. Process Creation Detection

### Event ID

- 4688 - A new process has been created

```kql
SecurityEvent
| where EventID == 4688
| project TimeGenerated, Account, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

### Detection Logic

Provides process execution visibility for endpoint investigation.

---

## 7. PowerShell Execution Detection

### Event IDs

- 4688 - Process creation
- 4103 - PowerShell module logging
- 4104 - PowerShell script block logging

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

### Detection Logic

Detects PowerShell process execution.

### MITRE ATT&CK

- T1059.001 - PowerShell

---

## 8. Encoded PowerShell Detection

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| where CommandLine has_any ("EncodedCommand", "-enc", "-e")
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

### Fallback Query When CommandLine Is Not Collected

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName
| sort by TimeGenerated desc
```

### Detection Logic

Detects encoded PowerShell usage when command-line arguments are available. In the lab, process execution was visible, but command-line arguments were limited.

### MITRE ATT&CK

- T1059.001 - PowerShell

---

## 9. Service Installation Detection

### Event ID

- 4697 - A service was installed in the system

```kql
SecurityEvent
| where EventID == 4697
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Detection Logic

Detects service creation through Security logs.

### MITRE ATT&CK

- T1543.003 - Windows Service

---

## 10. Scheduled Task Creation Detection

### Event ID

- 4698 - A scheduled task was created

```kql
SecurityEvent
| where EventID == 4698
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Detection Logic

Detects scheduled task creation, a common persistence method.

### MITRE ATT&CK

- T1053.005 - Scheduled Task

---

## 11. Security Log Cleared Detection

### Event ID

- 1102 - The audit log was cleared

```kql
SecurityEvent
| where EventID == 1102
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Detection Logic

Detects possible log tampering or attacker evidence removal.

### MITRE ATT&CK

- T1070.001 - Clear Windows Event Logs

---

## 12. Service Control Manager Service Creation

### Event ID

- 7045 - A service was installed in the system

```kql
Event
| where EventID == 7045
| project TimeGenerated, Computer, EventID, RenderedDescription
| sort by TimeGenerated desc
```

### Lab Note

Event ID 7045 was verified locally in Windows Event Viewer under the System log. The Azure `Event` table was empty in this lab environment, indicating System log collection was not enabled in the current DCR.

---

## Analyst Notes

Detection quality depends on:

- Audit policy configuration
- Data Collection Rule configuration
- Command-line argument visibility
- Event source coverage
- Baseline activity
- False positive review

