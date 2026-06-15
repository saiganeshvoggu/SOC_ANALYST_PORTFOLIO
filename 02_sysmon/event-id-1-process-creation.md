# Sysmon Event ID 1 - Process Creation Investigation

## Objective
Document how to investigate Sysmon Event ID 1 process creation logs as part of SOC Analyst threat hunting.

## What is Event ID 1?
Sysmon Event ID 1 records process creation activity. It tells analysts what process executed, who executed it, what command line was used, and what parent process launched it.

## Why Event ID 1 is Important
Attackers often execute commands, scripts, living-off-the-land binaries, malware payloads, or post-exploitation tools. Event ID 1 gives visibility into execution activity.

## Key Fields to Review

| Field | Investigation Purpose |
|---|---|
| Image | Identifies the executed process path |
| CommandLine | Shows how the process was executed |
| ParentImage | Shows what launched the process |
| ParentCommandLine | Provides parent process execution context |
| User | Shows the account context |
| Hashes | Supports file reputation and malware analysis |
| ProcessGuid | Helps correlate process activity |
| ParentProcessGuid | Helps track process lineage |
| IntegrityLevel | Shows process integrity level |

## Verified Lab Example
Observed process relationship:

ParentImage: C:\Program Files\Splunk\bin\splunkd.exe
Image: splunk-optimize.exe
User: NT SERVICE\Splunkd
Event ID: 1
Task Category: Process Create

This appears normal for Splunk internal activity, but the same method is used to detect suspicious behavior.

## Investigation Workflow
1. Open Event Viewer.
2. Navigate to Sysmon Operational logs.
3. Open Event ID 1.
4. Review process name and full path.
5. Review command line.
6. Review parent process.
7. Review user context.
8. Review hashes.
9. Determine whether the activity is expected or suspicious.
10. If suspicious, enrich file hash, process path, and command line indicators.

## Suspicious Behaviors to Watch
- PowerShell with encoded commands
- Office applications launching PowerShell or CMD
- Scripts running from temporary folders
- Unknown executables running from user profile folders
- Living-off-the-land binaries used with suspicious parameters
- Unexpected parent-child process relationships
- Processes making external network connections

## Interview Answer
When investigating Sysmon Event ID 1, I first review the process image, command line, parent image, parent command line, user context, and hashes. Then I determine whether the parent-child relationship is expected. If suspicious, I enrich the hash, check related network or DNS activity, and document the finding in an incident report.
