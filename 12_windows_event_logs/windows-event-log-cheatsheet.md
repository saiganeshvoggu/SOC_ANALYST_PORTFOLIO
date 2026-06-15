# Windows Security Event Log Cheat Sheet

| Event ID | Description                 |
| -------- | --------------------------- |
| 4624     | Successful Logon            |
| 4625     | Failed Logon                |
| 4634     | Logoff                      |
| 4672     | Special Privileges Assigned |
| 4688     | Process Creation            |
| 4720     | User Account Created        |
| 4726     | User Account Deleted        |
| 4732     | User Added To Group         |
| 4740     | Account Locked Out          |
| 1102     | Audit Log Cleared           |

## SOC Analyst Focus

Most commonly investigated:

* 4624
* 4625
* 4672
* 4688
* 4740
* 1102

These events are frequently used during authentication, privilege escalation, and incident response investigations.
