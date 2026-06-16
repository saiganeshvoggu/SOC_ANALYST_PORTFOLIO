# Data Connectors

## Overview

Data Connectors are used to ingest logs and security telemetry into Microsoft Sentinel. A connector acts as a bridge between a data source and the Log Analytics Workspace.

Without data connectors, Microsoft Sentinel cannot collect logs, generate alerts, or create incidents.

---

## Purpose

Data Connectors help:

* Collect logs from systems and applications
* Ingest cloud security events
* Monitor user activity
* Detect threats
* Enable incident investigation

---

## Data Connector Workflow

Data Source

↓

Data Connector

↓

Log Analytics Workspace

↓

KQL Query

↓

Analytics Rule

↓

Alert

↓

Incident

---

## Common Data Connectors

### Windows Security Events

Collects Windows Event Logs.

Examples:

* Event ID 4624
* Event ID 4625
* Event ID 4672
* Event ID 4688

Used for:

* Login monitoring
* Brute force detection
* Account compromise investigations

---

### Microsoft Defender for Endpoint

Collects:

* Endpoint alerts
* Malware detections
* Device telemetry

Used for:

* Threat detection
* Endpoint investigations

---

### Microsoft Entra ID

Collects:

* User sign-ins
* Authentication events
* Administrative activities

Used for:

* Identity monitoring
* Suspicious login detection

---

### Microsoft 365

Collects:

* Exchange activity
* SharePoint activity
* Teams activity

Used for:

* User activity monitoring
* Insider threat detection

---

### Syslog Connector

Collects logs from:

* Linux systems
* Firewalls
* Routers
* Network devices

Used for:

* Network monitoring
* Infrastructure security

---

### Common Event Format (CEF)

Used to integrate:

* Fortinet
* Palo Alto
* Check Point
* Cisco Devices

Provides normalized log collection.

---

## Connector Status

A connector can be:

### Connected

Logs are successfully flowing.

### Disconnected

No log ingestion.

### Misconfigured

Connector exists but data is not reaching Sentinel.

---

## Connector Health Checks

SOC Analysts should verify:

* Connector Status
* Last Data Received
* Data Volume
* Table Population
* Ingestion Delays

---

## SOC Analyst Responsibilities

Daily checks:

* Verify connectors are healthy
* Confirm log ingestion
* Investigate missing logs
* Validate connector configuration
* Escalate ingestion failures

---

## Real Example

Scenario:

Windows Security Events Connector enabled.

User enters wrong password 10 times.

Windows Event ID 4625 generated.

Connector sends logs to Sentinel.

Analytics Rule detects brute force activity.

Alert generated.

Incident created.

SOC Analyst investigates.

---

## Interview Questions

### What is a Data Connector?

A Data Connector is used to collect and ingest logs from various security data sources into Microsoft Sentinel.

---

### Why are Data Connectors important?

Without Data Connectors, Sentinel cannot receive logs, generate alerts, detect threats, or create incidents.

---

### What happens if a connector stops working?

Security logs stop arriving, reducing visibility and potentially causing threats to go undetected.

---

## Evidence Screenshots

Add screenshots later:

* Data Connectors Page
* Windows Security Events Connector
* Connector Configuration
* Connector Connected Status
* Data Ingestion Verification
