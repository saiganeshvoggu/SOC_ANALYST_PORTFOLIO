# Incident Investigation Phase

## Status

**Phase Status:** Completed  
**Platform:** Microsoft Sentinel / Azure Log Analytics  
**Primary Data Source:** Windows Security Events  
**Endpoint:** Windows 11 endpoint onboarded through Azure Arc and Azure Monitor Agent

---

## Objective

This phase documents practical SOC incident investigation workflows using Microsoft Sentinel, KQL and Windows Security Events.

The goal was to move from hunting and detection into analyst-style investigation: alert review, evidence collection, timeline analysis, severity classification, root cause assessment and closure notes.

---

## Completed Investigations

| Investigation | Focus Area | Event IDs | Status |
|---|---|---:|---|
| 1 | Failed login investigation | 4625 | Completed |
| 2 | Failed-to-successful logon correlation | 4625, 4624 | Completed |
| 3 | PowerShell execution investigation | 4688 | Completed |
| 4 | Persistence investigation | 4697, 4698 | Completed |
| 5 | Privileged logon review | 4672 | Completed |
| 6 | Security log cleared review | 1102 | Completed |

---

## Investigation Workflow

1. Identify the alert or suspicious event.
2. Validate the Event ID and log source.
3. Review affected account and host.
4. Check related activity before and after the event.
5. Correlate authentication, execution, privilege and persistence events.
6. Assign severity.
7. Determine whether activity is benign, suspicious or malicious.
8. Document findings and closure notes.

---

## Key Skills Practiced

- Alert triage
- Timeline analysis
- Authentication investigation
- Failed-to-successful login correlation
- PowerShell parent-child process review
- Persistence investigation
- Privilege activity review
- Security log clearing review
- MITRE ATT&CK mapping
- Severity classification
- SOC-style closure documentation

---

## MITRE ATT&CK Mapping

| Investigation Area | ATT&CK Tactic | Technique |
|---|---|---|
| Failed logins | Credential Access | T1110 Brute Force |
| Successful logon after failures | Initial Access / Persistence | T1078 Valid Accounts |
| PowerShell execution | Execution | T1059.001 PowerShell |
| Service installation | Persistence / Privilege Escalation | T1543.003 Windows Service |
| Scheduled task creation | Persistence / Execution | T1053.005 Scheduled Task |
| Security log cleared | Defense Evasion | T1070.001 Clear Windows Event Logs |

---

## Outcome

The incident investigation phase confirmed practical ability to review Sentinel events, correlate related activity, classify severity and document analyst conclusions. All observed activity was consistent with controlled lab testing and expected administrative/security tooling behavior.
