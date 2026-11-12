# Network Reconnaissance & Network Scanning

## Project Overview

This project documents practical penetration testing activities performed as part of my Week 2 Cybersecurity & Ethical Hacking internship at **Networkwalks**.

The primary objective was to understand how security professionals perform information gathering, footprinting, host discovery, and network scanning before moving towards deeper security assessments.

The project covered two major phases:

1. **Footprinting & Reconnaissance** – Gathering publicly available information about a target domain.
2. **Network Scanning & Discovery** – Using Zenmap to identify active port/services and analyze information exposure.

> All activities were performed within an authorized testing scope for educational purposes.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Security testing environment |
| WHOIS | Domain registration information |
| WhatWeb | Web technology fingerprinting |
| Nslookup | DNS resolution |
| cURL | HTTP response header analysis |
| Wafw00f | Web Application Firewall detection |
| DNSRecon | DNS enumeration |
| Zenmap | Network scanning and host discovery |
| Nmap | Network reconnaissance and port scanning |

## Activities Performed

### 1. Footprinting & Reconnaissance

Performed information gathering against the authorized target domain using multiple Kali Linux tools.

Activities included:

- WHOIS lookup to collect domain registration information.
- Web technology fingerprinting using WhatWeb.
- DNS resolution using Nslookup.
- HTTP response header inspection using cURL.
- WAF identification using Wafw00f.
- DNS record enumeration using DNSRecon.

### 2. Network Scanning Using Zenmap

Used Zenmap (Nmap GUI) to perform network discovery and scanning.

Activities included:

- Identifying active hosts.
- Discovering open, closed, and filtered TCP ports.
- Identifying running services and service versions.
- Collecting IP and MAC address information.
- Analyzing network scan results.


## Key Observations

The reconnaissance activities demonstrated how publicly accessible information can help build an initial profile of a target's infrastructure.

The network scanning exercise provided practical experience in:

- Host discovery.
- Port enumeration.
- Service identification.
- Network mapping.
- Attack surface identification.

**Important:** The observations documented in this project are reconnaissance findings, not confirmed vulnerabilities. No exploitation or vulnerability validation was performed during these modules.

## Security Recommendations

Based on the activities performed:

- Regularly review publicly exposed technology information.
- Keep CMS platforms and plugins updated.
- Review HTTP response headers.
- Audit publicly accessible DNS records.
- Properly configure and monitor WAF protection.
- Perform regular network discovery.
- Investigate unexpected network devices.
- Maintain updated network documentation.

## Skills Developed

- Network Reconnaissance
- Information Gathering
- DNS Enumeration
- Web Technology Fingerprinting
- HTTP Header Analysis
- WAF Detection
- Host Discovery
- TCP Port Scanning
- Service Enumeration
- Network Mapping
- Security Documentation

## Project Evidence

Screenshots of the practical exercises and scan results are documented in the project report.

Suggested evidence to include in this repository:

- WHOIS output
- WhatWeb output
- Nslookup results
- cURL HTTP headers
- Wafw00f results
- DNSRecon output
- Zenmap network discovery results
- Zenmap port scan results

## Authorization & Disclaimer

All testing activities were conducted within the authorized scope of the assigned educational exercise.

This repository is intended for educational and cybersecurity learning purposes only. Do not perform reconnaissance or scanning against systems without appropriate authorization.

---

**Author:** Mukund Ugale  
**Program:** Cybersecurity & Ethical Hacking Internship  
**Organization:** Networkwalks  
**Modules:** W2-PM1 (Multiple Kali Tools) | W2-PM5 (Zenmap Scanning)
