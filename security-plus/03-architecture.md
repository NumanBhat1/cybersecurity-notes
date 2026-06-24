# Domain 3: Security Architecture (18%)

## Network design

- **DMZ / screened subnet** - public-facing servers isolated from internal LAN.
- **Segmentation / VLANs** - separate networks to limit blast radius.
- **Micro-segmentation** - very granular, per-workload (Zero Trust).
- **Air gap** - physically isolated network.
- **East-west vs north-south traffic** - lateral (internal) vs in/out.

## Security devices

| Device | Role |
|--------|------|
| Firewall | Filters traffic by rules |
| NGFW | Adds app awareness, IPS, deep inspection |
| WAF | Protects web apps (layer 7) |
| IDS | Detects (alerts only) |
| IPS | Detects + blocks |
| Proxy | Intermediary; forward (clients) or reverse (servers) |
| Load balancer | Distributes traffic, availability |
| Jump server / bastion | Hardened gateway into a secure zone |

## Cloud concepts

- **IaaS / PaaS / SaaS** - Infrastructure / Platform / Software as a Service.
- **Shared responsibility model** - provider secures the cloud, you secure what's *in* it (more yours in IaaS, less in SaaS).
- **CASB** - Cloud Access Security Broker (policy enforcement between users and cloud).
- **Serverless** - run code without managing servers.

## Resilience & redundancy

- **High availability (HA)** - minimize downtime (clustering, failover).
- **RAID** - disk redundancy (0 = stripe/no redundancy, 1 = mirror, 5 = stripe+parity, 10 = mirror+stripe).
- **Backups** - full, incremental, differential. 3-2-1 rule: 3 copies, 2 media, 1 offsite.
- **RTO** - max acceptable downtime. **RPO** - max acceptable data loss (time).
- **Hot / warm / cold site** - recovery site readiness (hot = ready now, cold = empty space).

## Data concepts

- **Data states** - at rest, in transit, in use.
- **Encryption** protects at rest (full-disk, file) and in transit (TLS).
- **Data classification** - public, internal, confidential, restricted.
- **Tokenization** - replace sensitive data with a token.
- **Masking** - hide part of data (e.g. last 4 of a card).
- **Hashing** - one-way (integrity, not encryption).
