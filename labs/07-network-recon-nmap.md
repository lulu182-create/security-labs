# Lab 07: Network Reconnaissance with Nmap

**Category:** Reconnaissance
**Tools:** Nmap, Kali Linux, Metasploitable 2 (intentionally vulnerable target VM)
**Environment:** Isolated lab network

## Objective
Practice service enumeration against a known-vulnerable target to understand how attackers map an attack surface.

## Steps
1. Identified the target's IP address on the isolated lab network.
2. Ran `nmap -sV` to scan for open ports and identify running service versions.
3. Reviewed the results for exposed, high-risk services.

## Findings
The scan revealed multiple exposed services, including FTP, SSH, Telnet, HTTP, and Samba, several of which are commonly misconfigured or run outdated/vulnerable versions on Metasploitable by design.

## Takeaway
Service enumeration is the reconnaissance step before most real attacks. From a defensive view, this is exactly what an internal vulnerability scan should catch and what a hardened host should minimize (closing unused ports, patching services, disabling legacy protocols like Telnet).
