# Detection Engineering Phase

## Status

**Phase Status:** Completed  
**Platform:** Microsoft Sentinel / Azure Log Analytics  
**Endpoint:** Windows 11 endpoint onboarded through Azure Arc  
**Data Source:** Windows Security Events via Azure Monitor Agent and local Windows Event Viewer validation

---

## Objective

This phase documents practical detection engineering labs focused on Windows endpoint telemetry, authentication events, account management, privilege activity, PowerShell execution, persistence, and log tampering.

The goal of this phase was to move from basic log viewing into detection logic development using KQL and Windows Event IDs.

---

## Skills Practiced

- Windows Event ID investigation
- Microsoft Sentinel / Log Analytics querying
- KQL detection logic
- Threshold-based detection
- Correlation-based detection
- Audit policy validation and configuration
- Persistence detection
- Privilege escalation detection
- PowerShell execution monitoring
- MITRE ATT&CK mapping
- False positive review
- SOC analyst investigation notes

---

## Completed Labs

| Lab | Detection Area | Event IDs | Status |
|---|---|---:|---|
| 1 | Failed login detection | 4625 | Completed |
| 2 | Successful logon visibility | 4624 | Completed |
| 3 | Brute-force success correlation | 4625 + 4624 | Completed |
| 4 | User account creation | 4720 | Completed |
| 5 | Local group membership change | 4732 | Completed |
| 6 | Privileged logon detection | 4672 | Completed |
| 7 | Process creation auditing | 4688 | Completed |
| 8 | PowerShell operational logging | 4103 / 4104 | Completed |
| 9 | Encoded PowerShell execution | 4688 / PowerShell | Completed |
| 10 | Service installation detection | 4697 | Completed |
| 11 | Scheduled task creation detection | 4698 | Completed |
| 12 | Security log cleared detection | 1102 | Completed |
| 13 | Service Control Manager service creation | 7045 | Completed locally |

---

## Detection Coverage

### Authentication

- Failed logons
- Successful logons
- Brute-force style activity
- Successful login after repeated failed attempts

### Account and Privilege Activity

- New user account creation
- Group membership changes
- Privileged logons

### Execution

- Process creation
- PowerShell execution
- Encoded PowerShell execution

### Persistence

- Service installation
- Scheduled task creation
- Service Control Manager events

### Defense Evasion

- Security log clearing

---

## Key KQL Concepts Used

- `where`
- `project`
- `sort by`
- `summarize`
- `count()`
- `countif()`
- `maxif()`
- `bin()`
- Event correlation using multiple Event IDs

---

## MITRE ATT&CK Mapping

| Detection | ATT&CK Tactic | Technique |
|---|---|---|
| Failed logins | Credential Access | T1110 Brute Force |
| Successful login after failures | Credential Access / Initial Access | T1110 / T1078 |
| User account creation | Persistence | T1136 Create Account |
| Admin group membership change | Persistence / Privilege Escalation | T1098 Account Manipulation |
| PowerShell execution | Execution | T1059.001 PowerShell |
| Encoded PowerShell | Execution / Defense Evasion | T1059.001 |
| Service installation | Persistence / Privilege Escalation | T1543.003 Windows Service |
| Scheduled task creation | Persistence / Execution | T1053.005 Scheduled Task |
| Security log cleared | Defense Evasion | T1070.001 Clear Windows Event Logs |

---

## Outcome

This phase confirms hands-on ability to generate security events, verify them in Windows Event Viewer, ingest them into Microsoft Sentinel, and build practical KQL detection logic suitable for SOC analyst interviews and portfolio demonstration.
