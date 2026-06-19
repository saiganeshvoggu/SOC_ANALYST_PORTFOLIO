# MITRE ATT&CK Common SOC Use Cases

## Purpose
This document explains how SOC analysts use MITRE ATT&CK during daily monitoring, alert triage, threat hunting, and incident reporting.

## 1. Alert Classification
SOC analysts map alerts to MITRE tactics and techniques to describe attacker behavior clearly.

Example:
- Alert: Multiple failed logins
- Event: Windows Event ID 4625
- Technique: T1110 Brute Force
- Tactic: Credential Access

## 2. Threat Hunting
Analysts use MITRE techniques to build hunting hypotheses.

Example hypothesis:
Attackers may use PowerShell for execution.

Related technique:
- T1059.001 PowerShell

Possible data sources:
- Sysmon Event ID 1
- Windows Security Event ID 4688
- Splunk process creation logs

## 3. Incident Reporting
MITRE mapping improves incident reports by explaining what attacker behavior was observed.

Example:
Instead of writing only `PowerShell executed`, write:
`PowerShell execution was observed and mapped to MITRE ATT&CK T1059.001 - PowerShell under the Execution tactic.`

## 4. Detection Coverage
Security teams use MITRE ATT&CK to identify which attacker techniques are covered by detections and which are not.

Example:
- T1566 Phishing: Covered by email security and header analysis
- T1059 PowerShell: Covered by Sysmon process creation monitoring
- T1110 Brute Force: Covered by Windows Security Event ID 4625 monitoring

## 5. Interview Relevance
SOC analysts should be able to explain:
- What MITRE ATT&CK is
- Difference between tactic and technique
- How alerts are mapped to MITRE
- How MITRE helps threat hunting
- How MITRE improves reporting

## Portfolio Mapping

| Portfolio Section | Related MITRE Usage |
|---|---|
| Email Security | T1566 Phishing |
| Sysmon | T1059 Command and Scripting Interpreter |
| Windows Event Logs | T1110 Brute Force and T1078 Valid Accounts |
| Threat Intelligence | IOC enrichment and investigation support |
| Incident Response | Incident classification and reporting |

## Summary
MITRE ATT&CK helps analysts convert raw alerts into attacker behavior. This makes investigations easier to explain, prioritize, and document.
