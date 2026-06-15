# Event ID 4625 – Failed Logon

## Description

Event ID 4625 is generated when an authentication attempt fails.

## Importance

SOC Analysts frequently investigate Event ID 4625 because it can indicate:

* Incorrect passwords
* Brute-force attacks
* Password spraying
* Credential abuse attempts

## Investigation Steps

1. Open Event Viewer
2. Navigate to:

Windows Logs → Security

3. Filter:

4625

4. Review:

* Account Name
* Failure Reason
* Source Address
* Workstation Name
* Time Created

## Lab Findings

A failed authentication event was generated and verified during testing.

## Detection Use Cases

* Brute-force detection
* Password spraying detection
* Suspicious authentication attempts

## Evidence

See:

evidence/windows_event_logs/eventid-4625-failed-logon.png
