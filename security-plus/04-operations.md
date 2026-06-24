# Domain 4: Security Operations (28%)

The largest domain - this is the SOC-analyst work, so it's directly relevant.

## Identity & access management

- **Provisioning / deprovisioning** - create/remove accounts (offboard fast!).
- **Least privilege** - only the access needed.
- **Separation of duties** - no single person controls a whole sensitive process.
- **Privileged Access Management (PAM)** - control/monitor admin accounts.
- **Federation** - use one identity across orgs (SAML, OIDC).
- **SSO** - one login, many apps. **MFA** - multiple factors.

## Hardening

- Disable unused services/ports, change default creds, patch, apply baselines.
- **Endpoint hardening** - EDR, host firewall, disk encryption.
- **Group Policy (Windows)** - enforce settings across a domain.
- **Allow list vs deny list** - allow only approved (safer) vs block known-bad.

## Monitoring & SIEM

- **SIEM** - collects + correlates logs, alerts on patterns.
- **SOAR** - automates response (playbooks).
- **Log sources** - firewall, IDS/IPS, OS, application, authentication.
- **Alerting & tuning** - reduce false positives.
- **NetFlow** - traffic metadata for analysis.

## Vulnerability management

- **Scanning** - credentialed vs non-credentialed; authenticated scans see more.
- **CVSS** - severity score. **CVE** - the vuln ID.
- **False positive / false negative** - scanner wrong in either direction.
- **Remediation** - patch, mitigate, or accept the risk.
- **Pen testing** - authorized simulated attack (black/gray/white box).

## Incident Response (IR) lifecycle

1. **Preparation** - tools, plans, training.
2. **Detection & analysis** - identify and scope the incident.
3. **Containment** - stop the spread (short/long-term).
4. **Eradication** - remove the threat.
5. **Recovery** - restore systems.
6. **Lessons learned** - post-incident review.

## Digital forensics

- **Order of volatility** - capture most volatile first (RAM/cache before disk).
- **Chain of custody** - documented handling of evidence.
- **Legal hold** - preserve data for litigation.
- **Hashing evidence** - prove it wasn't altered.

## Automation

Scripting repetitive tasks, SOAR playbooks, infrastructure as code. Benefits:
speed, consistency, scale. Risks: complexity, single point of failure.
