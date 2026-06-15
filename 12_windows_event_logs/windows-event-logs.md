# Windows Event Logs

## Overview

Windows Event Logs are a primary source of security telemetry used by SOC Analysts to investigate authentication activity, account changes, privilege assignments, system events, and suspicious behavior.

This lab focuses on Windows Security Logs commonly monitored during security investigations.

## Event IDs Covered

* Event ID 4624 – Successful Logon
* Event ID 4625 – Failed Logon
* Event ID 4634 – Logoff
* Event ID 4672 – Special Privileges Assigned

## Investigation Objectives

* Understand Windows authentication events
* Identify successful and failed login activity
* Detect potential brute-force attacks
* Monitor privileged account activity
* Build foundational SOC investigation skills

## Tools Used

* Event Viewer
* Windows Security Logs
* Sysmon
* Splunk

## Skills Demonstrated

* Event Filtering
* Event Analysis
* Authentication Monitoring
* Privilege Monitoring
* Security Investigation Workflow
* Windows Log Analysis

## Evidence

Screenshots are stored under:

evidence/windows_event_logs/

## Conclusion

Windows Security Logs provide critical visibility into authentication and privilege-related activity. Understanding these events is essential for SOC Analysts performing detection, investigation, and incident response activities.
