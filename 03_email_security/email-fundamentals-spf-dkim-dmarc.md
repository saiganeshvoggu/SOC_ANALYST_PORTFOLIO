# Email Fundamentals, SPF, DKIM and DMARC

## Phase 2 - Phishing Investigation and SOC Alert Triage

## Objective
Understand how email works and how SOC analysts investigate phishing emails using email authentication technologies and header analysis.

## Email Flow
Sender -> Mail Server -> Internet -> Recipient Mail Server -> Inbox

SOC analysts investigate whether an email is legitimate, spoofed, malicious, or part of a phishing campaign.

## Main Email Components

### Header
Contains technical metadata such as:
- Source IP
- Sender information
- Mail transfer path
- SPF result
- DKIM result
- DMARC result
- Message identifiers

### Body
The actual email content shown to the user.

### Attachments
Files included in the email such as PDF files, Office documents, ZIP archives, or executables.

## What is Phishing?
Phishing is a social engineering attack where attackers attempt to trick users into revealing credentials, downloading malware, or performing unauthorized actions.

## Common Phishing Types
- Generic Phishing
- Spear Phishing
- Whaling
- Business Email Compromise

## SPF - Sender Policy Framework
SPF verifies whether the sending mail server is authorized to send email for a domain.

Analyst question: Is the sending server authorized?

## DKIM - DomainKeys Identified Mail
DKIM verifies email integrity using a cryptographic signature.

Analyst question: Was the email modified in transit?

## DMARC - Domain-based Message Authentication, Reporting and Conformance
DMARC applies domain policy based on SPF and DKIM validation.

Common policies:
- none
- quarantine
- reject

## SOC Investigation Questions
1. Who sent the email?
2. Is the sender domain legitimate?
3. Did SPF pass?
4. Did DKIM pass?
5. Did DMARC pass?
6. Does the email contain suspicious URLs?
7. Does the email contain suspicious attachments?
8. Is the message requesting credentials, money, or urgent action?

## Common Investigation Tools
- VirusTotal
- URLScan
- AbuseIPDB
- Google Message Header Analyzer
- MXToolbox

## Interview Question
What is the difference between SPF, DKIM, and DMARC?

Answer: SPF validates the sending server. DKIM validates message integrity. DMARC applies policy decisions based on SPF and DKIM results.

## Skills Demonstrated
- Email security fundamentals
- Phishing investigation basics
- Email authentication concepts
- SOC alert triage preparation
- Security operations documentation
