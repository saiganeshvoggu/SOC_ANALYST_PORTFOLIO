# IOC Extraction

## Objective
Learn how to extract Indicators of Compromise from suspicious emails, URLs, domains, IP addresses, files, and threat intelligence tools.

## What is an IOC?
IOC stands for Indicator of Compromise. It is evidence that may indicate malicious or suspicious activity.

## Common IOC Types

| IOC Type | Example | Notes |
|---|---|---|
| URL | hxxps://fake-login[.]com/login | Defanged URL |
| Domain | fake-login[.]com | Defanged domain |
| IP Address | 185.x.x.x | Infrastructure indicator |
| Email Address | support@fake-login.com | Sender or reply-to indicator |
| Hash | SHA256 hash | Malware/file reputation |
| File Name | invoice.pdf.exe | Suspicious attachment |
| ASN | AS15169 | Network ownership/context |

## Defanging
Defanging means making an IOC safe to share in reports.

Example:
Original: https://fake-login.com/login
Defanged: hxxps://fake-login[.]com/login

## IOC Extraction Workflow
1. Start from suspicious email or URL.
2. Extract sender, reply-to, return-path, URLs, domains, IP addresses, attachments, and hashes.
3. Check reputation in VirusTotal.
4. Analyze behavior in URLScan.io.
5. Create an IOC table.
6. Add verdict and recommended actions.
7. Search the SIEM for matching IOCs.

## IOC Table Template

| IOC Type | Value | Source | Notes |
|---|---|---|---|
| URL | hxxps://example[.]com/login | Email body | Suspicious login URL |
| Domain | example[.]com | URL extraction | Possible phishing domain |
| IP Address | x.x.x.x | URLScan | Hosting IP |
| ASN | ASXXXXX | URLScan | Infrastructure ownership |

## SOC Analyst Notes
IOC extraction is important because SOC teams use IOCs to block threats, search logs, identify affected users, and create detection rules.

## Interview Answer
IOC extraction is the process of collecting suspicious indicators such as URLs, domains, IPs, hashes, and email addresses from alerts or investigations. These indicators are used for blocking, threat hunting, and incident response.
