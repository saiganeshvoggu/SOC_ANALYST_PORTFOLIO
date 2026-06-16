# Incident Management

## Overview

Incident Management is the process of reviewing, investigating, documenting, escalating, and resolving security incidents in Microsoft Sentinel.

Incidents are the primary objects investigated by SOC Analysts.

---

## Alert vs Incident

### Alert

A single security detection.

Example:

Failed Login Detection

---

### Incident

A collection of related alerts grouped together for investigation.

Example:

Failed Logins

*

Successful Login

*

Administrative Access

↓

Possible Account Compromise

---

## Incident Lifecycle

New

↓

Active

↓

Investigating

↓

Resolved

↓

Closed

---

## Incident Components

### Title

Incident name.

Example:

Possible Brute Force Attack

---

### Severity

* Informational
* Low
* Medium
* High

---

### Status

* New
* Active
* Closed

---

### Owner

Assigned analyst.

---

### Entities

* Users
* Hosts
* IP Addresses
* URLs
* Processes

---

### Alerts

Related security detections.

---

## Investigation Process

### Step 1

Review incident title.

### Step 2

Review severity.

### Step 3

Review related alerts.

### Step 4

Review affected entities.

### Step 5

Review timeline.

### Step 6

Determine root cause.

### Step 7

Document findings.

### Step 8

Close or escalate.

---

## Real SOC Example

Incident:

Possible Brute Force Attack

Alerts:

* Event ID 4625
* Event ID 4625
* Event ID 4625

Affected User:

Administrator

Source IP:

192.168.1.25

Outcome:

Escalated for investigation.

---

## SOC Analyst Responsibilities

* Triage incidents
* Investigate alerts
* Validate threats
* Escalate when required
* Document findings
* Close incidents

---

## Interview Questions

### What is an Incident?

An Incident is a collection of related alerts requiring investigation.

### What is the first thing you review?

Severity, alerts, entities, and timeline.

### What is incident ownership?

Assignment of an incident to a responsible analyst.

---

## Evidence Screenshots

Add screenshots later:

* Incidents Page
* Incident Details
* Incident Timeline
* Incident Closure
