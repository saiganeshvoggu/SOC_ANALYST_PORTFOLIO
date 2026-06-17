# SOC Analyst Portfolio — Sai Ganesh Voggu

**SOC Analyst | CompTIA Security+ CE | Microsoft Sentinel | Splunk | Sysmon | KQL | Threat Detection & Incident Response | MSc Data Science — University of Essex**

This repository documents my SOC analyst experience, hands-on security operations labs, SIEM workflows, detection engineering notes, threat hunting exercises, incident investigation workflows, incident response templates, and cybersecurity portfolio projects. The content is built from sanitized, non-confidential examples based on professional experience and personal lab work.

---

## About Me

Cybersecurity professional with hands-on SOC experience triaging **25–55 security alerts daily** across a **2,000+ user enterprise environment** spanning India and the United States. Experienced in endpoint security, DLP operations, Microsoft 365 security, incident response, alert documentation, and security operations support.

- **Role Focus:** SOC Analyst / Cybersecurity Operations Analyst
- **Core Areas:** Alert Triage, Incident Investigation, Incident Response, DLP, Endpoint Security, Threat Detection, SIEM Monitoring, Security Documentation
- **SIEM & Logging:** Microsoft Sentinel, Splunk Enterprise, Log Analytics Workspace, Windows Event Logs, Sysmon
- **Cloud Security Lab:** Azure Arc, Azure Monitor Agent, Data Collection Rules, Windows Security Events via AMA
- **Tools:** Zoho Service Desk, SentinelOne, Arctic Wolf, Microsoft Purview, Microsoft 365 Security, Exchange Admin Center, Absolute, BitLocker
- **Certifications:** CompTIA Security+ CE, AWS Solutions Architect – Associate, Microsoft SOC Program Foundations
- **Education:** MSc Data Science — University of Essex, United Kingdom
- **Currently Building:** SOC case management templates, interview preparation notes, and recruiter-ready SOC portfolio documentation

---

## Portfolio Highlights

### Incident Investigation Phase
- Completed SOC-style incident investigations using Microsoft Sentinel, Azure Log Analytics, Windows Security Events and KQL.
- Investigated failed login activity using Event ID 4625 and reviewed failed attempt counts by account.
- Correlated failed and successful logons using Event IDs 4625 and 4624.
- Investigated PowerShell execution using Event ID 4688 and reviewed parent process context.
- Investigated persistence activity using Event IDs 4697 and 4698.
- Investigated Security log clearing using Event ID 1102.
- Documented severity, classification, evidence, MITRE ATT&CK mapping and closure notes.

### Threat Hunting Phase
- Completed proactive threat hunting labs using Microsoft Sentinel, Azure Log Analytics, Windows Security Events and KQL.
- Hunted authentication activity using Event IDs 4624, 4625 and 4672.
- Hunted PowerShell execution using Event ID 4688 and reviewed parent process context.
- Hunted persistence activity using Event IDs 4697 and 4698.
- Hunted defense evasion activity using Event ID 1102 for Security log clearing.
- Produced a threat hunting report covering findings, risk assessment, recommendations and MITRE ATT&CK mapping.

### Detection Engineering Phase
- Built and validated detection logic using Microsoft Sentinel, Azure Log Analytics, Windows Security Events, Event Viewer and KQL.
- Created detections for failed logons, successful logons, brute-force patterns, privileged logons, user creation, group membership changes, process creation, PowerShell execution, service installation, scheduled task creation and security log clearing.
- Enabled and validated Windows audit policies for process creation, service installation, scheduled task creation and related security events.
- Practiced KQL logic using `where`, `project`, `sort by`, `summarize`, `count()`, `countif()`, `maxif()` and time-window based detection logic.
- Mapped detections to MITRE ATT&CK techniques including T1110, T1059.001, T1136, T1098, T1543.003, T1053.005 and T1070.001.

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
- Investigated key Windows Security Event IDs including 4624, 4625, 4672, 4688, 4697, 4698, 4720, 4732 and 1102.
- Reviewed process creation audit policy and Windows Security logging behavior.
- Documented analyst notes for logon, failed logon, privilege activity, account creation and persistence events.

### MITRE ATT&CK Mapping
- Mapped portfolio activity to common MITRE ATT&CK tactics and techniques.
- Covered brute force, valid accounts, PowerShell execution, account creation, account manipulation, Windows service persistence, scheduled task persistence and event log clearing.

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
- Incident Investigation

### Incident Investigation
- Failed login investigation
- Failed-to-successful logon correlation
- PowerShell execution investigation
- Parent-child process review
- Persistence investigation
- Security log clearing investigation
- Severity classification
- SOC closure notes
- MITRE ATT&CK mapping

### Threat Hunting
- Authentication hunting
- Failed and successful logon analysis
- Privileged logon hunting
- PowerShell execution hunting
- Persistence hunting
- Defense evasion hunting
- MITRE ATT&CK-based hunt documentation
- Threat hunting report writing

### Detection Engineering
- Windows Security Event ID detection
- Microsoft Sentinel KQL detection logic
- Threshold-based alert logic
- Correlation-based detection
- Brute-force detection
- Privileged logon detection
- Account creation detection
- Group membership change detection
- Process creation monitoring
- PowerShell execution detection
- Persistence detection
- Security log clearing detection
- MITRE ATT&CK mapping
- False positive analysis

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
| `14_detection_engineering` | Detection engineering labs, KQL rules and analyst notes |
| `15_threat_hunting` | Threat hunting labs, hunt queries and report documentation |
| `16_incident_investigation` | SOC incident investigation labs, evidence review and report template |
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
- Phase 7: Detection Engineering ✅
- Phase 8: Threat Hunting ✅
- Phase 9: Incident Investigation ✅
- Phase 10: SOC Case Management 🔄
- Phase 11: Interview Preparation 🔄

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

### Phase 7 - Detection Engineering
- Failed login detection using Windows Security Event ID 4625
- Successful logon review using Windows Security Event ID 4624
- Brute-force success correlation using Event IDs 4625 and 4624
- User account creation detection using Event ID 4720
- Local group membership change detection using Event ID 4732
- Privileged logon detection using Event ID 4672
- Process creation detection using Event ID 4688
- PowerShell execution review using Event IDs 4103, 4104 and 4688
- Encoded PowerShell execution simulation and detection logic
- Service installation detection using Event ID 4697
- Scheduled task creation detection using Event ID 4698
- Security log cleared detection using Event ID 1102
- Service Control Manager service installation review using Event ID 7045
- MITRE ATT&CK mapping and false positive notes

### Phase 8 - Threat Hunting
- Authentication hunting using Event IDs 4624, 4625 and 4672
- PowerShell hunting using Event ID 4688
- Persistence hunting using Event IDs 4697 and 4698
- Privilege escalation hunting using Event ID 4672
- Defense evasion hunting using Event ID 1102
- Threat hunting report with findings, risk assessment, recommendations and MITRE ATT&CK mapping

### Phase 9 - Incident Investigation
- Failed login incident investigation using Event ID 4625
- Failed-to-successful logon correlation using Event IDs 4625 and 4624
- PowerShell execution investigation using Event ID 4688
- Persistence investigation using Event IDs 4697 and 4698
- Security log cleared investigation using Event ID 1102
- Incident report template covering evidence, timeline, impact, severity and closure notes

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

### Detection Engineering Workflow
- Identify event source and Event ID
- Generate controlled test activity
- Validate event locally in Event Viewer
- Validate SIEM ingestion in Microsoft Sentinel
- Build KQL detection logic
- Review false positives
- Map to MITRE ATT&CK
- Document analyst notes

### Threat Hunting Workflow
- Define hunt hypothesis
- Select relevant data source
- Write KQL hunt query
- Review accounts, hosts, timestamps and event patterns
- Identify suspicious behavior or confirm benign activity
- Map findings to MITRE ATT&CK
- Document hunt results and recommendations

### Incident Investigation Workflow
- Review the alert or event
- Collect supporting evidence using KQL
- Build a timeline
- Correlate authentication, execution, persistence and defense evasion activity
- Assign severity
- Determine root cause and classification
- Document closure notes or escalation path

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
| Threat Detection | MITRE ATT&CK, Windows security events, endpoint alerts, detection logic, Microsoft Sentinel detections |
| Detection Engineering | KQL detections, authentication correlation, PowerShell detection, persistence detection, log tampering detection |
| Threat Hunting | Authentication hunting, PowerShell hunting, persistence hunting, defense evasion hunting, hunt reporting |
| Incident Investigation | Alert triage, evidence collection, timeline review, severity classification, closure notes |
| Vulnerability Support | CVE review, remediation tracking, patch discussion support |
| Documentation | SOPs, runbooks, incident notes, escalation records |
| Threat Intelligence | URLScan.io, VirusTotal, MXToolbox |

---

## Goal

Build practical SOC Analyst skills through hands-on labs, investigations, documentation, and portfolio projects.

---

## Disclaimer

All content in this repository is educational and based on sanitized professional experience, lab work, and publicly available cybersecurity knowledge. No proprietary, confidential, customer, employee, or internal company information is included.
