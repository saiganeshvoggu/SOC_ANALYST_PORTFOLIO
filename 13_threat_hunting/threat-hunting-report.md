# Threat Hunting Report

## Report Status

**Status:** Completed  
**Phase:** Threat Hunting  
**Platform:** Microsoft Sentinel / Azure Log Analytics  
**Data Source:** Windows Security Events  
**Environment:** Personal SOC lab

---

## Scope

This hunt reviewed Windows endpoint activity for suspicious authentication, PowerShell execution, persistence, privilege activity and defense evasion.

---

## Data Sources Reviewed

| Data Source | Purpose |
|---|---|
| SecurityEvent | Windows Security Event hunting |
| Windows Event Viewer | Local validation |
| Microsoft Sentinel / Log Analytics | KQL hunting and SIEM review |

---

## Hunt Areas

| Hunt Area | Event IDs |
|---|---|
| Authentication | 4624, 4625 |
| Privileged Logons | 4672 |
| PowerShell Execution | 4688 |
| Persistence | 4697, 4698 |
| Defense Evasion | 1102 |

---

## Findings

### Finding 1 - Failed Login Activity

Failed login activity was observed using Event ID 4625.

**Assessment:** Expected lab-generated activity.  
**Risk:** Low

---

### Finding 2 - Successful Login Activity

Successful login activity was observed using Event ID 4624.

High activity was seen from expected accounts such as SYSTEM, Microsoft account login activity and service accounts.

**Assessment:** Expected system and user behavior.  
**Risk:** Low

---

### Finding 3 - PowerShell Execution

PowerShell execution was observed through Event ID 4688.

Parent processes included expected lab/security tooling such as Splunk and Azure Connected Machine Agent.

**Assessment:** Expected administrative and lab activity.  
**Risk:** Low

---

### Finding 4 - Persistence Events

Service installation and scheduled task creation events were observed:

- 4697 - A service was installed in the system
- 4698 - A scheduled task was created

**Assessment:** Controlled lab-generated persistence simulation.  
**Risk:** Low

---

### Finding 5 - Privileged Logon Activity

Privileged logon activity was observed using Event ID 4672.

Accounts included SYSTEM and expected lab user activity.

**Assessment:** Expected system and lab activity.  
**Risk:** Low

---

### Finding 6 - Security Log Cleared

Event ID 1102 was observed:

```text
1102 - The audit log was cleared.
```

**Assessment:** Controlled lab-generated defense evasion simulation.  
**Risk:** Low in lab / High in production

---

## Overall Assessment

No real malicious activity was identified during this hunt. The observed events were consistent with controlled lab activity and expected administrative/security tooling behavior.

---

## Recommendations

For a production SOC environment:

1. Alert on Security Event ID 1102.
2. Monitor repeated failed logins using Event ID 4625.
3. Correlate failed logins followed by successful logons.
4. Monitor PowerShell execution and collect command-line arguments.
5. Alert on unexpected service installation and scheduled task creation.
6. Review privileged logon activity for unusual accounts or times.
7. Ensure Security, System and PowerShell Operational logs are collected by SIEM.

---

## MITRE ATT&CK Summary

| Activity | Technique |
|---|---|
| Failed login activity | T1110 Brute Force |
| Valid account usage | T1078 Valid Accounts |
| PowerShell execution | T1059.001 PowerShell |
| Service installation | T1543.003 Windows Service |
| Scheduled task creation | T1053.005 Scheduled Task |
| Security log clearing | T1070.001 Clear Windows Event Logs |

---

## Final Conclusion

Threat hunting phase completed successfully. This phase demonstrates proactive hunting ability using Microsoft Sentinel and KQL across authentication, execution, persistence, privilege escalation and defense evasion behaviors.
