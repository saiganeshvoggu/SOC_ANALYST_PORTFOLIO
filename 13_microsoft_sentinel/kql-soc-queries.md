# KQL SOC Queries

## Overview

Kusto Query Language (KQL) is the primary query language used in Microsoft Sentinel and Log Analytics Workspace.

SOC Analysts use KQL to:

- Search logs
- Validate data ingestion
- Investigate incidents
- Detect suspicious activity
- Perform threat hunting
- Build analytics rules

---

## Basic Query Structure

```kql
TableName
| where Condition
| project Field1, Field2
| summarize count() by Field
| sort by Field desc
```

---

## Query 1 - Verify Agent Connectivity

### Purpose

Confirm that the Azure Arc machine and Azure Monitor Agent are sending data to Log Analytics.

```kql
Heartbeat
| take 10
```

### SOC Use Case

- Agent health verification
- Data ingestion troubleshooting
- Connector validation

---

## Query 2 - Verify Windows Security Events

### Purpose

Confirm that Windows Security Events are being collected.

```kql
SecurityEvent
| where TimeGenerated > ago(1h)
| take 20
```

### SOC Use Case

- Security event ingestion validation
- Windows endpoint monitoring
- Sentinel connector verification

---

## Query 3 - Event Frequency by Event ID

### Purpose

Identify the most common Windows Security Event IDs.

```kql
SecurityEvent
| summarize Count=count() by EventID
| sort by Count desc
```

### SOC Use Case

- Baseline normal event activity
- Identify noisy events
- Prioritize investigation targets

---

## Query 4 - Failed Login Attempts

### Purpose

Identify failed authentication attempts.

```kql
SecurityEvent
| where EventID == 4625
| sort by TimeGenerated desc
```

### SOC Use Case

- Failed login investigation
- Brute-force detection
- Password spraying detection
- Account compromise triage

---

## Query 5 - Successful Logins

### Purpose

Review successful authentication activity.

```kql
SecurityEvent
| where EventID == 4624
| sort by TimeGenerated desc
```

### SOC Use Case

- Login validation
- User activity review
- Authentication investigation

---

## Query 6 - Privileged Logins

### Purpose

Identify logons where special privileges were assigned.

```kql
SecurityEvent
| where EventID == 4672
| sort by TimeGenerated desc
```

### SOC Use Case

- Administrative logon monitoring
- Privileged account review
- Suspicious access investigation

---

## Query 7 - Recent Security Activity

### Purpose

Review recent security events with only important columns.

```kql
SecurityEvent
| where TimeGenerated > ago(24h)
| project TimeGenerated, EventID, Computer
| take 50
```

### SOC Use Case

- Quick triage
- Event timeline review
- Endpoint activity validation

---

## Query 8 - Failed Login Count by User

### Purpose

Identify users receiving multiple failed logins.

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedLogins=count() by Account
| sort by FailedLogins desc
```

---

## Query 9 - Failed Login Count by Host

### Purpose

Identify systems receiving login failures.

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedLogins=count() by Computer
| sort by FailedLogins desc
```

---

## Query 10 - Top Hosts by Activity

### Purpose

Identify active systems.

```kql
SecurityEvent
| summarize ActivityCount=count() by Computer
| sort by ActivityCount desc
```

---

## Query 11 - Top Accounts by Activity

### Purpose

Identify accounts generating the highest number of events.

```kql
SecurityEvent
| summarize ActivityCount=count() by Account
| sort by ActivityCount desc
```

---

## Query 12 - Logoff Events

### Purpose

Review logoff activity.

```kql
SecurityEvent
| where EventID == 4634
| sort by TimeGenerated desc
```

---

## Query 13 - Security Log Cleared

### Purpose

Identify attempts to clear the Windows Security log.

```kql
SecurityEvent
| where EventID == 1102
| sort by TimeGenerated desc
```

### SOC Use Case

- Defense evasion monitoring
- Suspicious log tampering investigation
- Incident response escalation

---

## Query 14 - User Created

### Purpose

Identify newly created local or domain users where available.

```kql
SecurityEvent
| where EventID == 4720
| sort by TimeGenerated desc
```

---

## Query 15 - User Added to Security Group

### Purpose

Identify group membership changes.

```kql
SecurityEvent
| where EventID in (4728, 4732)
| sort by TimeGenerated desc
```

---

## Lab Results Observed

During the Microsoft Sentinel setup lab, the following tables and event types were successfully observed:

- `Heartbeat` table returned the onboarded Windows machine.
- `SecurityEvent` table returned Windows Security Events.
- Event ID frequency query returned multiple Windows event IDs.
- Event ID `4624` returned successful logon activity.
- Event ID `4672` appeared in the event frequency output.

---

## Interview Notes

### What is KQL?

KQL stands for Kusto Query Language. It is used in Microsoft Sentinel and Log Analytics to search, filter, summarize and investigate log data.

### Why is KQL important for SOC Analysts?

KQL allows SOC analysts to investigate incidents, validate alerts, perform threat hunting, build detections and analyze security telemetry.

### Common KQL Operators

- `where`
- `project`
- `summarize`
- `count()`
- `sort by`
- `extend`
- `join`
- `ago()`
- `in`

---

## Evidence Screenshots To Add

Recommended screenshot names:

- `heartbeat-query-results.png`
- `securityevent-query-results.png`
- `eventid-frequency-summary.png`
- `successful-logon-4624-results.png`
- `recent-security-events-results.png`
