# Sysmon Basics for SOC Analysts

## Objective
This guide explains Microsoft Sysmon basics, why SOC analysts use it, how to verify it, and how to investigate Sysmon Event ID 1 process creation events.

## What is Sysmon?
Sysmon is a Microsoft Sysinternals tool that provides detailed Windows endpoint telemetry. It records events such as process creation, network connections, file creation, registry activity, DNS queries, and other security-relevant activity.

## Why SOC Analysts Use Sysmon
SOC analysts use Sysmon to:
- Investigate process execution
- Analyze command-line activity
- Review parent-child process relationships
- Identify suspicious PowerShell activity
- Detect living-off-the-land binary abuse
- Investigate suspicious network and DNS activity
- Enrich incident investigations with endpoint telemetry

## Verified Local Setup

| Item | Status |
|---|---|
| Sysmon installed | Verified |
| Sysmon service running | Verified |
| Startup type automatic | Verified |
| Event Viewer operational log active | Verified |
| Event ID 1 process creation logs visible | Verified |
| Sysmon configuration available using sysmon64 -c | Verified |
| Sysmon schema available using sysmon64 -s | Verified |

## Event Viewer Path
Applications and Services Logs > Microsoft > Windows > Sysmon > Operational

## Important Sysmon Event IDs

| Event ID | Event Name | SOC Analyst Value |
|---|---|---|
| 1 | Process Create | Investigate process execution and command-line activity |
| 3 | Network Connection | Review process-based outbound network connections |
| 7 | Image Loaded | Analyze DLL loading behavior |
| 8 | CreateRemoteThread | Detect process injection behavior |
| 10 | Process Access | Investigate credential dumping behavior |
| 11 | File Create | Identify suspicious files or dropped payloads |
| 12/13/14 | Registry Events | Investigate persistence and configuration changes |
| 22 | DNS Query | Investigate suspicious domain lookups |

## Event ID 1 Useful Fields
- ProcessGuid
- ProcessId
- Image
- OriginalFileName
- CommandLine
- CurrentDirectory
- User
- IntegrityLevel
- Hashes
- ParentProcessGuid
- ParentProcessId
- ParentImage
- ParentCommandLine
- ParentUser

## Example Process Relationship Observed
Parent Process: splunkd.exe
Child Process: splunk-optimize.exe

This is normal Splunk activity, but the same method helps identify suspicious execution chains.

## Interview Talking Point
I installed and verified Sysmon on Windows, confirmed the Sysmon64 service was running automatically, analyzed Event ID 1 process creation events, reviewed command-line and parent process details, and integrated the telemetry into Splunk for threat hunting.
