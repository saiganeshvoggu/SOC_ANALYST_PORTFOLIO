# Authentication Hunting

## Status

**Status:** Completed  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Objective

Identify suspicious authentication patterns by hunting failed logons, successful logons and privileged logons.

---

## Event IDs

| Event ID | Description |
|---:|---|
| 4625 | An account failed to log on |
| 4624 | An account was successfully logged on |
| 4672 | Special privileges assigned to new logon |

---

## Hunt 1 - Top Failed Login Accounts

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count() by Account
| sort by FailedAttempts desc
```

### Hunt Question

Which accounts have the highest number of failed login attempts?

### Lab Findings

Observed failed login activity for lab-created and local accounts. Activity was consistent with controlled testing.

---

## Hunt 2 - Top Successful Login Accounts

```kql
SecurityEvent
| where EventID == 4624
| summarize SuccessfulLogins=count() by Account
| sort by SuccessfulLogins desc
```

### Hunt Question

Which accounts have the highest number of successful logons?

### Lab Findings

High counts were observed for expected system and user accounts such as `NT AUTHORITY\\SYSTEM`, Microsoft account login activity and service accounts.

---

## Hunt 3 - Privileged Logon Activity

```kql
SecurityEvent
| where EventID == 4672
| summarize PrivilegedLogons=count() by Account
| sort by PrivilegedLogons desc
```

### Hunt Question

Which accounts are receiving special privileges during logon?

### Lab Findings

Privileged logon activity was observed for expected accounts such as SYSTEM and the lab user account.

---

## Analyst Notes

Authentication hunting should review:

- Repeated failed logons
- Failed logons followed by successful logons
- Admin or privileged account usage
- Unusual accounts
- Unusual times
- Unexpected hosts

---

## MITRE ATT&CK Mapping

| Activity | Technique |
|---|---|
| Failed logins | T1110 Brute Force |
| Successful logons | T1078 Valid Accounts |
| Privileged access usage | Privilege escalation review |

---

## Conclusion

Authentication events were visible in Microsoft Sentinel. The observed activity was consistent with lab testing and expected system behavior. No real malicious authentication pattern was identified.
