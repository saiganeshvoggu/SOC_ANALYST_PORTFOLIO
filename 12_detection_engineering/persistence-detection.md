# Persistence Detection Lab

## Status

**Status:** Completed  
**Category:** Persistence  
**Platform:** Windows Event Viewer and Microsoft Sentinel / Azure Log Analytics

---

## Objective

Detect common Windows persistence techniques using service installation and scheduled task creation events.

Attackers often use services and scheduled tasks to maintain access after initial compromise.

---

## Persistence Events Covered

| Event ID | Description | Log Source | Status |
|---:|---|---|---|
| 4697 | A service was installed in the system | Security | Verified in Sentinel |
| 4698 | A scheduled task was created | Security | Verified locally; Sentinel collection may vary |
| 7045 | A service was installed in the system | System | Verified locally |

---

## MITRE ATT&CK Mapping

| Detection | Tactic | Technique |
|---|---|---|
| Service installation | Persistence / Privilege Escalation | T1543.003 Windows Service |
| Scheduled task creation | Persistence / Execution | T1053.005 Scheduled Task |

---

## 4697 - Service Installation Detection

### Audit Policy

```cmd
auditpol /set /subcategory:"Security System Extension" /success:enable /failure:enable
```

### Test Command

```cmd
sc create AdminLabService binPath= "C:\Windows\System32\cmd.exe"
```

### Detection Query

```kql
SecurityEvent
| where EventID == 4697
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Cleanup

```cmd
sc delete AdminLabService
```

---

## 4698 - Scheduled Task Creation Detection

### Audit Policy

```cmd
auditpol /set /subcategory:"Other Object Access Events" /success:enable /failure:enable
```

### Test Command

```cmd
schtasks /create /tn "AdminLabTask" /tr "cmd.exe" /sc once /st 23:59
```

### Detection Query

```kql
SecurityEvent
| where EventID == 4698
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

### Cleanup

```cmd
schtasks /delete /tn "AdminLabTask" /f
```

---

## 7045 - Service Control Manager Detection

### Test Command

```cmd
sc create Lab7045Service binPath= "C:\Windows\System32\cmd.exe"
```

### Local Event Viewer Path

```text
Event Viewer
Windows Logs
System
```

### KQL Query

```kql
Event
| where EventID == 7045
| project TimeGenerated, Computer, EventID, RenderedDescription
| sort by TimeGenerated desc
```

### Lab Finding

Event ID 7045 was confirmed locally in the Windows System log. The Azure `Event` table was empty in this lab environment, indicating System log collection was not enabled in the current Data Collection Rule.

---

## Combined Persistence Hunting Query

```kql
SecurityEvent
| where EventID in (4697, 4698)
| project TimeGenerated, Account, Computer, EventID, Activity
| sort by TimeGenerated desc
```

---

## Detection Logic

Trigger when:

- A new service is installed
- A scheduled task is created
- Activity occurs from a non-standard user
- Service or task names appear suspicious
- Binary path points to user-writable directories such as:
  - `C:\Users\Public\`
  - `C:\Temp\`
  - `AppData\Roaming\`
  - `Downloads\`

---

## SOC Analyst Investigation Notes

Review:

- Account that created the service or task
- Service name or task name
- Executable path
- Parent process
- Timestamp
- Related process creation events
- Recent logons from the same account
- Whether activity matches approved admin work

---

## False Positive Considerations

Benign causes:

- Software installation
- Patch management
- IT administration
- Endpoint monitoring tools
- Backup agents
- Security agents

---

## Lab Outcome

Persistence-related activity was successfully generated and detected through Windows event telemetry. Service installation was confirmed through Event ID 4697 in Sentinel and Event ID 7045 locally in the System log. Scheduled task creation was confirmed locally through Event ID 4698.
