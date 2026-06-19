# Microsoft Sentinel Setup Lab

## Objective

Document a hands-on Microsoft Sentinel lab for Windows security event monitoring.

## Environment

| Item | Value |
|---|---|
| SIEM | Microsoft Sentinel |
| Workspace | `soc-workspaces` |
| Resource Group | `soc-lab-rg` |
| Region | Central India |
| Machine | Windows 11 |
| Connector | Windows Security Events via AMA |
| Data Rule | `soc-windows-security-events-dcr` |

## Completed Work

- Created Azure resource group.
- Created Log Analytics Workspace.
- Enabled Microsoft Sentinel.
- Installed Windows Security Events solution from Content Hub.
- Connected Windows machine using Azure Arc.
- Installed Azure Connected Machine Agent.
- Created Data Collection Rule.
- Connected Windows Security Events via AMA.
- Verified data using `Heartbeat` table.
- Verified Windows events using `SecurityEvent` table.

## Architecture

```text
Windows 11
  -> Azure Arc
  -> Azure Monitor Agent
  -> Data Collection Rule
  -> Log Analytics Workspace
  -> Microsoft Sentinel
```

## SOC Analyst Value

This lab demonstrates SIEM setup, endpoint log onboarding, connector validation, KQL basics, and Windows security event monitoring.
