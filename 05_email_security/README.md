# Email Security Investigation

## Purpose

This folder documents email security fundamentals, phishing investigation workflow, header analysis and authentication checks.

## Skills Covered

- Email header review
- SPF, DKIM and DMARC validation
- Sender and domain verification
- URL and attachment review workflow
- MXToolbox usage
- Phishing triage documentation

## Analyst Workflow

```text
Review sender
  -> Review subject and body
  -> Check headers
  -> Validate SPF, DKIM and DMARC
  -> Extract URLs and indicators
  -> Check reputation sources
  -> Document verdict
```

## SOC Analyst Value

Email security is a core SOC responsibility. This section demonstrates phishing triage, authentication checks and safe documentation practices.
