# Investigation 1 — Failed Login Analysis
**Date:** May 21, 2026
**Tools Used:** Splunk, Windows Event Logs

## What I Was Looking For
Investigated EventCode 4625 (failed login attempts) to determine 
if any suspicious activity occurred on the Windows endpoint.

## How I Found It
Searched Splunk using:
index=main security 4625

## What I Found
3 failed login attempts detected.

2 failures occurred at the exact same timestamp.
1 failure occurred approximately 1 hour earlier.

Account names involved:
- DWM-1 (Desktop Window Manager — a Windows system process)
- DESKTOP-L8B6SVL$ (the computer account — normal Windows authentication)

Logon Types:
- 2 events were Logon Type 2 (Interactive)
- 1 event had no Logon Type assigned

## Conclusion
All 3 failed login attempts were attributed to Windows background 
system processes and computer accounts. No human user accounts were 
involved. No external IP addresses were present. The timing and 
account types are consistent with normal Windows startup behavior.

**Result: False Positive — No action required**

## What Suspicious Would Look Like
- Large number of failures in a short time from the same account
- Failures targeting Administrator or a real username
- External IP address as the source
- Failures immediately followed by a successful login
