# Investigation 2 — New User Account Creation
**Date:** May 21, 2026
**Tools Used:** Splunk, Windows Event Logs

## What I Was Looking For
Investigated EventCode 4720 (new user account created) to determine 
if any unauthorized accounts were created on the Windows endpoint.

## How I Found It
Searched Splunk using:
index=main security 4720

## What I Found
7 new account creation events detected.

Event 1 — 6:58 AM
- Created by: DESKTOP-L8B6SVL$ (computer account)
- Account created: SYSTEM
- Assessment: Built in Windows system account, created automatically

Events 2 and 3 — 12:22 PM (duplicate entries)
- Created by: DESKTOP-L8B6SVL$ (computer account)
- Account created: cheyston
- Assessment: My own user account created during Windows setup

Events 4 and 5 — 12:14 PM (duplicate entries)
- Created by: WIN-9PKKLF6C3P7$ (computer account)
- Account created: defaultuser0
- Assessment: Temporary account created during Windows Out of Box 
  Experience, automatically deleted after setup

Events 6 and 7 — 12:11 PM (duplicate entries)
- Created by: MINWINPC$ (computer account)
- Account created: WDAGUtilityAccount
- Assessment: Windows Defender Application Guard account, created 
  automatically during Windows 11 installation

## Conclusion
All 7 account creation events are legitimate Windows installation 
activity. Every account was created by a computer account ending 
in $ which indicates automated system processes, not human users. 
All accounts are either built in Windows accounts or my own user 
account. No unauthorized accounts were created.

**Result: False Positive — No action required**

## What Suspicious Would Look Like
- A real username creating a new account
- New account with an unusual name like backdoor or temp123
- Account created at an unexpected time like 3am
- Account created long after initial Windows setup was complete
- Multiple new accounts created in rapid succession
