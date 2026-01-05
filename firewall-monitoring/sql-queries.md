# Firewall Monitoring SPL Queries (pfSense)

These queries support network-level threat monitoring using pfSense syslog data ingested into Splunk SIEM.

---

## Firewall Traffic Volume Over Time

```spl
index=main sourcetype=syslog host=10.0.0.246
| timechart span=5m count

index=main sourcetype=syslog host=10.0.0.246 (block OR deny)
| timechart span=5m count as "Blocked Events"

index=main sourcetype=syslog host=10.0.0.246
| eval action=case(
    match(_raw, "(?i)\bblock\b"), "block",
    match(_raw, "(?i)\bpass\b"), "pass",
    1=1, "other"
)
| stats count by action
| where action!="other"

index=main sourcetype=syslog host=10.0.0.246 (block OR deny)
| stats count by _raw
| sort - count
| head 10


index=main sourcetype=syslog (filterlog OR pfSense OR pfsense)
| timechart span=5m count
