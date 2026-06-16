# Automation Rules

## Overview

Automation Rules in Microsoft Sentinel are used to automatically perform actions when alerts or incidents are generated.

They help SOC teams reduce manual effort and improve response times.

---

## Purpose

Automation Rules help:

* Reduce analyst workload
* Standardize response actions
* Improve incident handling
* Accelerate investigations
* Automate repetitive tasks

---

## Automation Workflow

Alert Generated

↓

Incident Created

↓

Automation Rule Triggered

↓

Action Executed

---

## Common Actions

### Assign Incident

Automatically assign incidents to a SOC analyst.

Example:

High Severity Incident

↓

Assign Tier-1 Analyst

---

### Change Severity

Automatically increase or decrease severity.

Example:

Critical Threat Intelligence Match

↓

Change Severity to High

---

### Add Tags

Automatically categorize incidents.

Examples:

* Phishing
* Malware
* Brute Force
* Suspicious Login

---

### Change Status

Update incident status automatically.

Examples:

* New
* Active
* Closed

---

### Trigger Playbook

Launch a Logic App workflow.

Example:

Malicious IP Detected

↓

Trigger Response Playbook

↓

Block IP

---

## Benefits

* Faster response
* Consistent handling
* Reduced manual work
* Improved SOC efficiency
* Better incident tracking

---

## Real SOC Example

Scenario:

Five failed logins detected.

Analytics Rule creates incident.

Automation Rule adds:

Tag: Brute Force

Severity: Medium

Owner: Tier-1 Analyst

---

## SOC Analyst Responsibilities

* Configure automation rules
* Validate automation actions
* Monitor failures
* Review automated decisions
* Update workflows when needed

---

## Interview Questions

### What are Automation Rules?

Automation Rules automatically perform actions on alerts and incidents based on predefined conditions.

### Why are Automation Rules important?

They reduce manual work and improve response speed.

### Can Automation Rules close incidents?

Yes, they can update status, severity, ownership, tags and trigger playbooks.

---

## Evidence Screenshots

Add screenshots later:

* Automation Rules Page
* Automation Rule Creation
* Automation Rule Trigger
* Incident Updated Automatically
