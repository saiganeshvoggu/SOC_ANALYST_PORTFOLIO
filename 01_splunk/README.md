# Splunk SIEM Lab

## Purpose

This folder documents Splunk learning, local SIEM setup, search practice, log ingestion and SOC-style investigation notes.

## Skills Covered

- Splunk installation and navigation
- Index and source type validation
- Basic SPL query writing
- Log ingestion validation
- Event frequency review
- Search filtering and field selection

## Example Queries

```spl
index=main
```

```spl
index=main
| table _time host source sourcetype
| sort - _time
```

## SOC Analyst Value

Splunk is widely used in SOC environments for alert triage, log review, event correlation and threat hunting. This lab demonstrates hands-on SIEM fundamentals.
