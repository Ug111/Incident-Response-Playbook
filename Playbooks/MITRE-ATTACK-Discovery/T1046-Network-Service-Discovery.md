# Playbook: T1046 - Network Service Discovery

## Technique Overview
Adversaries attempt to identify active services, open ports, and running 
applications on a network determine viable attack paths and vulnerable
targets before launching further attacks. commonly performed using tools
like nmap during the reconnaissance phase.

## Detection
- Multiple connection attempts to sequential/varied ports from single source
- Threshold-based rule: 10+ port connections within  60 seconds from same host
- Source: Suricata SID 100002 ("Potential Port Scan")
- SYN packets without completed handshake (half-open scan pattern)

## Investigation Steps
1. Identify source IP and scope of ports/hosts targeted
2. Determine scan type (TCP SYN scan, fully connect, UDP scan) via flag analysis
3. Check if scan originated internally or externally
4. Cross-reference source IP against known asset inventory / expected scanning (e.g., vulnerability scanners)
5. Review whether any scanned ports returned service banners (indicates deeper enumeration)

## Containment
- Block or rate-limit source IP at firewall if unauthorized
- Verify no follow-on exploitation attempts against discovered open ports
- If internal source: identify device/user and confirm authorization (may be legitimate scanning tool)

## Reference Incident
See: [Ticket #001](../ ../04-same-incident-tickets/ticket-001.md)

## Related MITRE Techniques
- T1595 - Active Scanning (pre-access external reconnaissance)
- T1018 - Remote System Discovery
- T1590 - Gather Victim Network Information
