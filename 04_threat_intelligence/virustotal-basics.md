# VirusTotal Basics

## Objective
Learn how SOC analysts use VirusTotal to perform reputation checks on URLs, domains, IP addresses, files, and hashes.

## Official Link
https://www.virustotal.com/

## What is VirusTotal?
VirusTotal is an open-source threat intelligence and reputation platform. It aggregates detections from many security vendors and provides intelligence about suspicious files, URLs, domains, and IP addresses.

## When SOC Analysts Use It
- Suspicious email URL investigation
- Phishing domain reputation check
- File hash reputation check
- Malware triage
- IP/domain enrichment during incident response

## What Can Be Checked
| Indicator Type | Example | Use Case |
|---|---|---|
| URL | hxxps://fake-login[.]com/login | Phishing investigation |
| Domain | fake-login[.]com | Domain reputation |
| IP Address | 185.x.x.x | Infrastructure investigation |
| File Hash | SHA256 value | Malware/file reputation |
| File Upload | PDF, EXE, DOCM, ZIP | Malware triage |

## How to Use VirusTotal
1. Open https://www.virustotal.com/
2. Select the correct tab: File, URL, Search.
3. Paste the suspicious URL/domain/IP/hash.
4. Review the detection score.
5. Check details such as registrar, domain age, IP, relations, and community comments.
6. Record findings in an incident report.

## Important Fields to Collect
- Detection score
- Security vendor results
- Registrar
- Domain creation date
- Last analysis date
- Community score/comments
- Related URLs/domains/IPs
- File names and hashes if file analysis is involved

## SOC Analyst Notes
A 0 detection result does not always mean safe. Always check context such as domain age, brand impersonation, redirects, suspicious spelling, and related infrastructure.

## Interview Answer
VirusTotal is a threat intelligence platform used to check reputation of URLs, domains, IPs, files, and hashes by aggregating detections from multiple security vendors. In SOC investigations, I use it for initial triage and IOC enrichment.
