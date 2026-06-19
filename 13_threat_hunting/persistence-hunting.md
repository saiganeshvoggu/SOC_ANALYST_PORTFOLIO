# Persistence Hunting

## Status

**Status:** Completed  
**Data Source:** `SecurityEvent`  
**Platform:** Microsoft Sentinel / Azure Log Analytics

---

## Objective

Hunt for persistence activity using Windows service installation and scheduled task creation events.

Attackers often create services or scheduled tasks to maintain access after compromise.

---

## Event IDs

| Event ID | Description |
|---:|---|
| 4697 | A service was installed in the system |
| 4698 | A scheduled task was created |
| 7045 | A service was installed in the system, System log |

---

## Hunt Query

```kql
SecurityEvent
| where EventID in (4697, 4698)
| project TimeGenerated, Account, Computer, EventID, Activity
| sort by TimeGenerated desc
```

---

## Hunt Questions

- Was a new service installed?
- Was a scheduled task created?
- Which account created it?
- Was it created during expected admin activity?
- Is the binary path suspicious?

---

## Lab Findings

Both persistence-related events were observed:

- `4697 - A service was installed in the system`
- `4698 - A scheduled task was created`

Observed activity was consistent with controlled lab testing.

---

## Suspicious Indicators

Review service or scheduled task activity when:

- Created by unknown user accounts
- Created outside maintenance windows
- Binary path points to user-writable directories
- Task or service name mimics legitimate software
- Activity is followed by PowerShell, CMD or network connections

Suspicious paths include:

```text
C:\Users\Public\
C:\Temp\
C:\Users\<user>\AppData\Roaming\
C:\Users\<user>\Downloads\
```

---

## MITRE ATT&CK Mapping

| Activity | Technique |
|---|---|
| Windows Service | T1543.003 |
| Scheduled Task | T1053.005 |

---

## Conclusion

Persistence hunting successfully identified service installation and scheduled task creation activity. No real malicious persistence was identified; activity was lab-generated.
