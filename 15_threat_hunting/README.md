# Threat Hunting Phase

## Status

**Phase Status:** Completed  
**Platform:** Microsoft Sentinel / Azure Log Analytics  
**Primary Data Source:** Windows Security Events  
**Endpoint:** Windows 11 endpoint onboarded through Azure Arc and Azure Monitor Agent

---

## Objective

This phase documents practical threat hunting exercises using Microsoft Sentinel, Azure Log Analytics and Windows Security Events.

The goal was to move beyond alert-based monitoring and proactively search for suspicious behavior across authentication, PowerShell execution, persistence, privilege activity and defense evasion.

---

## Threat Hunting Mindset

A SOC analyst responds to alerts.  
A threat hunter proactively searches for suspicious activity even when no alert has fired.

This phase focused on asking investigative questions such as:

- Which accounts have the most failed logins?
- Which accounts have the most successful logons?
- Are privileged logons occurring?
- Who executed PowerShell?
- What launched PowerShell?
- Were services or scheduled tasks created?
- Was the Security log cleared?

---

## Completed Hunts

| Hunt | Focus Area | Event IDs | Status |
|---|---|---:|---|
| 1 | Authentication hunting | 4624, 4625, 4672 | Completed |
| 2 | PowerShell hunting | 4688 | Completed |
| 3 | Persistence hunting | 4697, 4698 | Completed |
| 4 | Privilege escalation hunting | 4672 | Completed |
| 5 | Defense evasion hunting | 1102 | Completed |

---

## Hunt Coverage

### Authentication

- Failed login activity
- Successful login activity
- Privileged logon activity
- Failed login patterns by account

### Execution

- PowerShell process execution
- Parent process review
- Service and agent launched PowerShell activity

### Persistence

- Service installation
- Scheduled task creation

### Privilege Escalation

- Special privileges assigned to new logons
- Admin-level account activity review

### Defense Evasion

- Security audit log clearing

---

## Key KQL Concepts Used

- `where`
- `project`
- `sort by`
- `summarize`
- `count()`
- Grouping by Account and Computer
- Sorting by frequency and timestamp

---

## MITRE ATT&CK Mapping

| Hunt Area | ATT&CK Tactic | Technique |
|---|---|---|
| Failed logins | Credential Access | T1110 Brute Force |
| Successful logons | Initial Access / Persistence | T1078 Valid Accounts |
| PowerShell execution | Execution | T1059.001 PowerShell |
| Service installation | Persistence / Privilege Escalation | T1543.003 Windows Service |
| Scheduled task creation | Persistence / Execution | T1053.005 Scheduled Task |
| Privileged logon | Privilege Escalation | Account privilege usage review |
| Security log cleared | Defense Evasion | T1070.001 Clear Windows Event Logs |

---

## Threat Hunting Outcome

The hunts showed lab-generated activity including failed logins, successful logons, PowerShell execution, service creation, scheduled task creation, privileged logons and Security log clearing.

No real malicious activity was identified. The observed activity was consistent with controlled lab testing and expected administrative/security tooling behavior.

---

## Analyst Summary

Threat hunting helped validate:

- Log coverage
- Event ID visibility
- PowerShell visibility
- Persistence-related event visibility
- Privileged logon visibility
- Defense evasion detection using Event ID 1102

This phase demonstrates practical SOC threat hunting skills using Microsoft Sentinel and KQL.
