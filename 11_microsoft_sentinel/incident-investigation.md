# Microsoft Sentinel Incident Investigation Workflow

## Objective
Document a basic SOC Analyst workflow for reviewing incidents in Microsoft Sentinel.

## Workflow

1. Open Microsoft Sentinel.
2. Navigate to Incidents.
3. Review incident title, severity, status, and entities.
4. Identify affected users, hosts, IP addresses, and alerts.
5. Review related logs using KQL.
6. Check timeline and evidence.
7. Map activity to MITRE ATT&CK.
8. Determine if the incident is true positive, false positive, or requires escalation.
9. Document findings and recommended action.
10. Close or escalate the incident.

## Key Fields to Review
- Incident title
- Severity
- Entities
- Alerts
- Tactics and techniques
- Related events
- Timeline
- Owner
- Status

## SOC Analyst Notes
A Sentinel incident groups related alerts and entities. Analysts review incidents to determine impact, affected assets, root cause, and response action.

## Interview Talking Point
When reviewing a Sentinel incident, I check severity, entities, alert details, timeline, related logs, and MITRE mapping. Then I use KQL to validate activity and document whether the incident is a true positive, false positive, or escalation candidate.
