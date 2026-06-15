# Splunk + Sysmon Lab Summary Report

## Lab Name
Splunk + Sysmon Integration and Basic Threat Hunting

## Analyst
Sai Ganesh Voggu

## Objective
Build hands-on SOC Analyst experience by integrating Sysmon endpoint logs into Splunk and performing basic threat hunting using SPL queries.

## Tools Used
- Splunk Enterprise
- Microsoft Sysmon
- Windows Event Logs
- SPL Search Processing Language

## Data Source

| Field | Value |
|---|---|
| Log Source | Microsoft-Windows-Sysmon/Operational |
| Splunk Index | main |
| Sourcetype | XmlWinEventLog:Microsoft-Windows-Sysmon/Operational |
| Primary Event Tested | Event ID 1 - Process Creation |

## Investigation Summary
Sysmon was installed on a Windows endpoint and configured to generate detailed endpoint telemetry. Splunk was configured to ingest Sysmon operational logs. After ingestion was verified, basic SPL searches were used to review process creation activity and identify suspicious execution patterns.

## Findings
- Sysmon logs were successfully ingested into Splunk.
- Process creation telemetry was searchable in Splunk.
- Event ID 1 provided useful details such as image path, command line, user, and parent process.
- Basic threat hunting searches were created for PowerShell activity, encoded commands, living-off-the-land binaries, DNS queries, and process-network behavior.

## Skills Practiced
- SIEM setup validation
- Log source verification
- Sysmon event analysis
- SPL query writing
- Process execution hunting
- SOC-style documentation

## MITRE ATT&CK Relevance

| Tactic | Technique Example | Relevance |
|---|---|---|
| Execution | Command and Scripting Interpreter | Detect suspicious PowerShell or command-line execution |
| Defense Evasion | Obfuscated Files or Information | Identify encoded or obfuscated command usage |
| Command and Control | Application Layer Protocol | Review suspicious outbound connections and DNS activity |
| Persistence | Registry Run Keys / Startup Folder | Future Sysmon registry monitoring use case |

## Evidence

Screenshots should be uploaded under:

```text
evidence/splunk/
evidence/sysmon/
```

Key screenshots:

- splunk-sysmon-search.png
- splunk-process-frequency-analysis.png
- splunk-commandline-analysis.png
- sysmon-event-viewer-operational.png
- sysmon-eventid1-processcreation-1.png

## Final Status
Completed.

This lab establishes a foundation for SOC Analyst work involving endpoint telemetry, SIEM investigation, and threat hunting workflows.

## Resume Bullet
Configured Microsoft Sysmon log ingestion into Splunk and developed practical SPL threat hunting queries to investigate process creation, PowerShell usage, suspicious command-line activity, and endpoint telemetry for SOC Analyst workflows.
