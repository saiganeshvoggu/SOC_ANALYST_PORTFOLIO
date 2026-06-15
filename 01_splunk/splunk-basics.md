# Splunk Basics for SOC Analysts

## Objective
Document basic Splunk concepts and SPL commands used during SOC Analyst investigations.

## What is Splunk?
Splunk is a SIEM and log analysis platform used to collect, search, analyze, and visualize security logs.

## Why SOC Analysts Use Splunk
- Search security logs
- Investigate suspicious activity
- Validate alerts
- Hunt for threats
- Extract fields from raw logs
- Correlate activity across hosts and users

## Basic Search Structure

```spl
index=<index_name> sourcetype=<sourcetype_name>
```

Example:

```spl
index=main sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
```

## SPL Commands Covered

| Command | Purpose |
|---|---|
| search | Filter events |
| table | Display selected fields |
| stats | Aggregate results |
| count | Count events |
| sort | Order results |
| rex | Extract fields using regex |
| where | Apply conditions |

## Key Learning
Sysmon logs were ingested as raw XML, so EventCode was not always automatically extracted. Raw XML search and `rex` extraction were used.

## Interview Talking Point
I used Splunk to investigate Sysmon logs, extracted fields from raw XML using `rex`, and created SPL queries using `search`, `table`, `stats`, `count`, and `sort` for process creation analysis.
