# MITRE ATT&CK Mapping Lab

## Objective
Map existing SOC portfolio labs to MITRE ATT&CK tactics and techniques.

## Why This Matters
SOC analysts use MITRE ATT&CK to explain alerts in terms of attacker behavior. Instead of documenting only the raw event, analysts map the event to a tactic and technique.

## Portfolio Lab Mapping

| Portfolio Activity | Event / Source | MITRE Technique | Tactic |
|---|---|---|---|
| Failed login investigation | Windows Event ID 4625 | T1110 Brute Force | Credential Access |
| Successful login investigation | Windows Event ID 4624 | T1078 Valid Accounts | Valid Accounts / Account Abuse Context |
| Process creation analysis | Sysmon Event ID 1 | T1059 Command and Scripting Interpreter | Execution |
| Email header analysis | Email investigation | T1566 Phishing | Initial Access |
| Domain and URL reputation review | VirusTotal and URLScan | IOC enrichment | Investigation Support |
| Special privileges assigned | Windows Event ID 4672 | Privileged account activity | Privilege Monitoring |

## Evidence

Screenshots should be uploaded under:

```text
evidence/mitre-attack/
```

Expected evidence:

- mitre-matrix-overview.png
- t1566-phishing.png
- t1059-powershell.png
- t1003-credential-dumping.png
- tactic-initial-access.png
- tactic-execution.png
- tactic-credential-access.png
- tactic-privilege-escalation.png
- mitre-mapping-table.png

## Interview Talking Point
I mapped my hands-on investigations to MITRE ATT&CK techniques such as T1566 Phishing, T1059 Command and Scripting Interpreter, T1110 Brute Force, and T1078 Valid Accounts. This helps explain raw security events as attacker behavior.
