# Analytics Rules

## Overview

Analytics Rules are used in Microsoft Sentinel to detect suspicious activities from collected logs and generate security alerts automatically.

Analytics Rules are one of the most important components in Sentinel because they convert raw log data into actionable security alerts.

---

## Purpose

Analytics Rules help:

* Detect threats automatically
* Generate alerts
* Create incidents
* Reduce manual monitoring
* Improve SOC efficiency

---

## Analytics Rule Workflow

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

## Types of Analytics Rules

### Scheduled Rules

Run KQL queries at scheduled intervals.

Example:

Check failed logins every 5 minutes.

---

### Near Real-Time (NRT)

Runs continuously with very low delay.

Used for:

* Brute force attacks
* Critical security events

---

### Fusion Rules

Microsoft built-in correlation rules.

Correlates multiple alerts into a single incident.

---

### Machine Learning Rules

Uses behavioral analytics and anomaly detection.

Examples:

* Unusual login behavior
* Suspicious user activity

---

## Rule Components

### Query

KQL query used to identify suspicious activity.

### Schedule

Determines how often the query runs.

### Threshold

Minimum number of events required.

### Alert Details

Alert title, description, severity.

### Entity Mapping

Maps users, hosts, IPs and processes.

---

## Example Rule

### Failed Login Detection

KQL Query:

SecurityEvent
| where EventID == 4625

Purpose:

Detect failed login attempts.

Severity:

Medium

Frequency:

Every 5 minutes.

---

## SOC Analyst Responsibilities

* Create detection rules
* Tune false positives
* Review generated alerts
* Validate detections
* Update detection logic

---

## Real Investigation Example

Scenario:

Attacker attempts multiple failed logins.

Event ID:

4625

Analytics Rule:

Failed Login Detection

Result:

Alert generated.

Incident created.

SOC Analyst investigates source IP and target account.

---

## Interview Questions

### What are Analytics Rules?

Analytics Rules are detection mechanisms in Microsoft Sentinel that analyze logs and generate security alerts.

### What is the difference between Alert and Incident?

Alert = Detection

Incident = Collection of related alerts requiring investigation.

### Why are Analytics Rules important?

They automate threat detection and reduce manual monitoring efforts.

---

## Evidence Screenshots

Add screenshots later:

* Analytics Rules Page
* Rule Creation Wizard
* Failed Login Rule
* Generated Alert
* Created Incident
