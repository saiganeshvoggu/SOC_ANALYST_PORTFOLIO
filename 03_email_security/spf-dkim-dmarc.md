# SPF, DKIM and DMARC Notes

## Objective
Understand the three major email authentication checks used during email security investigations.

## SPF - Sender Policy Framework
SPF verifies whether the sending mail server is allowed to send email for the envelope sender domain.

SOC Analyst Question: Is this sending IP permitted by the sender domain?

Example Result: SPF PASS

## DKIM - DomainKeys Identified Mail
DKIM uses a digital signature to validate that the message was signed by the sender domain and was not changed in transit.

SOC Analyst Question: Is the domain signature valid?

Example Result: DKIM PASS

## DMARC - Domain-based Message Authentication, Reporting and Conformance
DMARC uses SPF and DKIM alignment to validate whether the visible From domain is authenticated.

SOC Analyst Question: Does the visible sender domain align with authentication results?

Example Result: DMARC PASS

## Simple Difference

| Control | What It Checks |
|---|---|
| SPF | Sending server authorization |
| DKIM | Message signature and integrity |
| DMARC | Domain alignment and policy |

## Strong Interview Answer
SPF validates whether the sending server is authorized. DKIM validates message integrity using a domain signature. DMARC checks alignment between the visible From domain and SPF/DKIM results, then applies the sender domain policy.
