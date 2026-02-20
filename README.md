# Red Team Lab – Network Connectivity & Netcat Testing

## Lab Summary
This project simulates a Red Team scenario focused on diagnosing network connectivity and validating whether remote exploitation is technically possible.

The goal was not exploitation itself, but understanding the prerequisites that make exploitation feasible in real environments.

---

## Environment

- Attacker: Kali Linux
- Target: Linux server
- Virtualization: VMware
- Network: Internal subnet (same Layer 2 network)

---

## Tools Used

- Nmap – host discovery and port visibility
- Netcat – TCP communication testing and shell simulation
- Linux networking tools – interface and routing diagnostics

---

## Methodology

### Network Identification
Verified interfaces using `ip addr`, confirming valid IP addresses and distinguishing loopback from reachable hosts.

### Routing Analysis
Inspected routing table with `ip route`.  
Detected missing route preventing connectivity and corrected network configuration.

### Host Validation
Used Nmap to confirm host reachability and observe port filtering behavior.

### Service Communication Test
Established TCP communication using Netcat listener/client model.  
Validated bidirectional communication and successful handshake.

### Error Investigation
Observed and interpreted typical connectivity failures:

- **Network unreachable** → routing problem  
- **Connection timed out** → firewall or service absence  
- **Connection refused** → port closed but host reachable  

---

## Red Team Simulation

### Bind Shell
Target listens for inbound connection.

### Reverse Shell
Target initiates outbound connection to attacker.  
This approach is more realistic because it bypasses inbound firewall restrictions.

---

## Skills Demonstrated

- Network troubleshooting methodology  
- Layer 3 routing diagnosis  
- Service availability validation  
- TCP communication verification  
- Understanding prerequisites for exploitation  
- Structured Red Team reasoning process  

---

## Key Takeaways

Remote exploitation depends on multiple technical prerequisites:

1. Functional network connectivity  
2. Valid routing configuration  
3. Open port  
4. Listening service  
5. Firewall allowing traffic  

Failure at any stage prevents exploitation.

---

## Files

- `Red_Team_Lab_Connectivity_Netcat_EN.pdf` – full lab documentation

---

## Author

**Sivonaldo Silva**  
Cybersecurity student focused on hands-on Red Team practice.

---

This repository is part of my practical cybersecurity learning journey.
