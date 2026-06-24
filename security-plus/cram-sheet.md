# Security+ Cram Sheet (SY0-701)

One-page, high-yield review. The stuff most likely to show up. Skim this right
before the exam.

## Must-memorize formulas

- **SLE = Asset Value x Exposure Factor**
- **ALE = SLE x ARO** (ARO = times per year)
- **Risk = Likelihood x Impact**

## CIA + extras

Confidentiality, Integrity, Availability. Add **Non-repudiation** (can't deny -
digital signatures) and **Authentication**.

## AAA

Authentication (who you are) -> Authorization (what you can do) -> Accounting (what you did).

## Auth factors (MFA = 2+ different ones)

Know / Have / Are / Where you are / What you do.

## Control TYPES (function)

Preventive, Detective, Corrective, Deterrent, Compensating, Directive.

## Control CATEGORIES

Technical, Managerial, Operational, Physical.

## Ports (highest-yield)

| Port | Service | | Port | Service |
|------|---------|---|------|---------|
| 22 | SSH/SFTP | | 443 | HTTPS |
| 23 | Telnet (insecure) | | 445 | SMB |
| 25 | SMTP | | 636 | LDAPS |
| 53 | DNS | | 993 | IMAPS |
| 80 | HTTP | | 995 | POP3S |
| 88 | Kerberos | | 3389 | RDP |
| 389 | LDAP | | 161 | SNMP |

Insecure -> Secure: Telnet->SSH, FTP->SFTP, HTTP->HTTPS, LDAP->LDAPS, SNMPv1/2->v3.

## Crypto quick hits

- **Symmetric** (one key, fast): AES, 3DES.
- **Asymmetric** (key pair): RSA, ECC.
- **Hashing** (one-way, integrity): SHA-256, MD5 (weak).
- **PKI**: CA issues certs; CRL/OCSP check revocation; CSR requests a cert.
- **TLS** secures data in transit. **Salting** defeats rainbow tables.

## Malware one-liners

Virus (needs host) - Worm (self-spreads) - Trojan (disguised) - RAT (backdoor) -
Ransomware (encrypts) - Rootkit (hides) - Logic bomb (triggers) - Fileless (memory only).

## Social engineering

Phishing (email), Spear (targeted), Whaling (execs), Vishing (voice), Smishing (SMS),
Pretexting, Tailgating. Levers: authority, urgency, scarcity, fear, familiarity.

## Attacks to know

SQLi, XSS, CSRF, buffer overflow, privilege escalation, replay, on-path (MITM),
DoS/DDoS, DNS/ARP poisoning, evil twin, zero-day.

## Incident Response (in order)

Preparation -> Detection & Analysis -> Containment -> Eradication -> Recovery -> Lessons Learned.

## Forensics

Order of volatility (RAM first, disk later). Chain of custody. Hash evidence. Legal hold.

## BC/DR

- **RTO** = max downtime tolerated. **RPO** = max data loss (time) tolerated.
- Sites: **Hot** (ready now) / **Warm** / **Cold** (empty).
- Backups: full, incremental, differential. 3-2-1 rule.

## Risk responses

Accept, Avoid, Transfer, Mitigate.

## Frameworks / compliance

PCI DSS (cards), HIPAA (health), GDPR (EU privacy), SOC 2, ISO 27001, NIST CSF/800-53.

## Zero Trust

Never trust, always verify. Least privilege, micro-segmentation, continuous auth.
Control plane (decisions) + data plane (enforcement).

## Acronyms people blank on

SIEM (log collection/correlation), SOAR (automated response), DLP (data loss prevention),
EDR/XDR (endpoint detection), PAM (privileged access mgmt), CASB (cloud broker),
NAC (network access control), WAF (web app firewall), IDS/IPS (detect/prevent).
