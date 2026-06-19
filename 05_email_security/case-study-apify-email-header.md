# Case Study - Email Header Analysis

## Case Summary
A legitimate marketing email was reviewed using Gmail Show Original and MXToolbox Email Header Analyzer.

## Investigation Goal
Determine whether the sender authentication and routing details were consistent with a legitimate sender.

## Tools Used
- Gmail Show Original
- MXToolbox Email Header Analyzer
- Manual header review

## Authentication Results

| Check | Result |
|---|---|
| SPF | PASS |
| DKIM | PASS |
| DMARC | PASS |

## Header Areas Reviewed
- From address
- Reply-To address
- Return-Path
- Received headers
- Authentication-Results
- DKIM-Signature
- Message-ID
- Delivery delay
- Mail relay path

## Final Verdict
Classification: Legitimate email

Risk Level: Low

## Reasoning
- SPF passed.
- DKIM passed.
- DMARC passed.
- Sender domain aligned with authentication results.
- Relay information showed normal delivery behavior.
- No suspicious routing indicators were observed.

## Skills Practiced
- Gmail Show Original usage
- MXToolbox Email Header Analyzer usage
- SPF review
- DKIM review
- DMARC review
- Return-Path review
- Relay path review
- SOC-style final verdict writing

## Interview Talking Point
I analyzed a real email header using Gmail Show Original and MXToolbox. I reviewed SPF, DKIM, DMARC, Return-Path, relay path and delivery delay, then documented a final verdict based on authentication and routing evidence.
