# Event ID 4624 – Successful Logon

## Description

Event ID 4624 indicates that an account successfully authenticated to the system.

## Importance

SOC Analysts use Event ID 4624 to:

* Monitor user logins
* Track authentication activity
* Investigate unauthorized access
* Establish login timelines

## Investigation Steps

1. Open Event Viewer
2. Navigate to:

Windows Logs → Security

3. Filter:

4624

4. Review:

* Account Name
* Logon Type
* Workstation Name
* Source Address
* Time Created

## Lab Findings

A successful authentication event was generated and verified using Event Viewer.

## Detection Use Cases

* Unauthorized logins
* After-hours access
* Suspicious authentication activity
* Account compromise investigations

## Evidence

See:

evidence/windows_event_logs/eventid-4624-successful-logon.png
