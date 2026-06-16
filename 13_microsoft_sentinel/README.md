# Microsoft Sentinel SIEM Lab

## Overview

This folder documents a hands-on Microsoft Sentinel SIEM lab focused on cloud SIEM deployment, endpoint onboarding, Windows Security Event ingestion, KQL querying, and SOC investigation workflows.

Microsoft Sentinel is a cloud-native SIEM and SOAR platform used by SOC teams to collect logs, create analytics rules, investigate incidents, run hunting queries, automate response actions, and build dashboards.

---

## Lab Status

**Status:** Hands-on setup completed

The Microsoft Sentinel lab has been configured with Windows endpoint log ingestion using Azure Arc, Azure Monitor Agent, Data Collection Rules, and Windows Security Events via AMA.

---

## Completed Components

- Azure subscription verified
- Resource group created: `soc-lab-rg`
- Log Analytics Workspace created: `soc-workspaces`
- Microsoft Sentinel enabled on workspace
- Windows Security Events solution installed from Content Hub
- Local Windows 11 endpoint onboarded using Azure Arc
- Azure Connected Machine Agent installed successfully
- Azure Monitor Agent enabled
- Data Collection Rule created: `soc-windows-security-events-dcr`
- Windows Security Events via AMA connected
- Heartbeat table verified
- SecurityEvent table verified
- Basic KQL queries executed successfully

---

## Architecture

```text
Windows 11 Endpoint
        ↓
Azure Arc
        ↓
Azure Monitor Agent (AMA)
        ↓
Data Collection Rule (DCR)
        ↓
Log Analytics Workspace
        ↓
Microsoft Sentinel
        ↓
KQL Hunting / Analytics Rules / Incidents
```

---

## SOC Analyst Skills Demonstrated

- Microsoft Sentinel workspace setup
- Azure Log Analytics configuration
- Azure Arc endpoint onboarding
- Azure Monitor Agent deployment
- Data Collection Rule creation
- Windows Security Event ingestion
- KQL query execution
- Event ID analysis
- Log ingestion validation
- SIEM troubleshooting
- Threat hunting preparation
- Detection engineering foundation

---

## Key Tables Used

| Table | Purpose |
|---|---|
| `Heartbeat` | Confirms endpoint and agent connectivity |
| `SecurityEvent` | Stores Windows Security Event logs |

---

## Important Windows Event IDs Observed

| Event ID | Meaning |
|---|---|
| 4624 | Successful logon |
| 4625 | Failed logon |
| 4672 | Special privileges assigned to new logon |
| 5058 | Key file operation |
| 5061 | Cryptographic operation |
| 5379 | Credential Manager credentials were read |
| 4798 | Local user group membership enumerated |

---

## Evidence Screenshots

Screenshots for this lab should be stored under the repository evidence folder, preferably using a structure like:

```text
evidence/
└── microsoft-sentinel/
    ├── sentinel-enabled.png
    ├── azure-arc-machine-connected.png
    ├── dcr-created.png
    ├── windows-security-events-connected.png
    ├── heartbeat-query-results.png
    └── securityevent-query-results.png
```

---

## Files in This Folder

| File | Purpose |
|---|---|
| `sentinel-overview.md` | Microsoft Sentinel overview and SOC relevance |
| `log-analytics-workspace.md` | Log Analytics Workspace setup notes |
| `data-connectors.md` | Data connector concepts and Windows Security Events via AMA |
| `kql-basics.md` | KQL fundamentals |
| `kql-soc-queries.md` | SOC-focused KQL queries |
| `analytics-rules.md` | Sentinel analytics rule notes |
| `incident-management.md` | Incident handling workflow |
| `incident-investigation.md` | Incident investigation process |
| `workbooks.md` | Dashboard and workbook notes |
| `automation-rules.md` | Automation rule basics |
| `investigation-graph.md` | Investigation graph notes |
| `sentinel-case-study.md` | End-to-end lab case study |
| `sentinel-interview-questions.md` | Interview preparation notes |

---

## Next Learning Phase

- Failed login detection
- Brute-force detection logic
- Privileged logon monitoring
- Security log cleared detection
- Custom analytics rules
- Incident generation
- MITRE ATT&CK mapping for Sentinel detections
