# NETWORKWALKS-B084J-WK2-PM1-FOOTPRINTING-RECON-KALI-TOOLS

Footprinting & Reconnaissance with Multiple Kali Tools

**Building a complete public profile of a target website using six built-in Kali Linux reconnaissance tools**

## Project Overview

This project focuses on **footprinting and passive reconnaissance** of the live website **networkwalks.com** using six built-in Kali Linux tools: `whois`, `whatweb`, `nslookup`, `curl`, `wafw00f` and `dnsrecon`.

Reconnaissance is the first step in any real attack or security test. Before touching a target, an attacker quietly collects as much public information as possible: who owns the domain, its real IP address, the hosting provider, the web technologies it runs, its DNS and mail records, and whether a firewall is protecting it.

Each tool reveals a different piece of the target, and together they build a full profile of it. The findings from this project form the foundation for the scanning and attack-simulation projects that follow.

This project builds on the Week 1 lab environment: a Kali Linux VM on a VirtualBox NAT Network (`10.0.0.0/24`).

## Objectives

The main objectives of this project are to:

- Find domain registration details using `whois`.
- Fingerprint web technologies using `whatweb`.
- Resolve the domain to its IP address using `nslookup`.
- Read HTTP response headers using `curl -I`.
- Detect a Web Application Firewall using `wafw00f`.
- Enumerate DNS records using `dnsrecon`.
- Save a screenshot and a text-file output for every task.
- Understand how attackers use each piece of information.
- Document the complete process.
- Prepare the findings for future scanning and security-testing projects.

## Purpose of the Lab

This lab provides an isolated and controlled environment for learning **footprinting and reconnaissance** techniques.

It can be used for activities such as:

- Domain and registrar investigation
- Web technology fingerprinting
- DNS enumeration
- HTTP header analysis
- Firewall (WAF) detection
- Attack-surface mapping

# Lab Setup Procedure

All commands were run from a terminal in Kali Linux. The screenshot and text output of each command were saved for the final report.

## Step 1. Domain Registration Lookup (whois)

`whois` queries the public domain registration record to find who owns the domain, when it was registered, and its name servers.

**Tool:** whois

```
whois networkwalks.com
```

![whois output](screenshots/task1-whois.png)

**Key findings:**

- Registrar: GoDaddy.com, LLC
- Creation date: 2019-11-06
- Registry expiry date: 2027-11-06
- Name servers: `NS6135.HOSTGATOR.COM`, `NS6136.HOSTGATOR.COM`
- DNSSEC: unsigned

**How attackers use this:** The name servers point to HostGator, so an attacker instantly learns the hosting provider. Registration dates and abuse contacts help with social engineering and planning.
