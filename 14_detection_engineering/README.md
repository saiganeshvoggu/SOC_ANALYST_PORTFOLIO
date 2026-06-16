# Detection Engineering

## Overview

This folder contains SOC detection notes based on Windows Security Events, Microsoft Sentinel and KQL.

The goal is to convert log patterns into clear SIEM monitoring logic for analyst review.

## Use Cases

| Use Case | Data Source | Event IDs | Status |
|---|---|---|---|
| Failed login review | Windows Security Events | 4625 | Planned |
| Successful login review | Windows Security Events | 4624 | Planned |
| Privileged logon review | Windows Security Events | 4672 | Planned |
| Security log cleared review | Windows Security Events | 1102 | Planned |
| New user created review | Windows Security Events | 4720 | Planned |
| Group membership change review | Windows Security Events | 4728, 4732 | Planned |

## Workflow

```text
Collect logs
  -> Write KQL query
  -> Validate results
  -> Document analyst notes
  -> Prepare Sentinel analytics rule
  -> Review alert output
```

## Skills Demonstrated

- KQL query writing
- Windows Event ID analysis
- Microsoft Sentinel analytics rule preparation
- MITRE ATT&CK mapping
- SOC documentation

## Next Steps

- Add failed login review notes
- Add privileged logon review notes
- Add security log cleared review notes
- Add Microsoft Sentinel analytics rule notes
