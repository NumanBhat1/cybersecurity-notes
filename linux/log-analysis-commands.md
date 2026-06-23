# Linux: Log Analysis Commands

The command-line skills a SOC analyst uses to dig through logs on a Linux host.

## Where logs live

| Path | What's in it |
|------|--------------|
| `/var/log/auth.log` | Authentication (logins, sudo, SSH) - Debian/Ubuntu |
| `/var/log/secure` | Same, on RHEL/CentOS |
| `/var/log/syslog` | General system messages |
| `/var/log/kern.log` | Kernel messages |
| `journalctl` | systemd journal (modern logging) |

## Core commands

```bash
# view a log live as it updates
tail -f /var/log/auth.log

# search for a pattern
grep "Failed password" /var/log/auth.log

# count matches
grep -c "Failed password" /var/log/auth.log

# show lines around a match (context)
grep -B2 -A2 "error" /var/log/syslog
```

## The classic log-analysis pipeline

Find the top source IPs of failed SSH logins:

```bash
grep "Failed password" /var/log/auth.log \
  | grep -oE "from [0-9.]+" \
  | awk '{print $2}' \
  | sort | uniq -c | sort -rn | head
```

Breakdown:
- `grep` finds the failed-login lines
- `grep -oE` pulls just the IP after "from"
- `awk '{print $2}'` keeps the IP field
- `sort | uniq -c` counts duplicates
- `sort -rn` ranks highest first

## Handy text tools

| Tool | Use |
|------|-----|
| `grep` | search for patterns (add `-i` for case-insensitive, `-E` for regex) |
| `awk` | extract / process columns |
| `sed` | find-and-replace, edit streams |
| `cut` | grab fields by delimiter (`cut -d: -f1`) |
| `sort` / `uniq` | order and de-duplicate (`uniq -c` to count) |
| `wc -l` | count lines |
| `tail` / `head` | end / start of a file |

## Useful one-liners

```bash
# successful SSH logins
grep "Accepted password" /var/log/auth.log

# all sudo commands run
grep "sudo:" /var/log/auth.log

# logins from a specific IP
grep "10.0.0.5" /var/log/auth.log

# journalctl: ssh service logs since boot
journalctl -u ssh --since today
```

## SOC takeaway

Most "detection" on a single host is just smart grep/awk over the right log file.
Getting fluent with this pipeline is one of the highest-value Linux skills for an
analyst.
