# Log Analytics Workspace

## Overview

Log Analytics Workspace is the central data storage and analytics platform used by Microsoft Sentinel. All collected security logs, alerts, and telemetry are stored inside a Log Analytics Workspace, where analysts can search, investigate, and detect threats using Kusto Query Language (KQL).

---

## Purpose

The primary purpose of a Log Analytics Workspace is to:

* Collect logs from multiple sources
* Store security telemetry
* Support threat hunting activities
* Enable incident investigation
* Provide data for analytics rules
* Generate alerts and incidents

---

## Data Flow

Data Source

↓

Data Connector

↓

Log Analytics Workspace

↓

KQL Queries

↓

Analytics Rules

↓

Alerts

↓

Incidents

↓

Investigation

---

## Common Data Sources

A Log Analytics Workspace can collect data from:

### Windows Systems

* Security Events
* Event Viewer Logs
* Sysmon Logs

### Linux Systems

* Syslog
* Authentication Logs

### Cloud Services

* Microsoft Entra ID
* Microsoft Defender
* Microsoft 365
* Azure Activity Logs

### Network Devices

* Firewalls
* Routers
* IDS/IPS Solutions

---

## Important Tables

### SecurityEvent

Contains Windows Security Event Logs.

Examples:

* Event ID 4624
* Event ID 4625
* Event ID 4672

---

### SecurityAlert

Contains generated security alerts.

---

### SecurityIncident

Contains Sentinel incidents.

---

### SigninLogs

Stores Azure AD / Entra ID sign-in activity.

---

### AuditLogs

Stores administrative and configuration changes.

---

### Syslog

Stores Linux system logs.

---

### Heartbeat

Shows device connectivity and agent status.

---

## Benefits

* Centralized log storage
* Fast threat hunting
* Long-term log retention
* Powerful KQL searching
* Integration with Microsoft Sentinel

---

## SOC Analyst Usage

A SOC Analyst uses the Log Analytics Workspace to:

* Search logs
* Investigate alerts
* Validate incidents
* Hunt threats
* Create detection rules

---

## Interview Questions

### What is a Log Analytics Workspace?

A Log Analytics Workspace is a centralized Azure service used to collect, store, analyze, and query logs from multiple sources.

---

### Why is Log Analytics Workspace important in Sentinel?

Microsoft Sentinel uses Log Analytics Workspace as its backend storage and analytics engine for security monitoring and threat detection.

---

## Evidence Screenshots

Add screenshots later:

* Workspace Overview
* Tables View
* SecurityEvent Table
* SigninLogs Table
* Sample KQL Query
