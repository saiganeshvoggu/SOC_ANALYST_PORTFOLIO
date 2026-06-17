# Failed Login Detection Lab

## Lab Status

**Status:** Completed  
**Phase:** Detection Engineering  
**Platform:** Microsoft Sentinel / Azure Log Analytics  
**Data Source:** Windows Security Events via Azure Monitor Agent  
**Primary Event ID:** 4625  
**Detection Type:** Brute-force style failed login detection

---

## Objective

Build and validate a detection for multiple failed login attempts using Windows Security Event ID 4625 in Microsoft Sentinel.

This lab demonstrates how Windows authentication failures can be collected from an endpoint, ingested into Microsoft Sentinel, queried using KQL, and converted into detection logic for brute-force or password-guessing activity.

---

## Tools and Components Used

- Microsoft Sentinel
- Azure Log Analytics Workspace
- Azure Arc-enabled Windows endpoint
- Azure Monitor Agent
- Data Collection Rule
- Windows Event Viewer
- Windows Security Logs
- KQL

---

## MITRE ATT&CK Mapping

| Tactic | Technique | Technique ID |
|---|---|---|
| Credential Access | Brute Force | T1110 |
| Credential Access | Password Guessing | T1110.001 |
| Credential Access | Password Spraying | T1110.003 |

---

## Event Details

| Field | Value |
|---|---|
| Windows Event ID | 4625 |
| Event Meaning | An account failed to log on |
| Channel | Security |
| Logon Type Observed | 2 - Interactive |
| Example Account Observed | SAIGANESHVOGGU\\test |
| Example Computer Observed | SaiGaneshVoggu |

---

## Lab Steps Performed

1. Generated failed login attempts on the Windows endpoint.
2. Verified Event ID 4625 in Windows Event Viewer.
3. Confirmed that Windows Security Events were ingested into Microsoft Sentinel.
4. Queried failed login events using KQL.
5. Counted failed login attempts by account and computer.
6. Built threshold-based detection logic for repeated failed logins.
7. Validated that the detection returned results when the threshold was met.

---

## Verification Query

```kql
SecurityEvent
| where EventID == 4625
| sort by TimeGenerated desc
```

### Purpose

This query confirms that failed login events are available in the `SecurityEvent` table.

---

## Failed Attempt Count Query

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count()
by Account, Computer
```

### Result Observed

The query successfully counted failed login attempts for the test account and endpoint.

Example result:

| Account | Computer | FailedAttempts |
|---|---|---|
| SAIGANESHVOGGU\\test | SaiGaneshVoggu | 2 |
| -\\- | SaiGaneshVoggu | 7 |

---

## Final Detection Query

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count()
by Account, Computer, bin(TimeGenerated, 5m)
| where FailedAttempts >= 5
```

---

## Detection Logic

Trigger when:

- Event ID equals `4625`
- Failed login attempts are grouped by account and computer
- Failed attempts are counted inside a 5-minute time window
- Failed attempts are greater than or equal to 5

Detection meaning:

```text
5 or more failed login attempts within 5 minutes = Potential brute-force or password-guessing activity
```

---

## Detection Result

The detection logic successfully returned threshold-matching results.

Observed result:

| Time Window | Computer | FailedAttempts |
|---|---|---|
| 17/06/2026 08:40 UTC | SaiGaneshVoggu | 7 |
| 17/06/2026 08:50 UTC | SaiGaneshVoggu | 5 |

This confirms that the detection successfully identified repeated failed login activity.

---

## SOC Analyst Investigation Notes

When this detection triggers, an analyst should review:

- Target account
- Target computer
- Number of failed attempts
- Time window of activity
- Logon type
- Source IP address, when available
- Whether a successful login occurred after the failed attempts
- Whether the same source attempted multiple accounts
- Whether the account is privileged or sensitive

---

## Possible Alert Classification

| Condition | Classification |
|---|---|
| Failed attempts only, no success | Suspicious authentication activity |
| Failed attempts followed by successful login | Possible account compromise |
| Same source against many users | Possible password spraying |
| Many attempts against one user | Possible brute force |

---

## False Positive Considerations

Possible benign causes:

- User forgot password
- Cached credentials
- Recently changed password
- Mapped drive or service using old credentials
- Typing mistakes during login
- Lab-generated test activity

---

## Recommended Severity

**Medium**

Reason:

Repeated failed login attempts may indicate brute-force activity, but severity should increase if followed by a successful login, privileged account activity, or external source IP involvement.

---

## Interview Talking Point

Built and validated a failed-login brute-force detection in Microsoft Sentinel using KQL. The detection monitored Windows Security Event ID 4625 and identified accounts with five or more failed login attempts within a five-minute window.

---

## Lab Outcome

**Completed successfully.**

This lab validates practical detection engineering skills using Windows Security Events, Microsoft Sentinel, Azure Arc, AMA, DCR, and KQL.
