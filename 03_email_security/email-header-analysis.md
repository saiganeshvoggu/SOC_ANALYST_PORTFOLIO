# Email Header Analysis

## Objective
Document how to review email headers during a SOC Analyst email security investigation.

## Tools Used
- Gmail Show Original
- MXToolbox Email Header Analyzer
- Manual header review

## Why Headers Matter
Email headers provide technical evidence about where an email came from, which servers handled it, and whether sender authentication passed.

## Key Fields

| Header Field | Purpose |
|---|---|
| From | Visible sender address |
| Reply-To | Address used when replying |
| Return-Path | Bounce/envelope sender address |
| Received | Mail relay path |
| Received-SPF | SPF result |
| Authentication-Results | SPF, DKIM and DMARC results |
| DKIM-Signature | DKIM signing details |
| Message-ID | Unique message identifier |
| Subject | Email subject |
| Date | Send time |

## Gmail Show Original Workflow
1. Open the email in Gmail.
2. Open the message menu.
3. Click Show original.
4. Review SPF, DKIM and DMARC summary.
5. Copy or download the original header.
6. Paste the header into MXToolbox Email Header Analyzer.
7. Review relay path, source IP, delay and authentication results.

## Authentication Checks

### SPF
Checks whether the sending server is permitted to send mail for the envelope sender domain.

### DKIM
Validates that the message has a valid domain signature and that message integrity is preserved.

### DMARC
Checks domain alignment using SPF and DKIM results and applies the sender domain policy.

## Header Review Checklist
1. Check From address.
2. Check Reply-To address.
3. Review Return-Path.
4. Review SPF result.
5. Review DKIM result.
6. Review DMARC result.
7. Review source IP address.
8. Review relay path.
9. Review delivery delay.
10. Review sender infrastructure.
11. Document final verdict.

## Interview Talking Point
I review email headers by checking From, Reply-To, Return-Path, Received headers, Authentication-Results, SPF, DKIM, DMARC, source IP, relay path and delivery delay. Then I document whether the email appears legitimate or requires further investigation.
