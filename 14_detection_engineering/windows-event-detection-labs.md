# Windows Event Detection Labs

## Objective

This document summarizes the Windows Event IDs tested during the Detection Engineering phase.

Each event was validated through hands-on activity using Windows Event Viewer and Microsoft Sentinel / Azure Log Analytics where supported by the current collection configuration.

---

## Lab Environment

- Windows 11 endpoint
- Azure Arc-enabled machine
- Azure Monitor Agent
- Data Collection Rule
- Microsoft Sentinel
- Azure Log Analytics Workspace
- Windows Event Viewer
- Admin CMD / PowerShell

---

## Event ID Summary

| Event ID | Description | Log Source | Lab Result |
|---:|---|---|---|
| 4624 | Successful logon | Security | Verified |
| 4625 | Failed logon | Security | Verified |
| 4672 | Special privileges assigned to new logon | Security | Verified |
| 4688 | Process creation | Security | Verified after audit policy enablement |
| 4697 | Service installed | Security | Verified |
| 4698 | Scheduled task created | Security | Verified locally; Azure collection may vary |
| 4720 | User account created | Security | Verified |
| 4732 | Member added to local group | Security | Verified |
| 1102 | Audit log cleared | Security | Verified |
| 4103 | PowerShell module logging | PowerShell Operational | Verified locally |
| 4104 | PowerShell script block logging | PowerShell Operational | Verified locally |
| 7045 | Service installed | System | Verified locally |

---

## 4624 - Successful Logon

### Purpose

Used to identify successful authentication events.

### Query

```kql
SecurityEvent
| where EventID == 4624
| sort by TimeGenerated desc
```

### Analyst Use

- Confirm successful authentication
- Review logon type
- Correlate with failed login attempts
- Identify suspicious successful access after failures

---

## 4625 - Failed Logon

### Purpose

Used to identify failed authentication attempts.

### Query

```kql
SecurityEvent
| where EventID == 4625
| sort by TimeGenerated desc
```

### Analyst Use

- Detect brute-force attempts
- Detect password spraying
- Identify repeated failed attempts

---

## 4672 - Privileged Logon

### Purpose

Detects logons where special privileges were assigned.

### Query

```kql
SecurityEvent
| where EventID == 4672
| project TimeGenerated, Account, Computer
| sort by TimeGenerated desc
```

### Analyst Use

- Review privileged account activity
- Monitor admin-level access
- Identify abnormal privileged logons

---

## 4688 - Process Creation

### Purpose

Provides process creation visibility.

### Audit Policy Used

```cmd
auditpol /set /subcategory:"Process Creation" /success:enable /failure:enable
```

### Query

```kql
SecurityEvent
| where EventID == 4688
| project TimeGenerated, Account, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

### Analyst Use

- Process hunting
- Parent-child process analysis
- PowerShell and CMD execution detection

---

## 4697 - Service Installed

### Purpose

Detects service installation through Security logs.

### Audit Policy Used

```cmd
auditpol /set /subcategory:"Security System Extension" /success:enable /failure:enable
```

### Test Command

```cmd
sc create AdminLabService binPath= "C:\Windows\System32\cmd.exe"
```

### Query

```kql
SecurityEvent
| where EventID == 4697
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Analyst Use

- Service-based persistence detection
- Unauthorized service installation review

---

## 4698 - Scheduled Task Created

### Purpose

Detects scheduled task creation.

### Audit Policy Used

```cmd
auditpol /set /subcategory:"Other Object Access Events" /success:enable /failure:enable
```

### Test Command

```cmd
schtasks /create /tn "AdminLabTask" /tr "cmd.exe" /sc once /st 23:59
```

### Query

```kql
SecurityEvent
| where EventID == 4698
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Analyst Use

- Scheduled task persistence detection
- Suspicious automation review

---

## 4720 - User Account Created

### Purpose

Detects new user account creation.

### Test Command

```cmd
net user soclabuser Test@12345 /add
```

### Query

```kql
SecurityEvent
| where EventID == 4720
| project TimeGenerated, Computer, Account, TargetAccount, Activity
| sort by TimeGenerated desc
```

### Analyst Use

- Unauthorized account creation detection
- Persistence investigation

---

## 4732 - Local Group Membership Change

### Purpose

Detects users being added to local security groups.

### Test Command

```cmd
net localgroup Administrators adminlab /add
```

### Query

```kql
SecurityEvent
| where EventID == 4732
| project TimeGenerated, Account, TargetAccount, Activity
| sort by TimeGenerated desc
```

### Analyst Use

- Local admin membership monitoring
- Privilege escalation review

---

## 1102 - Security Log Cleared

### Purpose

Detects security audit log clearing.

### Test Command

```cmd
wevtutil cl Security
```

### Query

```kql
SecurityEvent
| where EventID == 1102
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Analyst Use

- Log tampering detection
- Defense evasion investigation

---

## 4103 / 4104 - PowerShell Operational Logging

### Purpose

Detects PowerShell command and script activity through PowerShell Operational logs.

### Local Path

```text
Event Viewer
Applications and Services Logs
Microsoft
Windows
PowerShell
Operational
```

### Analyst Use

- PowerShell activity review
- Script execution monitoring
- Suspicious command investigation

---

## 7045 - Service Control Manager Service Install

### Purpose

Detects service installation through the System log.

### Local Path

```text
Event Viewer
Windows Logs
System
```

### Query Attempt

```kql
Event
| where EventID == 7045
| project TimeGenerated, Computer, EventID, RenderedDescription
| sort by TimeGenerated desc
```

### Lab Note

The event was confirmed locally in Windows Event Viewer. The Azure `Event` table was empty, indicating System log collection was not enabled in the current Data Collection Rule.

---

## Key Learning

Detection engineering requires both event knowledge and telemetry validation. A detection is only useful when the required logs are enabled, collected, and searchable in the SIEM.
