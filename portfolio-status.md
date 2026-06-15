# SOC Analyst Portfolio Status

## Current Repository Status
This repository is structured as a SOC Analyst portfolio with hands-on labs, documentation, workflows, and evidence references.

## Folder Review

| Folder | Status | Notes |
|---|---|---|
| 01_splunk | Complete | Splunk basics, integration notes, and threat hunting queries are documented. Evidence references added. |
| 02_sysmon | Complete | Sysmon basics, Event ID 1 analysis, configuration and schema verification are documented. Evidence references added. |
| 03_email_security | Complete | Email header analysis, SPF, DKIM, DMARC and case study notes are documented. Evidence references added. |
| 04_threat_intelligence | Complete | VirusTotal, URLScan, IOC extraction and Google domain investigation are documented. Evidence references added. |
| 05_reports | Complete | Splunk/Sysmon report and Phase 1 verification report are documented. Evidence references added. |
| 06_sops | Complete | Security SOP section exists and can be expanded later. |
| 07_dlp_and_compliance | Complete | Microsoft Purview DLP operations notes are documented. |
| 08_incident_response | Complete | Incident response playbooks are documented. |
| 09_threat_detection | Complete | MITRE-based threat detection notes are documented. |
| 10_vulnerability_research | Complete | CVE analysis template and vulnerability review notes are documented. |
| 11_mitre_attack | Complete | MITRE basics, lifecycle, technique notes, mapping lab, cheat sheet, SOC use cases and evidence references are documented. |
| 12_windows_event_logs | Complete | Windows Security Event IDs 4624, 4625, 4634 and 4672 are documented. Evidence references added. |
| 13_microsoft_sentinel | Started | Sentinel overview, KQL basics, and incident workflow starter notes are added for the next learning phase. |
| evidence | Ready | Evidence folder structure and screenshot naming plan are documented. |
| archive | Complete | Older migrated content is preserved. |

## Evidence Folder Plan

```text
evidence/
├── splunk/
├── sysmon/
├── email-security/
├── threat-intelligence/
├── reports/
├── windows-event-logs/
└── mitre-attack/
```

## Screenshot Reference Summary

### Splunk
- splunk-dashboard.png
- splunk-data-inputs.png
- splunk-sysmon-search.png
- splunk-eventid1-search.png
- splunk-process-frequency-analysis.png
- splunk-commandline-analysis.png

### Sysmon
- sysmon-service-running-1.png
- sysmon-service-running-2.png
- sysmon-event-viewer-operational.png
- sysmon-eventid1-processcreation-1.png
- sysmon-eventid1-processcreation-2.png
- sysmon-eventid1-processcreation-3.png
- sysmon-config-verification.png
- sysmon-schema-verification.png

### Email Security
- gmail-show-original.png
- mxtoolbox-analysis.png

### Threat Intelligence
- virustotal-google-domain.png
- urlscan-google-domain.png
- ioc-extraction-table.png

### Reports
- incident-report-example.png

### Windows Event Logs
- eventid-4624-successful-logon.png
- eventid-4625-failed-logon.png
- eventid-4634-logoff.png
- eventid-4672-special-privileges.png
- windows-auditpol-process-creation-disabled.png

### MITRE ATT&CK
- mitre-matrix-overview.png
- t1566-phishing.png
- t1059-powershell.png
- t1003-credential-dumping.png
- tactic-initial-access.png
- tactic-execution.png
- tactic-credential-access.png
- tactic-privilege-escalation.png
- mitre-mapping-table.png

## Current Learning Progress

| Area | Status |
|---|---|
| Splunk | Completed |
| Sysmon | Completed |
| Email Security | Completed |
| Threat Intelligence | Completed |
| IOC Extraction | Completed |
| SOC Report Writing | Completed |
| Windows Event Logs | Foundation Completed |
| MITRE ATT&CK | Foundation Completed |
| Microsoft Sentinel | Started |
| KQL | Started |

## Next Learning Phase
Microsoft Sentinel and KQL.

Recommended next folders later:

```text
14_kql_queries/
15_detection_engineering/
16_soc_case_studies/
```
