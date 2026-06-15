# Sysmon Event Analysis Notes

## Objective
Document key Sysmon events that are useful for SOC Analyst investigations and threat hunting.

## Why Sysmon Matters
Windows Security logs are useful, but Sysmon provides richer endpoint telemetry. It helps analysts investigate process execution, network connections, file creation, registry activity, and persistence behavior.

## Important Sysmon Event IDs

| Event ID | Event Name | SOC Value |
|---|---|---|
| 1 | Process Creation | Detect suspicious execution and parent-child process chains |
| 3 | Network Connection | Identify outbound connections from suspicious processes |
| 7 | Image Loaded | Investigate DLL loading behavior |
| 8 | CreateRemoteThread | Detect process injection behavior |
| 10 | Process Access | Investigate credential dumping attempts |
| 11 | File Created | Detect dropped payloads and suspicious files |
| 12/13/14 | Registry Events | Detect persistence and configuration changes |
| 15 | FileCreateStreamHash | Detect alternate data streams |
| 22 | DNS Query | Investigate suspicious domain lookups |

## Event ID 1: Process Creation
Commonly used for investigating suspicious command execution.

Analyst questions:
- What process executed?
- Who executed it?
- What was the command line?
- What parent process launched it?
- Is the process path expected?
- Are there suspicious flags or encoded commands?

## Event ID 3: Network Connection
Useful for identifying suspicious outbound network activity.

Analyst questions:
- Which process created the connection?
- What destination IP was contacted?
- What port was used?
- Is the destination internal or external?
- Is the process expected to make network connections?

## Event ID 22: DNS Query
Useful for domain investigation and phishing/malware triage.

## Suspicious Patterns to Hunt
- PowerShell with encoded commands
- LOLBins such as certutil.exe, bitsadmin.exe, rundll32.exe, regsvr32.exe, mshta.exe
- Office applications launching script interpreters
- Unknown processes making outbound network connections
- Suspicious DNS queries from unusual processes
- Registry changes related to persistence

## Interview Talking Point
I used Sysmon telemetry in Splunk to analyze process creation, network connections, and DNS queries. I focused on Event ID 1 for execution hunting, Event ID 3 for outbound connection analysis, and Event ID 22 for suspicious domain investigation.
