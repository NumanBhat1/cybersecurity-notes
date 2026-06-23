# MITRE ATT&CK: Basics

What the framework is and why SOC analysts use it.

## What it is

**MITRE ATT&CK** is a public knowledge base of real-world attacker behavior,
organized as a matrix of **Tactics** (the *why* - attacker goals) and
**Techniques** (the *how* - specific methods). It gives defenders a shared
vocabulary for describing attacks.

Site: https://attack.mitre.org

## Tactics (the columns / attacker goals)

In rough order of an attack:

1. **Reconnaissance** - gathering info about the target
2. **Resource Development** - setting up infrastructure
3. **Initial Access** - getting in (phishing, exposed service)
4. **Execution** - running malicious code
5. **Persistence** - keeping access (new accounts, scheduled tasks)
6. **Privilege Escalation** - gaining higher permissions
7. **Defense Evasion** - avoiding detection (clearing logs)
8. **Credential Access** - stealing passwords/hashes
9. **Discovery** - exploring the environment
10. **Lateral Movement** - moving to other hosts
11. **Collection** - gathering target data
12. **Command and Control (C2)** - remote control channel
13. **Exfiltration** - stealing data out
14. **Impact** - destruction, ransomware, disruption

## Techniques (examples)

| ID | Technique | Tactic |
|----|-----------|--------|
| T1110 | Brute Force | Credential Access |
| T1059.001 | PowerShell | Execution |
| T1136 | Create Account | Persistence |
| T1046 | Network Service Discovery | Discovery |
| T1078 | Valid Accounts | Initial Access / Persistence |
| T1486 | Data Encrypted for Impact (ransomware) | Impact |
| T1070 | Indicator Removal (e.g. clear logs) | Defense Evasion |

## Why SOC analysts use it

- **Tagging detections** - mapping an alert to a technique (e.g. "this is T1110")
  makes reports clear and consistent.
- **Coverage gaps** - the matrix shows which attacker behaviors you can and can't
  detect.
- **Threat hunting** - pick a technique and go look for evidence of it.
- **Communication** - everyone on the team knows what "T1059.001" means.

## SOC takeaway

When you write up an investigation or build a detection, mapping it to an ATT&CK
technique instantly makes it look professional and helps the whole team reason
about coverage. It's a small habit with a big payoff.
