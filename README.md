# Red Team Lab – Network Connectivity & Netcat Testing

## Overview
This lab simulates a Red Team scenario focused on diagnosing network connectivity issues and establishing communication between two virtual machines.

The objective was to understand how routing, services, and firewall behavior impact the feasibility of remote exploitation.

## Lab Environment
- Kali Linux attacker machine
- Linux server target
- VMware virtual environment
- Internal network (same subnet)

## Tools Used
- Nmap
- Netcat
- Linux networking tools (ip addr, ip route)

## Methodology

### 1. Network Identification
- Verified interfaces using `ip addr`
- Confirmed both machines were in the same subnet
- Differentiated loopback vs real IP

### 2. Routing Diagnosis
- Checked routing table with `ip route`
- Identified missing route causing *Network unreachable*
- Fixed interface/network configuration

### 3. Host Discovery
- Used Nmap to confirm host availability
- Observed filtered/closed ports
- Confirmed that reachability does not imply service exposure

### 4. Service Communication Test
- Started Netcat listener on target
- Connected from attacker
- Validated bidirectional TCP communication

### 5. Error Analysis
Observed and analyzed:

- Network unreachable → routing issue
- Connection timed out → firewall/service absence
- Connection refused → port closed

### 6. Red Team Simulation

**Bind shell**
Target listens for incoming connection.

**Reverse shell**
Target initiates outbound connection to attacker (more realistic in real environments).

## Key Security Takeaways

- Exploitation requires a functional network first
- Routing misconfiguration prevents attacks entirely
- Open port + listening service are mandatory
- Reverse shells bypass inbound firewall restrictions
- Structured diagnosis is essential before exploitation

## Files

- `Red_Team_Lab_Connectivity_Netcat_EN.pdf` — full lab documentation

## Author
Sivonaldo Silva

---

This repository is part of my cybersecurity learning journey and hands-on Red Team practice.
