# Encoded PowerShell Detection Lab

## Status

**Status:** Completed  
**Category:** Execution / Defense Evasion  
**Primary Data Sources:** Windows Security Event 4688, PowerShell Operational Logs 4103 and 4104  
**Platform:** Windows Event Viewer and Microsoft Sentinel / Azure Log Analytics

---

## Objective

Detect PowerShell execution and encoded PowerShell usage, a common attacker technique used to obscure command content and execute scripts from the command line.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | Technique ID |
|---|---|---|
| Execution | PowerShell | T1059.001 |
| Defense Evasion | Obfuscated/Compressed Files and Information | T1027 |

---

## Lab Commands

### Generate a Safe Encoded PowerShell Command

```powershell
$command = "Get-Date"
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encoded = [Convert]::ToBase64String($bytes)
powershell.exe -EncodedCommand $encoded
```

### Example Encoded Command

```powershell
powershell.exe -EncodedCommand RwBlAHQALQBEAGEAdABlAA==
```

This decodes to:

```powershell
Get-Date
```

---

## Local Verification

PowerShell execution was verified locally through:

```text
Event Viewer
Applications and Services Logs
Microsoft
Windows
PowerShell
Operational
```

Relevant events:

| Event ID | Description |
|---:|---|
| 4103 | PowerShell module logging |
| 4104 | PowerShell script block logging |

---

## Sentinel / KQL Detection

### PowerShell Process Execution

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

---

## Encoded PowerShell Detection Query

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| where CommandLine has_any ("EncodedCommand", "-enc", "-e")
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName, CommandLine
| sort by TimeGenerated desc
```

---

## Fallback Query

In this lab, process creation telemetry was collected, but command-line arguments were limited in the available Sentinel results. When command-line data is unavailable, use process execution visibility as a fallback:

```kql
SecurityEvent
| where EventID == 4688
| where NewProcessName contains "powershell"
| project TimeGenerated, Account, Computer, NewProcessName, ParentProcessName
| sort by TimeGenerated desc
```

---

## Detection Logic

Trigger when:

- Event ID equals `4688`
- New process name contains `powershell`
- Command line contains encoded execution switches such as:
  - `EncodedCommand`
  - `-enc`
  - `-e`

---

## Analyst Investigation Notes

When encoded PowerShell is detected, review:

- User account
- Parent process
- Command line arguments
- Encoded payload, if available
- Whether PowerShell was launched by Office, browser, script host, Splunk, or another service
- Endpoint timeline
- Related network activity

---

## False Positive Considerations

Potential benign causes:

- Administrative scripts
- Endpoint management tools
- Software deployment tools
- Monitoring tools
- Security tooling

---

## Lab Outcome

Encoded PowerShell execution was generated successfully using a safe `Get-Date` command. PowerShell process execution was observed through Event ID 4688, and PowerShell Operational Logs were available locally through Event IDs 4103 and 4104.

This lab demonstrates practical understanding of PowerShell execution monitoring and detection limitations when command-line telemetry is not fully collected.
