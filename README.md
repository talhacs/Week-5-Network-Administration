# Week 5 — Enterprise Services Infrastructure Deployment

**Intern:** Talha Asghar
**Registration No.:** NETB01-1565
**Program:** IT-Simplera Institute — Network Administration Internship
**Supervisor:** Jawad Qayum, Senior Network Administrator
**Submission Date:** 1 August 2026 | **Deadline:** 1 August 2026

## Overview

A centralized enterprise services deployment — one authoritative server providing DHCP, DNS, HTTP/HTTPS, FTP, TFTP, NTP, Syslog, and SNMP to three department VLANs (HR, Finance, IT), built and verified in Cisco Packet Tracer.

## Repository Structure

```
Week5/
├── README.md
├── Week5_Report.pdf              # Full report: design, service config, verification, troubleshooting
├── Week5_Lab.pkt                  # Cisco Packet Tracer project (add your .pkt file here)
└── screenshots/
    ├── topology/                   # Full topology
    ├── dhcp-dns/                    # DHCP lease + DNS resolution
    ├── http-https/                  # Web service access
    ├── ftp-tftp/                    # File transfer + config backup/restore
    ├── ntp-syslog-snmp/             # Time sync, centralized logging, SNMP agent status
    └── connectivity-tests/          # Ping/traceroute from each department to the server
```

## Design Highlight

DHCP is centralized on the services server rather than run locally on the router — every department VLAN carries an `ip helper-address` pointing at the server, relaying DHCP broadcasts across the Layer 3 boundary. Every device (router + both switches) is also an NTP client, a Syslog client, and an SNMP-managed agent pointed at that same server, so there's one place to check time, logs, and device health for the whole network.

Full IP addressing (VLSM, base `10.60.0.0/16`, including a dedicated Server Farm VLAN) and all device configs are in `Week5_Report.pdf`, Sections 3-5.

## Tools

Cisco Packet Tracer

## Related

- LinkedIn post: [insert your post link after publishing]
- Part of the IT-Simplera Institute Network Administration Internship program.
