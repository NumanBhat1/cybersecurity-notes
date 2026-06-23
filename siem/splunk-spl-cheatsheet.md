# SIEM: Splunk SPL Cheatsheet

Basics of Splunk's Search Processing Language (SPL) for SOC work.

## How a search reads

Data flows left to right through pipes (`|`), each command transforming the
results from the one before it:

```spl
index=main sourcetype="WinEventLog:Security" EventCode=4625
| stats count by src_ip
| where count > 10
| sort -count
```

"Get failed logons, count them per source IP, keep IPs over 10, sort highest
first."

## Common search commands

| Command | What it does |
|---------|--------------|
| `search` / (implicit) | filter events |
| `stats` | aggregate (count, sum, avg, values) |
| `table` | pick columns to show |
| `sort` | order results (`-` for descending) |
| `where` | filter on computed conditions |
| `eval` | create/compute a new field |
| `rex` | extract fields with regex |
| `dedup` | remove duplicates |
| `top` / `rare` | most / least common values |
| `transaction` | group related events into one |
| `timechart` | aggregate over time (great for graphs) |

## Examples

```spl
# Top 10 source IPs for failed logons
index=main EventCode=4625
| top limit=10 src_ip

# Failed then successful logon from same IP within 5 min (possible compromise)
index=main (EventCode=4625 OR EventCode=4624)
| transaction src_ip maxspan=5m
| where eventcount > 5 AND searchmatch("EventCode=4624")

# Suspicious PowerShell process creations
index=main sourcetype="WinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
| search Image="*powershell.exe" (CommandLine="*-enc*" OR CommandLine="*-w hidden*")
| table _time, host, User, CommandLine

# New local user created
index=main EventCode=4720
| table _time, host, TargetUserName, SubjectUserName

# Logon volume over time
index=main EventCode=4624
| timechart count by host
```

## Time ranges

Use the time picker, or inline:

```spl
... earliest=-24h latest=now
... earliest=-7d@d
```

## SOC takeaway

Most SOC detections are a filter -> aggregate -> threshold pattern in SPL. Once
you can read a pipeline left to right, the rest is learning which fields exist in
your data (run a broad search and inspect the fields panel).
