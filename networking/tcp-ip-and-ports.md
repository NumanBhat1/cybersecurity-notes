# Networking: TCP/IP, Ports & Protocols

Notes on the networking fundamentals a SOC analyst uses every day.

## The TCP three-way handshake

How a TCP connection is established before any data is sent:

1. **SYN** - client -> server: "I want to talk, here's my sequence number."
2. **SYN-ACK** - server -> client: "OK, here's mine, and I acknowledge yours."
3. **ACK** - client -> server: "Acknowledged. Connection open."

Connection teardown uses **FIN / ACK**. A **RST** means "reset / refused" - often
seen when a port is closed.

Why it matters: scanning tools (nmap) and packet captures (Wireshark) show these
flags. Spotting lots of SYNs with no follow-up can indicate a SYN scan or flood.

## Common ports to know

| Port | Protocol | Notes |
|------|----------|-------|
| 20/21 | FTP | File transfer, clear text. Anonymous login is a risk. |
| 22 | SSH | Encrypted remote login. Replaced telnet. |
| 23 | Telnet | Remote login, **clear text** - insecure. |
| 25 | SMTP | Email sending. |
| 53 | DNS | Name resolution (UDP mostly, TCP for large/zone transfers). |
| 80 | HTTP | Web, unencrypted. |
| 110 | POP3 | Email retrieval. |
| 143 | IMAP | Email retrieval. |
| 161/162 | SNMP | Network device management. |
| 389 | LDAP | Directory services (e.g. Active Directory). |
| 443 | HTTPS | Web over TLS. |
| 445 | SMB | Windows file sharing. Common attack target. |
| 3389 | RDP | Windows remote desktop. Common brute-force target. |
| 3306 | MySQL | Database. |
| 6379 | Redis | In-memory DB; insecure if exposed without auth. |

## TCP vs UDP

- **TCP** - connection-oriented, reliable, ordered (handshake, retransmits). Web,
  email, SSH.
- **UDP** - connectionless, fast, no guarantee. DNS, streaming, some VoIP.

## OSI model (quick recall)

1. Physical 2. Data Link 3. Network 4. Transport 5. Session 6. Presentation 7. Application

Mnemonic: **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way.

## Key address concepts

- **Private ranges** (RFC 1918): `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`.
- **CIDR**: `/24` = 256 addresses (255.255.255.0). `/16` = 65,536.
- **NAT**: maps private internal IPs to a public one.
- **Loopback**: `127.0.0.1`.

## SOC takeaway

When you read a log or a packet capture, you're constantly asking: which IPs,
which ports, which protocol, and does this match normal behavior? Knowing the
common ports cold lets you spot the odd one out instantly.
