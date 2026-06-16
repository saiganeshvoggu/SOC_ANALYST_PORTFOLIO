# SOC Analyst Portfolio — Sai Ganesh Voggu

**SOC Analyst | CompTIA Security+ CE | Microsoft Sentinel | Splunk | Sysmon | KQL | Threat Detection & Incident Response | MSc Data Science — University of Essex**

This repository documents my SOC analyst experience, hands-on security operations labs, SIEM workflows, detection engineering notes, incident response templates, threat hunting exercises, and cybersecurity portfolio projects. The content is built from sanitized, non-confidential examples based on professional experience and personal lab work.

---

## About Me

Cybersecurity professional with hands-on SOC experience triaging **25–55 security alerts daily** across a **2,000+ user enterprise environment** spanning India and the United States. Experienced in endpoint security, DLP operations, Microsoft 365 security, incident response, alert documentation, and security operations support.

- **Role Focus:** SOC Analyst / Cybersecurity Operations Analyst
- **Core Areas:** Alert Triage, Incident Response, DLP, Endpoint Security, Threat Detection, SIEM Monitoring, Security Documentation
- **SIEM & Logging:** Microsoft Sentinel, Splunk Enterprise, Log Analytics Workspace, Windows Event Logs, Sysmon
- **Cloud Security Lab:** Azure Arc, Azure Monitor Agent, Data Collection Rules, Windows Security Events via AMA
- **Tools:** Zoho Service Desk, SentinelOne, Arctic Wolf, Microsoft Purview, Microsoft 365 Security, Exchange Admin Center, Absolute, BitLocker
- **Certifications:** CompTIA Security+ CE, AWS Solutions Architect – Associate, Microsoft SOC Program Foundations
- **Education:** MSc Data Science — University of Essex, United Kingdom
- **Currently Building:** KQL threat hunting, Microsoft Sentinel analytics rules, detection engineering and incident investigation labs

---

## Portfolio Highlights

### Microsoft Sentinel SIEM Lab
- Deployed Microsoft Sentinel on an Azure Log Analytics Workspace.
- Onboarded a Windows 11 endpoint using Azure Arc.
- Installed Azure Monitor Agent through Sentinel workflow.
- Created a Data Collection Rule for Windows Security Events.
- Connected Windows Security Events via AMA.
- Verified log ingestion using Heartbeat and SecurityEvent KQL queries.
- Performed basic KQL hunting for Event IDs, successful logons, privileged logons and event frequency.

### Splunk + Sysmon Lab
- Installed and configured Splunk Enterprise for local security log analysis.
- Installed Sysmon and validated Sysmon Operational logs.
- Ingested Sysmon telemetry into Splunk.
- Investigated process creation activity using Event ID 1.
- Practiced SPL searches, filtering, sorting, field selection and frequency analysis.

### Windows Event Log Analysis
- Investigated key Windows Security Event IDs including 4624, 4625, 4634 and 4672.
- Reviewed process creation audit policy and Windows Security logging behavior.
- Documented analyst notes for logon, failed logon, logoff and special privilege events.

### MITRE ATT&CK Mapping
- Mapped portfolio activity to common MITRE ATT&CK tactics and techniques.
- Covered T1566 Phishing, T1059 Command and Scripting Interpreter, T1003 Credential Dumping and related investigation concepts.

---

## Professional Experience

### Associate SOC Analyst — NB Healthcare Technologies (NationsBenefits India)
**Nov 2022 – Aug 2023**

Supported security operations for a **2,000+ user enterprise environment** across India and the United States.

### Key Contributions

- Triaged and investigated approximately **25–55 security alerts daily** across Zoho Service Desk, SentinelOne, and Arctic Wolf.
- Investigated failed login attempts, endpoint security events, BitLocker recovery requests, DLP incidents, and email quarantine alerts.
- Supported endpoint investigations and security monitoring across India and U.S. user environments.
- Assisted with Data Loss Prevention operations using Microsoft Purview for sensitive data such as SSN, UAN, credit card data, and internal business information.
- Supported Microsoft 365 Security and Exchange Admin Center activities including quarantine management and mobile access controls.
- Used Absolute and SentinelOne for endpoint visibility, compliance checks, device investigations, and security validation.
- Maintained operational tracking sheets for failed login responses, BitLocker recovery devices, DLP cases, and incident documentation.
- Contributed to SOC runbooks and process documents for failed authentication, BitLocker recovery, SEV-C processes, DLP investigations, and quarantine handling.
- Participated in vulnerability review discussions and remediation tracking with Information Security Engineers.
- Escalated approximately **10 security incidents** to Tier-2 analysts and Information Security Engineers for advanced investigation and remediation.

---

## Current Skills

### SIEM & Log Analysis
- Microsoft Sentinel
- Azure Log Analytics Workspace
- Azure Arc-enabled servers
- Azure Monitor Agent
- Data Collection Rules
- Splunk Enterprise
- SPL Query Writing
- KQL Query Writing
- Log Ingestion Validation
- Threat Hunting

### Endpoint Telemetry
- Microsoft Sysmon
- Windows Security Events
- Event ID Analysis
- Parent-Child Process Investigation
- Command-Line Analysis
- Endpoint Investigation

### Email Security
- Email Header Analysis
- SPF
- DKIM
- DMARC
- MXToolbox
- Gmail Show Original
- Phishing Investigation

### Threat Intelligence
- VirusTotal
- URLScan.io
- IOC Extraction
- Domain Reputation Analysis
- MITRE ATT&CK Mapping
- Incident Reporting

### Professional SOC Operations
- Alert triage
- Incident response
- DLP investigation
- Endpoint investigation
- Threat detection
- Vulnerability review support
- Security documentation

---

## Repository Structure

| Folder | Description |
|---|---|
| `01_splunk` | Splunk notes, SPL queries and hunting techniques |
| `02_sysmon` | Sysmon event analysis and endpoint telemetry |
| `03_email_security` | Email investigations and phishing analysis |
| `04_threat_intelligence` | IOC analysis, VirusTotal and URLScan investigations |
| `05_reports` | SOC-style investigation reports |
| `06_sops` | Security procedures and documentation |
| `07_dlp_and_compliance` | DLP investigation workflow and Microsoft Purview notes |
| `08_incident_response` | Incident response playbooks and escalation templates |
| `09_threat_detection` | Threat detection notes mapped to MITRE ATT&CK |
| `10_vulnerability_research` | CVE review and remediation tracking templates |
| `11_mitre_attack` | MITRE ATT&CK tactics, techniques and mapping labs |
| `12_windows_event_logs` | Windows Security Event Log investigations |
| `13_microsoft_sentinel` | Microsoft Sentinel, Azure Arc, AMA, DCR and KQL labs |
| `14_detection_engineering` | Detection logic and analytics rule documentation |
| `evidence` | Screenshots and lab evidence |
| `archive` | Original README content migrated from older repositories |

---

## Learning Roadmap

- Phase 1: Splunk + Sysmon ✅
- Phase 2: Email Security ✅
- Phase 2: Threat Intelligence ✅
- Phase 3: Windows Event Logs ✅
- Phase 4: MITRE ATT&CK ✅
- Phase 5: Microsoft Sentinel Setup ✅
- Phase 6: KQL Fundamentals ✅
- Phase 7: Detection Engineering 🔄
- Phase 8: Incident Investigation & Interview Preparation 🔄

---

## Completed Labs

### Phase 1 - Splunk + Sysmon
- Splunk installation and troubleshooting
- Sysmon installation and verification
- Sysmon Operational logs validation
- Sysmon integration with Splunk
- Event ID 1 process creation investigation
- Parent-child process analysis
- SPL commands: search, table, stats, count, sort, rex, where

### Phase 2 - Email Security
- Email flow and header fundamentals
- SPF, DKIM and DMARC analysis
- Gmail Show Original workflow
- MXToolbox Email Header Analyzer workflow
- Real email header case study

### Phase 2 - Threat Intelligence
- VirusTotal basics
- URLScan.io basics
- IOC extraction
- Domain reputation analysis
- Google domain investigation case study

### Phase 3 - Windows Event Logs
- Event ID 4624 successful logon
- Event ID 4625 failed logon
- Event ID 4634 logoff
- Event ID 4672 special privileges assigned
- Process creation audit policy verification

### Phase 4 - MITRE ATT&CK
- ATT&CK matrix basics
- Tactics and techniques overview
- T1566 phishing
- T1059 command and scripting interpreter
- T1003 OS credential dumping
- Mapping portfolio labs to MITRE ATT&CK

### Phase 5 - Microsoft Sentinel SIEM Lab
- Azure subscription and resource group setup
- Log Analytics Workspace deployment
- Microsoft Sentinel enablement
- Windows Security Events solution installation
- Azure Arc onboarding for Windows endpoint
- Azure Monitor Agent installation
- Data Collection Rule creation
- Windows Security Events via AMA connection
- Heartbeat table verification
- SecurityEvent table verification
- KQL query execution for event hunting

---

## Featured Security Workflows

### Alert Triage
- Review alert source and severity
- Validate user, endpoint, and event context
- Check previous related activity
- Document findings and action taken
- Escalate when required

### Microsoft Sentinel Investigation Workflow
- Validate data connector health
- Confirm ingestion through Heartbeat and SecurityEvent tables
- Identify event IDs and event frequency
- Filter suspicious authentication events
- Map events to MITRE ATT&CK tactics where applicable
- Convert repeated patterns into analytics rules

### Incident Response
- Failed login investigation
- BitLocker recovery handling
- Email quarantine validation
- DLP event review
- Endpoint investigation support

### Documentation
- SOC tracking sheets
- Alert response guides
- Remediation notes
- Escalation summaries
- Runbook drafts

---

## Technical Skills

| Category | Tools & Platforms |
|---|---|
| SIEM | Microsoft Sentinel, Splunk Enterprise, Log Analytics Workspace |
| Cloud Monitoring | Azure Arc, Azure Monitor Agent, Data Collection Rules |
| Query Languages | KQL, SPL |
| Alert Management | Zoho Service Desk, SentinelOne, Arctic Wolf |
| Endpoint Security | SentinelOne, Absolute, BitLocker, Sysmon, Windows Security Events |
| Microsoft Security | Microsoft 365 Security, Microsoft Purview, Exchange Admin Center |
| Identity & Access | MFA, access reviews, failed login investigations, successful logon analysis |
| Threat Detection | MITRE ATT&CK, Windows security events, endpoint alerts, detection logic |
| Vulnerability Support | CVE review, remediation tracking, patch discussion support |
| Documentation | SOPs, runbooks, incident notes, escalation records |
| Threat Intelligence | URLScan.io, VirusTotal, MXToolbox |

---

## Goal

Build practical SOC Analyst skills through hands-on labs, investigations, documentation, and portfolio projects.

---

## Disclaimer

All content in this repository is educational and based on sanitized professional experience, lab work, and publicly available cybersecurity knowledge. No proprietary, confidential, customer, employee, or internal company information is included.