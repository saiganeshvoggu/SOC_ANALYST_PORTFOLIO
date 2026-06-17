# Failed Login Incident Investigation

## Status

**Status:** Completed  
**Event ID:** 4625  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Alert Summary

Multiple failed login attempts were observed on the endpoint.

| Field | Value |
|---|---|
| Event ID | 4625 |
| Activity | An account failed to log on |
| Host | SaiGaneshVoggu |
| Time Range | Last 24 hours |

---

## KQL Evidence Query

```kql
SecurityEvent
| where EventID == 4625
| project TimeGenerated, Account, Computer, Activity
| sort by TimeGenerated desc
```

---

## Failed Attempt Count Query

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count() by Account
| sort by FailedAttempts desc
```

---

## Findings

Observed failed login counts:

| Account | Failed Attempts |
|---|---:|
| `-\\-` | 17 |
| `SAIGANESHVOGGU\\test` | 2 |
| `SAIGANESHVOGGU\\Administrator` | 2 |

Total failed attempts observed: **21**

---

## Analysis

The failed logins were low-volume and consistent with lab-generated authentication testing.

The `-\\-` account value indicates failed authentication activity where Windows did not resolve a valid account name. This can happen with invalid username attempts, local authentication failures or background authentication attempts.

The Administrator and test account failures were expected due to controlled lab activity.

---

## Brute Force Check

A brute force investigation should look for:

- High failed login volume
- Multiple failures against one account
- Failures followed by successful login
- Multiple source hosts or IPs
- Account lockouts

In this lab, failed login volume was low and did not indicate real brute-force activity.

---

## Severity

**Severity:** Informational / Low

---

## Classification

**Classification:** Benign lab-generated authentication activity

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|---|---|
| Credential Access | T1110 Brute Force |

---

## Closure Notes

No real malicious authentication behavior was identified. Activity was consistent with controlled lab testing. Incident closed as benign.
