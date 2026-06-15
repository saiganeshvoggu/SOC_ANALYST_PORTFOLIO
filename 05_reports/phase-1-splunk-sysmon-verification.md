# Phase 1 Verification Report - Splunk + Sysmon

## Objective
Verify that Splunk and Sysmon were installed, integrated, and used for basic SOC Analyst threat hunting.

## Phase 1 Status
Completed and verified.

## Splunk Verification

| Check | Status |
|---|---|
| Splunk Enterprise opened locally | Verified |
| Search & Reporting app accessible | Verified |
| Sysmon logs visible in Splunk | Verified |
| Sysmon sourcetype searchable | Verified |
| Raw XML Sysmon events searchable | Verified |
| Event ID 1 process creation searchable | Verified |
| rex field extraction tested | Verified |
| stats count by tested | Verified |
| table command tested | Verified |
| sort command tested | Verified |
| Targeted command-line search tested | Verified |

## Sysmon Verification

| Check | Status |
|---|---|
| Sysmon Operational log found in Event Viewer | Verified |
| Sysmon Event ID 1 visible | Verified |
| Process Create events visible | Verified |
| CommandLine field reviewed | Verified |
| ParentImage field reviewed | Verified |
| ParentCommandLine field reviewed | Verified |
| User field reviewed | Verified |
| Hashes field reviewed | Verified |
| Sysmon64 service running | Verified |
| Startup type automatic | Verified |
| Sysmon configuration checked using sysmon64 -c | Verified |
| Sysmon schema checked using sysmon64 -s | Verified |

## Key Finding
Sysmon logs were ingested into Splunk as raw XML. Because of this, direct EventCode searching did not always return results. The working method was raw XML search and field extraction using rex.

## Skills Demonstrated
- SIEM access and navigation
- Splunk Search & Reporting
- Sysmon endpoint telemetry verification
- Raw XML event analysis
- SPL field extraction using rex
- Process creation hunting
- Command-line analysis
- Parent-child process analysis
- Troubleshooting failed SPL searches
- SOC documentation

## Resume Bullet
Configured and verified Microsoft Sysmon log ingestion into Splunk, analyzed raw XML Sysmon Event ID 1 process creation logs, extracted Image and CommandLine fields using SPL rex, and built practical threat hunting searches using search, table, stats, count, and sort.

## Final Phase 1 Result
Splunk + Sysmon integration and basic threat hunting foundation completed and verified.
