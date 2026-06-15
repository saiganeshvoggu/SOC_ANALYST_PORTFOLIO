# Splunk + Sysmon Integration Lab

## Objective
Integrate Microsoft Sysmon logs with Splunk and validate that endpoint telemetry is searchable for SOC Analyst workflows.

## Lab Environment

| Component | Details |
|---|---|
| Operating System | Windows 11 |
| SIEM Tool | Splunk Enterprise local instance |
| Endpoint Telemetry | Microsoft Sysmon |
| Log Source | Microsoft-Windows-Sysmon/Operational |
| Splunk Index | main |
| Sourcetype | XmlWinEventLog:Microsoft-Windows-Sysmon/Operational |

## What Was Completed
- Installed and verified Splunk locally.
- Installed Microsoft Sysmon on Windows.
- Confirmed Sysmon Operational logs were generated.
- Configured Splunk to ingest Sysmon event logs.
- Verified Sysmon process creation events in Splunk.
- Practiced basic searches using Sysmon telemetry.

## Primary Event Tested
Sysmon Event ID 1 - Process Creation.

Useful fields:
- Image
- CommandLine
- ParentImage
- ParentCommandLine
- User
- ProcessGuid
- ProcessId
- Hashes

## SOC Analyst Skills Demonstrated
- SIEM log ingestion validation
- Endpoint telemetry analysis
- Sysmon Event ID understanding
- SPL query writing
- Process execution investigation
- Suspicious command-line review
- Evidence-based documentation

## Interview Talking Point
I configured Sysmon telemetry ingestion into Splunk, validated Event ID 1 process creation logs, and created SPL searches to identify process execution patterns and unusual parent-child process relationships.

## Status
Completed as part of Phase 1 SOC Analyst hands-on learning.
