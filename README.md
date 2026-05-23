# Cybersecurity Home Lab

## Overview
A defensive cybersecurity home lab focused on blue team skills — 
log analysis, SIEM investigation, intrusion detection, and 
endpoint monitoring.

I am currently a beginner in cybersecurity actively building my 
skills through hands on lab work. This repository documents my 
learning journey and investigations. I am open to any feedback 
or suggestions from the community — feel free to open an issue 
or reach out.

## Lab Architecture
- **Ubuntu 22.04 VM** — Analyst workstation running Splunk SIEM and Suricata IDS
- **Windows 11 VM** — Monitored endpoint running Sysmon and Splunk Forwarder

## Tools Used
- Splunk Enterprise — SIEM and log analysis
- Sysmon — Windows endpoint telemetry
- Suricata — Network intrusion detection
- Wireshark — Packet analysis
- tcpdump — Command line packet capture
- Atomic Red Team — Attack simulation
- Hayabusa — Windows log threat hunting
- Chainsaw — Log analysis with SIGMA rules

## Investigations
- [Investigation 1 - Failed Login Analysis](investigations/failed-login-analysis.md)
- [Investigation 2 - New User Account Creation](investigations/new-account-creation.md)

## Status
Currently building — adding investigations weekly
