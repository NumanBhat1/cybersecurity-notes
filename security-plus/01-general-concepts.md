# Domain 1: General Security Concepts (12%)

## The CIA Triad

- **Confidentiality** - only authorized people can access data (encryption, access control).
- **Integrity** - data isn't altered without authorization (hashing, digital signatures).
- **Availability** - systems/data are accessible when needed (redundancy, backups).

Sometimes extended with **Non-repudiation** (can't deny an action - digital signatures).

## AAA

- **Authentication** - proving who you are.
- **Authorization** - what you're allowed to do.
- **Accounting** - logging what you did.

### Authentication factors

- **Something you know** - password, PIN.
- **Something you have** - token, smart card, phone.
- **Something you are** - biometrics (fingerprint, face).
- **Somewhere you are** - location.
- **Something you do** - behavior (typing pattern).

MFA = two or more *different* factors.

## Control types (by function)

| Type | What it does | Example |
|------|--------------|---------|
| Preventive | Stops it happening | firewall, locks |
| Detective | Finds it after | IDS, logs, CCTV |
| Corrective | Fixes after | backups, patching |
| Deterrent | Discourages | warning signs |
| Compensating | Alternative control | extra monitoring when a fix isn't possible |
| Directive | Tells people what to do | policy |

## Control categories

- **Technical** (logical) - firewalls, encryption, MFA.
- **Managerial** (administrative) - policies, risk assessments.
- **Operational** - day-to-day human processes (awareness training, guards).
- **Physical** - fences, locks, badges.

## Zero Trust

"Never trust, always verify." No implicit trust based on network location.
Key ideas: verify every request, least privilege, micro-segmentation,
continuous authentication. Split into a **control plane** (policy decisions) and
**data plane** (enforcement).

## Important concepts

- **Gap analysis** - compare current state vs. desired state.
- **Defense in depth** - layered controls.
- **Honeypot / honeynet** - decoy systems to lure/study attackers.
- **Deception tech** - honeytokens, fake files to detect intrusion.
