# Google Domain Investigation

## Objective
Investigate google.com using VirusTotal and URLScan.io and document the findings in SOC analyst format.

## Investigation Date
June 2026

## Tools Used
- VirusTotal
- URLScan.io

## VirusTotal Findings

| Field | Finding |
|---|---|
| Target | google.com |
| Detection Score | 0/91 |
| Verdict | Clean |
| Registrar | MarkMonitor Inc. |
| Domain Age | 29 years |
| Last Analysis | 28 minutes before screenshot |
| Community Score | 707 |

## VirusTotal Analysis
The domain showed 0 detections from 91 vendors. The domain is very old, has a trusted registrar, and has strong positive community reputation. No malicious indicators were observed in the submitted screenshot.

## URLScan.io Findings

| Field | Finding |
|---|---|
| Submitted URL | https://google.com |
| Final URL | https://www.google.com/ |
| IP Address | 142.251.151.119 |
| ASN | AS15169 |
| Organization | Google LLC |
| Country | United States |
| Page Title | Google |
| Requests | 47 |
| Domains Contacted | 2 |
| IPs Contacted | 5 |
| HTTPS | 100% |

## URLScan.io Analysis
The URL redirected to the expected Google destination. The infrastructure belongs to Google LLC under AS15169. HTTPS was used and no suspicious redirects or suspicious contacted domains were observed.

## Extracted IOCs

| IOC Type | Value | Source | Notes |
|---|---|---|---|
| Domain | google.com | VirusTotal / URLScan | Benign domain |
| URL | https://google.com | URLScan | Submitted URL |
| Final URL | https://www.google.com/ | URLScan | Expected redirect |
| IP Address | 142.251.151.119 | URLScan | Google infrastructure |
| ASN | AS15169 | URLScan | Google LLC |
| Organization | Google LLC | URLScan | Legitimate infrastructure |

## Verdict
Benign

## Confidence
High

## Reason
The domain has 0/91 detections in VirusTotal, is 29 years old, uses Google-owned infrastructure, redirects to the expected final URL, and shows no suspicious behavior in URLScan.io.

## Recommended Action
No action required.

## Evidence

Screenshots should be uploaded under:

```text
evidence/threat-intelligence/
```

Expected evidence:

- virustotal-google-domain.png
- urlscan-google-domain.png
- ioc-extraction-table.png

## Interview Takeaway
This investigation demonstrates the ability to perform safe URL/domain reputation analysis, review website behavior, extract IOCs, and document a SOC-style verdict.
