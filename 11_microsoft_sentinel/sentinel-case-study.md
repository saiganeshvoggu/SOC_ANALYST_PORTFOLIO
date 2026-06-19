# Microsoft Sentinel Case Study

## Case Title

Multiple Failed Login Investigation

---

## Objective

Investigate repeated failed login attempts detected by Microsoft Sentinel.

---

## Detection Source

Windows Security Events

---

## Event ID

4625

Failed Logon

---

## Analytics Rule

Failed Login Detection Rule

---

## Alert Generated

Possible Brute Force Activity

Severity: Medium

---

## Incident Created

Possible Brute Force Attack

---

## Investigation Steps

### Step 1

Review incident details.

---

### Step 2

Review affected user.

Example:

administrator

---

### Step 3

Review source IP.

Example:

192.168.1.50

---

### Step 4

Review timeline.

Observed:

10 failed logins within 5 minutes.

---

### Step 5

Check for successful login activity.

Result:

No successful login detected.

---

### Step 6

Review additional alerts.

No related malware activity identified.

---

## MITRE ATT&CK Mapping

Technique:

T1110

Brute Force

Tactic:

Credential Access

---

## Findings

Repeated failed login attempts observed against a privileged account from a single source IP address.

Behavior is consistent with brute force activity.

---

## Verdict

Suspicious Activity

Potential Brute Force Attempt

---

## Recommended Actions

* Block source IP
* Reset password if necessary
* Enable MFA
* Continue monitoring

---

## Lessons Learned

* Analytics Rules successfully detected suspicious behavior.
* Incident management workflow worked as expected.
* Investigation identified probable brute force activity.

---

## Evidence Screenshots

Add screenshots later:

* Alert Generated
* Incident Created
* Investigation Timeline
* Final Incident Report
