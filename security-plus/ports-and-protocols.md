# Ports & Protocols (Security+)

Security+ expects you to know common ports and which are secure vs. insecure.

## Must-know ports

| Port | Protocol | Secure? | Notes |
|------|----------|---------|-------|
| 20/21 | FTP | No (clear text) | Use FTPS/SFTP instead |
| 22 | SSH / SFTP / SCP | Yes | Encrypted remote admin + file transfer |
| 23 | Telnet | No (clear text) | Replaced by SSH |
| 25 | SMTP | No by default | Email send; 587 for submission |
| 53 | DNS | - | Name resolution; DNSSEC adds integrity |
| 67/68 | DHCP | - | IP address assignment |
| 69 | TFTP | No | Trivial FTP, no auth |
| 80 | HTTP | No | Use HTTPS (443) |
| 88 | Kerberos | Yes | AD authentication |
| 110 | POP3 | No | 995 = POP3S (secure) |
| 123 | NTP | - | Time sync |
| 143 | IMAP | No | 993 = IMAPS (secure) |
| 161/162 | SNMP | v3 is secure | Network management |
| 389 | LDAP | No | 636 = LDAPS (secure) |
| 443 | HTTPS | Yes | HTTP over TLS |
| 445 | SMB | - | Windows file sharing; common attack target |
| 465/587 | SMTPS / Submission | Yes | Secure email send |
| 514 | Syslog | No by default | Log forwarding |
| 636 | LDAPS | Yes | Secure LDAP |
| 989/990 | FTPS | Yes | FTP over TLS |
| 993 | IMAPS | Yes | Secure IMAP |
| 995 | POP3S | Yes | Secure POP3 |
| 1433 | MS SQL | - | Database |
| 3306 | MySQL | - | Database |
| 3389 | RDP | - | Windows remote desktop |
| 5060/5061 | SIP / SIPS | - | VoIP signaling |
| 6379 | Redis | - | In-memory DB (insecure if exposed) |

## Secure vs. insecure pairs (common exam trick)

| Insecure | Secure replacement |
|----------|--------------------|
| Telnet (23) | SSH (22) |
| FTP (20/21) | SFTP (22) / FTPS (989/990) |
| HTTP (80) | HTTPS (443) |
| POP3 (110) | POP3S (995) |
| IMAP (143) | IMAPS (993) |
| LDAP (389) | LDAPS (636) |
| SNMP v1/v2 | SNMP v3 |

## Memory tip

Many secure versions are just the insecure port + "S" over TLS:
HTTP 80 -> HTTPS 443, but the email ones (POP3 110 -> 995, IMAP 143 -> 993,
LDAP 389 -> 636) you mostly have to memorize.
