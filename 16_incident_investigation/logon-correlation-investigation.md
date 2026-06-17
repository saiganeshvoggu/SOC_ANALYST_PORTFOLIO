# Failed-to-Successful Logon Correlation Investigation

## Status

**Status:** Completed  
**Event IDs:** 4625 and 4624  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Objective

Investigate whether failed logins were followed by successful logons, which may indicate successful password guessing or brute-force compromise.

---

## KQL Query

```kql
SecurityEvent
| where EventID in (4624, 4625)
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Investigation Questions

- Did failed logons occur?
- Did successful logons happen soon after?
- Which account was involved?
- Was the login volume suspicious?
- Was there privilege escalation or persistence after login?

---

## Findings

Both failed and successful logon events were observed:

| Event ID | Description |
|---:|---|
| 4625 | Failed logon |
| 4624 | Successful logon |

A sequence of failed logons followed by successful logons was visible, but the volume and context were consistent with expected lab activity.

---

## Analysis

A failed-to-successful login pattern can be normal when a user mistypes a password and then logs in successfully.

It becomes suspicious when:

- Many failed attempts occur before success
- The same account is targeted repeatedly
- The source is unknown
- Success is followed by PowerShell execution, privilege escalation or persistence

In this lab, no real compromise evidence was identified.

---

## Severity

**Severity:** Low

---

## Classification

**Classification:** Benign authentication activity

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|---|---|
| Credential Access | T1110 Brute Force |
| Initial Access / Persistence | T1078 Valid Accounts |

---

## Closure Notes

Failed and successful logon events were correlated. The activity was expected and lab-generated. Incident closed as benign.
