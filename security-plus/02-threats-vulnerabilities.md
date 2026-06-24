# Domain 2: Threats, Vulnerabilities & Mitigations (22%)

The biggest domain. Know the attack types and the threat actors.

## Threat actors

| Actor | Motivation / traits |
|-------|--------------------|
| Nation-state | Espionage, well-funded, APT, stealthy |
| Organized crime | Financial gain, ransomware |
| Hacktivist | Ideology / political |
| Insider threat | Employee - malicious or accidental |
| Script kiddie | Low skill, uses existing tools |
| Shadow IT | Unauthorized systems inside an org |

Attributes: internal vs external, resources/funding, sophistication.

## Social engineering

- **Phishing** - fraudulent email. **Spear phishing** = targeted. **Whaling** = execs.
- **Vishing** - voice/phone. **Smishing** - SMS.
- **Pretexting** - inventing a scenario.
- **Pharming** - redirecting to fake site (DNS poisoning).
- **Tailgating / piggybacking** - following someone through a door.
- **Business Email Compromise (BEC)** - impersonating an exec for fraud.
- Principles attackers exploit: **authority, urgency, scarcity, social proof, intimidation, familiarity**.

## Malware types

| Type | Behavior |
|------|----------|
| Virus | Needs a host file, user action to spread |
| Worm | Self-replicating, spreads on its own |
| Trojan | Disguised as legit software |
| RAT | Remote Access Trojan - backdoor control |
| Ransomware | Encrypts data, demands payment |
| Rootkit | Hides deep in OS, hard to detect |
| Keylogger | Records keystrokes |
| Logic bomb | Triggers on a condition/time |
| Spyware / adware | Tracks / shows ads |
| Fileless | Runs in memory, no file on disk |

## Application attacks

- **Injection** - SQLi, command injection (untrusted input run as code).
- **XSS** - inject scripts into web pages viewed by others.
- **CSRF** - trick a logged-in user into an unwanted action.
- **Buffer overflow** - write past a buffer to run code.
- **Privilege escalation** - gain higher rights (vertical/horizontal).
- **Replay attack** - capture and resend valid data.
- **Race condition (TOCTOU)** - time-of-check vs time-of-use gap.

## Network attacks

- **DoS / DDoS** - overwhelm a service.
- **On-path (MITM)** - intercept traffic between two parties.
- **DNS poisoning / ARP poisoning** - corrupt resolution/mapping.
- **Rogue access point / evil twin** - fake Wi-Fi.
- **Deauth attack** - kick Wi-Fi clients off.

## Vulnerability concepts

- **Zero-day** - unknown vuln, no patch yet.
- **CVE** - Common Vulnerabilities and Exposures (the ID list).
- **CVSS** - scoring system (0-10 severity).
- **Misconfiguration** - default creds, open ports, weak settings.
- **Supply chain** - compromise via a vendor/dependency.

## Mitigations

Segmentation, patching, least privilege, hardening, disabling unused services,
encryption, EDR, allow/deny lists, configuration enforcement, monitoring.
