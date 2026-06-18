# SOC Severity Classification Guide

## Purpose

This guide provides a simple severity model for SOC case management and alert triage.

---

## Informational

### Examples

- Single failed login
- Expected system activity
- Known administrative action

### Action

- Document
- Close if expected

---

## Low

### Examples

- Small number of failed logins
- Expected PowerShell from known tools
- Lab-generated activity

### Action

- Review context
- Document findings
- Close if benign

---

## Medium

### Examples

- Multiple failed logins from same account
- PowerShell from unusual parent process
- New service or scheduled task from admin account during unusual time

### Action

- Investigate related events
- Notify relevant team if required
- Monitor for recurrence

---

## High

### Examples

- Unexpected user added to Administrators group
- Suspicious service or scheduled task creation
- Successful login after many failed attempts
- Security log cleared without approval

### Action

- Escalate to Tier 2
- Recommend containment if needed
- Preserve evidence

---

## Critical

### Examples

- Confirmed malware execution
- Ransomware behavior
- Domain administrator compromise
- Data exfiltration
- Multiple impacted hosts

### Action

- Emergency escalation
- Incident Response team engagement
- Containment and recovery process

---

## Key Rule

Severity depends on context. The same event may be Low in a lab, Medium during approved admin activity, or High/Critical when unexpected in production.
