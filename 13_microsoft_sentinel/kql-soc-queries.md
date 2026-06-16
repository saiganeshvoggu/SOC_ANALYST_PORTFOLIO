# KQL SOC Queries

## Overview

Kusto Query Language (KQL) is the primary query language used in Microsoft Sentinel and Log Analytics Workspace.

SOC Analysts use KQL to:

* Search logs
* Investigate incidents
* Detect suspicious activity
* Perform threat hunting
* Build Analytics Rules

---

# Basic Query Structure

```kql
TableName
| where Condition
| project Field1, Field2
| summarize count() by Field
| sort by Field desc
```

---

# Query 1 - Failed Login Attempts

## Purpose

Identify failed authentication attempts.

```kql
SecurityEvent
| where EventID == 4625
```

## SOC Use Case

* Brute Force Detection
* Password Spraying Detection
* Account Compromise Investigation

---

# Query 2 - Successful Logins

## Purpose

Review successful authentication activity.

```kql
SecurityEvent
| where EventID == 4624
```

## SOC Use Case

* User Activity Review
* Login Validation
* Account Investigation

---

# Query 3 - Logoff Events

## Purpose

Review user logoff activity.

```kql
SecurityEvent
| where EventID == 4634
```

---

# Query 4 - Privileged Logins

## Purpose

Identify administrative access.

```kql
SecurityEvent
| where EventID == 4672
```

## SOC Use Case

* Privilege Escalation Monitoring
* Administrative Activity Review

---

# Query 5 - Failed Login Count by User

## Purpose

Identify users receiving multiple failed logins.

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedLogins=count() by Account
| sort by FailedLogins desc
```

---

# Query 6 - Failed Login Count by Host

## Purpose

Identify systems receiving login failures.

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedLogins=count() by Computer
| sort by FailedLogins desc
```

---

# Query 7 - Events in Last 24 Hours

## Purpose

Review recent activity.

```kql
SecurityEvent
| where TimeGenerated > ago(24h)
```

---

# Query 8 - Event Frequency

## Purpose

Identify most common security events.

```kql
SecurityEvent
| summarize EventCount=count() by EventID
| sort by EventCount desc
```

---

# Query 9 - Top Users by Activity

## Purpose

Identify active users.

```kql
SecurityEvent
| summarize ActivityCount=count() by Account
| sort by ActivityCount desc
```

---

# Query 10 - Top Hosts by Activity

## Purpose

Identify active systems.

```kql
SecurityEvent
| summarize ActivityCount=count() by Computer
| sort by ActivityCount desc
```

---

# Query 11 - PowerShell Activity

## Purpose

Identify PowerShell execution.

```kql
SecurityEvent
| where Process has "powershell"
```

## MITRE Mapping

T1059.001

PowerShell

---

# Query 12 - CMD Activity

## Purpose

Identify command prompt execution.

```kql
SecurityEvent
| where Process has "cmd.exe"
```

---

# Query 13 - Recent Alerts

## Purpose

Review generated alerts.

```kql
SecurityAlert
| sort by TimeGenerated desc
```

---

# Query 14 - Recent Incidents

## Purpose

Review incident activity.

```kql
SecurityIncident
| sort by TimeGenerated desc
```

---

# Query 15 - User Sign-in Activity

## Purpose

Review Azure/Entra sign-ins.

```kql
SigninLogs
| sort by TimeGenerated desc
```

---

# Query 16 - Failed Sign-ins

## Purpose

Review failed Entra ID logins.

```kql
SigninLogs
| where ResultType != 0
```

---

# Query 17 - Successful Sign-ins

## Purpose

Review successful Entra ID logins.

```kql
SigninLogs
| where ResultType == 0
```

---

# Query 18 - Security Incident Count

## Purpose

Count incidents by severity.

```kql
SecurityIncident
| summarize count() by Severity
```

---

# Query 19 - Alert Count by Severity

## Purpose

Review alert distribution.

```kql
SecurityAlert
| summarize count() by AlertSeverity
```

---

# Query 20 - Threat Hunting Starter Query

## Purpose

Review all recent security activity.

```kql
SecurityEvent
| where TimeGenerated > ago(7d)
| sort by TimeGenerated desc
```

---

# Interview Questions

## What is KQL?

KQL stands for Kusto Query Language and is used to search, analyze, and investigate logs within Microsoft Sentinel.

---

## Why is KQL important?

KQL enables SOC Analysts to:

* Investigate incidents
* Hunt threats
* Build detections
* Analyze logs

---

## What are the most commonly used operators?

* where
* project
* summarize
* count
* sort
* extend
* join

---

# SOC Analyst Practical Workflow

Incident Created

↓

Review Incident

↓

Run KQL Query

↓

Validate Activity

↓

Determine Root Cause

↓

Document Findings

↓

Respond

---

# Evidence Screenshots

Add screenshots later:

* Failed Login Query
* Successful Login Query
* PowerShell Query
* Alert Query
* Incident Query
* Threat Hunting Query
* KQL Results
