# SOC Incident Report Template

## 1. Incident Summary
Briefly describe what was reported.

Example: A user reported a suspicious email containing a login URL. The URL was investigated using VirusTotal and URLScan.io.

## 2. Alert Source
- User report:
- Email security alert:
- SIEM alert:
- EDR alert:
- Other:

## 3. Investigation Tools Used
- VirusTotal
- URLScan.io
- MXToolbox
- Splunk
- Sysmon

## 4. Initial Observations
- Sender:
- Subject:
- Suspicious URL:
- Attachment:
- Authentication result:

## 5. VirusTotal Findings
- Detection score:
- Registrar:
- Domain age:
- Last analysis date:
- Community comments:
- Related indicators:

## 6. URLScan.io Findings
- Submitted URL:
- Final URL:
- Redirect chain:
- Page title:
- Screenshot observation:
- IP address:
- ASN:
- Organization:
- Contacted domains:
- Suspicious indicators:

## 7. Extracted IOCs

| IOC Type | Value | Source | Notes |
|---|---|---|---|
| URL |  |  |  |
| Domain |  |  |  |
| IP Address |  |  |  |
| ASN |  |  |  |
| Hash |  |  |  |

## 8. Verdict
- Benign / Suspicious / Malicious
- Confidence: Low / Medium / High

## 9. Reasoning
Explain why the verdict was selected using evidence from VirusTotal, URLScan.io, email headers, and SIEM logs.

## 10. Recommended Actions
- Block URL/domain/IP if malicious
- Report phishing email
- Notify affected user
- Search SIEM/proxy/email logs for other hits
- Add IOCs to watchlist
- Preserve evidence

## 11. Interview Takeaway
This report demonstrates phishing triage, threat intelligence enrichment, IOC extraction, and SOC-style documentation.
