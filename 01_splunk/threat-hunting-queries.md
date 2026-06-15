# Splunk Threat Hunting Queries

## Objective
Maintain practical SPL query notes for SOC Analyst investigations using Windows and Sysmon telemetry.

## Query Areas Covered

### 1. Base Sysmon Search
Used to validate that Sysmon logs are available in Splunk.

### 2. Recent Process Creation Events
Used to review recently executed processes and identify unusual execution patterns.

### 3. PowerShell Activity
Used to review PowerShell execution and command-line context.

### 4. Encoded Command Review
Used to identify obfuscated or unusual command-line patterns.

### 5. Living-off-the-Land Binary Review
Used to review legitimate Windows binaries that may require analyst attention when executed with unusual parameters.

### 6. Office Parent-Child Process Review
Used to identify Office applications launching script interpreters or shells.

### 7. Network Connections from Processes
Used to review outbound connections and identify unexpected process-to-network behavior.

### 8. DNS Query Review
Used to investigate suspicious domain lookups and phishing/malware callback domains.

### 9. Count Processes by Image
Used to identify frequently executed processes and baseline endpoint activity.

### 10. Suspicious Download Command Review
Used to identify command-line based file retrieval activity.

## Evidence

Screenshots should be uploaded under:

```text
evidence/splunk/
```

Expected evidence:

- splunk-dashboard.png
- splunk-data-inputs.png
- splunk-sysmon-search.png
- splunk-eventid1-search.png
- splunk-process-frequency-analysis.png
- splunk-commandline-analysis.png

## Resume Impact
These queries demonstrate hands-on experience with SIEM searching, endpoint telemetry, suspicious process detection, and SOC investigation workflows.
