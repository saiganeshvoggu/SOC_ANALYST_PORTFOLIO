# KQL Basics for Microsoft Sentinel

## What is KQL?
KQL stands for Kusto Query Language. It is used in Microsoft Sentinel and Log Analytics to search and analyze log data.

## Why SOC Analysts Use KQL
SOC analysts use KQL to:
- Search security logs
- Filter events
- Count failed logins
- Investigate suspicious users or IPs
- Build hunting queries
- Support incident investigation

## Basic Query Structure

```kql
TableName
| where Condition
| project Field1, Field2
| summarize count() by Field
| sort by TimeGenerated desc
```

## Example Queries

### Failed Logons
```kql
SecurityEvent
| where EventID == 4625
```

### Successful Logons
```kql
SecurityEvent
| where EventID == 4624
```

### Count Failed Logons by Account
```kql
SecurityEvent
| where EventID == 4625
| summarize FailedLogons=count() by Account
| sort by FailedLogons desc
```

### Recent Security Events
```kql
SecurityEvent
| sort by TimeGenerated desc
| project TimeGenerated, EventID, Account, Computer
```

## Interview Talking Point
KQL is the query language used in Microsoft Sentinel to search and analyze security logs. It helps analysts investigate incidents, detect suspicious patterns, and perform threat hunting.
