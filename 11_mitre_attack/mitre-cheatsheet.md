# MITRE ATT&CK SOC Analyst Cheat Sheet

## Purpose
This cheat sheet summarizes important MITRE ATT&CK tactics and techniques commonly discussed in SOC Analyst interviews and investigations.

## Common Tactics

| Tactic | Purpose |
|---|---|
| Initial Access | How attackers enter an environment |
| Execution | How attackers run code |
| Persistence | How attackers maintain access |
| Privilege Escalation | How attackers gain higher permissions |
| Defense Evasion | How attackers avoid detection |
| Credential Access | How attackers steal credentials |
| Discovery | How attackers learn about the environment |
| Lateral Movement | How attackers move across systems |
| Collection | How attackers gather data |
| Command and Control | How attackers communicate with systems |
| Exfiltration | How attackers steal data |
| Impact | How attackers disrupt operations |

## Important Techniques

| Technique ID | Technique | SOC Relevance |
|---|---|---|
| T1566 | Phishing | Common initial access method |
| T1059 | Command and Scripting Interpreter | PowerShell, CMD, script execution |
| T1059.001 | PowerShell | Suspicious PowerShell execution |
| T1059.003 | Windows Command Shell | CMD execution activity |
| T1110 | Brute Force | Failed login and password attack detection |
| T1078 | Valid Accounts | Use of legitimate credentials |
| T1003 | OS Credential Dumping | Credential theft techniques |
| T1027 | Obfuscated Files or Information | Encoded or hidden command activity |
| T1041 | Exfiltration Over C2 Channel | Data theft over command-and-control channels |
| T1486 | Data Encrypted for Impact | Ransomware activity |

## Mapping Examples From Portfolio Labs

| Lab Activity | Event / Tool | MITRE Technique | Tactic |
|---|---|---|---|
| Failed login investigation | Windows Event ID 4625 | T1110 Brute Force | Credential Access |
| Successful login investigation | Windows Event ID 4624 | T1078 Valid Accounts | Defense Evasion / Persistence / Privilege Escalation |
| Process execution analysis | Sysmon Event ID 1 | T1059 Command and Scripting Interpreter | Execution |
| Phishing email investigation | Email Header Analysis | T1566 Phishing | Initial Access |
| IOC analysis | VirusTotal / URLScan | Threat Intelligence Enrichment | Investigation Support |

## Interview Answer
MITRE ATT&CK is a knowledge base of attacker tactics and techniques. SOC analysts use it to classify alerts, understand attacker behavior, map detections, write reports, and explain investigations in a standardized way.
