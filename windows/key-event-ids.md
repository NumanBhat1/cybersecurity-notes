# Windows: Key Security Event IDs

The Windows Event Log IDs a SOC analyst should recognize on sight. Found in
**Event Viewer -> Windows Logs -> Security** (and Sysmon under Applications and
Services Logs).

## Authentication & logon

| Event ID | Meaning | Why it matters |
|----------|---------|----------------|
| 4624 | Successful logon | Baseline of normal access; check Logon Type |
| 4625 | Failed logon | Bursts = brute force / password spraying |
| 4634 | Logoff | Session ended |
| 4648 | Logon with explicit credentials | "Run as" - possible lateral movement |
| 4768 | Kerberos TGT requested | AD authentication start |
| 4769 | Kerberos service ticket requested | Used in Kerberoasting attacks |
| 4771 | Kerberos pre-auth failed | Failed AD logon |

### Logon Types (field inside 4624/4625)

| Type | Meaning |
|------|---------|
| 2 | Interactive (at the keyboard) |
| 3 | Network (e.g. accessing a share) |
| 4 | Batch (scheduled task) |
| 5 | Service |
| 10 | RemoteInteractive (RDP) |

## Account & group changes

| Event ID | Meaning |
|----------|---------|
| 4720 | A user account was created |
| 4722 | A user account was enabled |
| 4724 | Password reset attempt |
| 4728 / 4732 | Member added to a security group (global / local) |
| 4740 | Account locked out |
| 4756 | Member added to a universal group |

New admin account + group add (4720 + 4732) in quick succession is a classic
persistence signal.

## Process & system

| Event ID | Source | Meaning |
|----------|--------|---------|
| 4688 | Security | New process created (enable command-line logging for full value) |
| 1 | Sysmon | Process creation (with hashes + full command line) |
| 3 | Sysmon | Network connection by a process |
| 7 | Sysmon | Image/DLL loaded |
| 11 | Sysmon | File created |
| 1102 | Security | **Audit log was cleared** - big red flag (anti-forensics) |

## SOC takeaway

A huge amount of Windows detection comes down to watching the right Event IDs:
4625 for brute force, 4720/4732 for new admins, 4688/Sysmon 1 for suspicious
processes, and 1102 for someone covering their tracks. Memorizing this short list
pays off in interviews and on the job.
