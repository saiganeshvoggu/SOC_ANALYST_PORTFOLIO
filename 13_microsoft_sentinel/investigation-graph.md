# Investigation Graph

## Overview

Investigation Graph is a visual investigation tool in Microsoft Sentinel that helps analysts understand relationships between entities involved in an incident.

It provides a graphical representation of users, hosts, IP addresses, processes, URLs, and alerts.

---

## Purpose

Investigation Graph helps analysts:

* Understand attack paths
* Identify affected assets
* Visualize relationships
* Accelerate investigations
* Determine root cause

---

## Common Entities

### User

Affected account.

Example:

sai.ganesh

---

### Host

Affected endpoint.

Example:

DESKTOP-01

---

### IP Address

Source or destination IP.

Example:

192.168.1.25

---

### Process

Executed application.

Example:

powershell.exe

---

### URL

Visited or malicious URL.

Example:

example.com

---

## Investigation Workflow

Incident

↓

Entities

↓

Relationships

↓

Timeline

↓

Root Cause Analysis

↓

Response

---

## Real Example

Incident:

Suspicious PowerShell Activity

Entities:

User

↓

Host

↓

PowerShell Process

↓

External IP

Investigation reveals suspicious script execution.

---

## Benefits

* Faster investigations
* Better visibility
* Simplified analysis
* Improved threat understanding

---

## SOC Analyst Responsibilities

* Review entities
* Trace relationships
* Identify suspicious activity
* Validate alerts
* Document findings

---

## Interview Questions

### What is Investigation Graph?

A visual investigation tool used to analyze relationships between entities involved in an incident.

### Why is it useful?

It helps analysts quickly understand attack paths and affected assets.

### What entities can appear?

Users, hosts, IP addresses, URLs, processes, alerts, and incidents.

---

## Evidence Screenshots

Add screenshots later:

* Investigation Graph View
* Entity Relationship View
* Host Analysis
* User Analysis
