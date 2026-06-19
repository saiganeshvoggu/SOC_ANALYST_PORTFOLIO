# SOC Analyst Technical Interview Answers

## 1. What detections have you built?

I built multiple Microsoft Sentinel detections using Windows Security Events and KQL. These included failed login detection using Event ID 4625, successful logon review using Event ID 4624, privileged logon detection using Event ID 4672, PowerShell execution review using Event ID 4688, service installation detection using Event ID 4697, scheduled task creation detection using Event ID 4698, user account creation detection using Event ID 4720, group membership change detection using Event ID 4732 and Security log clearing detection using Event ID 1102.

---

## 2. How do you investigate failed login activity?

I start by reviewing Event ID 4625 in the SecurityEvent table. I identify the affected account, host, time range and number of failed attempts. Then I check whether there was a successful login after the failures using Event ID 4624. I also review privileged logons, PowerShell activity and persistence events to determine whether the failed login activity led to compromise.

---

## 3. How do you investigate PowerShell execution?

I review Event ID 4688 for PowerShell process creation. I check the account, host, parent process and command line when available. I also review PowerShell Operational logs such as 4103 and 4104 when available. If PowerShell was launched by Office, a browser, script host or an unusual process, I treat it as more suspicious and correlate with other events.

---

## 4. How do you detect persistence?

I look for service installation events and scheduled task creation events. On Windows, Event ID 4697 indicates a service was installed and Event ID 4698 indicates a scheduled task was created. I also review System log Event ID 7045 for service creation when System logs are collected. I check who created it, when, on which host and whether the binary path is suspicious.

---

## 5. Why is Event ID 1102 important?

Event ID 1102 means the Windows Security audit log was cleared. In production, this is important because attackers may clear logs to hide evidence after compromise. I would immediately review related authentication, PowerShell, privilege and persistence events before the log clearing event.

---

## 6. What is threat hunting?

Threat hunting is proactive searching for suspicious activity even when no alert has fired. Instead of only responding to alerts, a threat hunter forms a hypothesis, selects data sources, writes queries and reviews patterns across accounts, hosts and timestamps.

---

## 7. What is the difference between detection engineering and threat hunting?

Detection engineering focuses on building alert logic that can automatically identify suspicious behavior. Threat hunting is proactive investigation where an analyst searches for suspicious activity without waiting for an alert.

---

## 8. How do you decide severity?

Severity depends on impact, confidence and context. A single failed login may be informational or low. A successful login after many failures may be medium or high. Unauthorized admin group membership, suspicious service creation or Security log clearing may be high. Confirmed malware, ransomware or domain compromise would be critical.
