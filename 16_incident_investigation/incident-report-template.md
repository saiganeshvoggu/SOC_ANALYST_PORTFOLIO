# SOC Incident Report Template

## Incident Summary

**Incident Title:**  
**Date:**  
**Analyst:**  
**Severity:**  
**Status:**  
**Classification:**  

---

## Alert Details

| Field | Value |
|---|---|
| Alert Source | Microsoft Sentinel / Log Analytics |
| Data Source | SecurityEvent |
| Event ID |  |
| Host |  |
| Account |  |
| Time Range |  |

---

## Initial Triage

- What triggered the investigation?
- Which account was involved?
- Which endpoint was involved?
- Was this expected or unexpected activity?

---

## Evidence Collected

```kql
// Paste investigation query here
```

### Key Observations

- Observation 1:
- Observation 2:
- Observation 3:

---

## Timeline

| Time | Event | Notes |
|---|---|---|
|  |  |  |

---

## Investigation Analysis

Document:

- Event meaning
- Related activity
- Possible root cause
- Whether activity is benign, suspicious or malicious
- False positive considerations

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|---|---|
|  |  |

---

## Impact Assessment

- Affected host:
- Affected account:
- Business impact:
- Data impact:
- Lateral movement observed: Yes / No
- Persistence observed: Yes / No

---

## Severity Classification

**Severity:** Informational / Low / Medium / High / Critical

Reason:

---

## Containment / Remediation

Actions taken or recommended:

- Reset password if needed
- Disable suspicious account if needed
- Isolate endpoint if needed
- Remove unauthorized persistence if needed
- Preserve logs and evidence
- Escalate to Tier 2 if needed

---

## Closure Notes

**Final Classification:**  
**Root Cause:**  
**Status:** Closed / Escalated / Monitoring  

Summary:
