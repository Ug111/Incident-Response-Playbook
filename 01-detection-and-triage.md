# 1. Detection & Triage

## Purpose
Establish a consistent process for identifying security events and determining initial priority before investigation begins

## Detection Sources
- IDS alerts (Suricata) - network-based threat signatures
- SIEM correlation searches (Splunk) - authentication and log-based anomalies
- Automated tooling (Python detection scripts) - Pattern-based flagging

## Triage Process

**Step 1: Acknowledge**
- Log receipt of alert with timestamp
- Assign unique ticket ID
- Note source system (IDS/SIEM/tool)

**Step 2: Initial Classification**
Classify by severity using this matrix:

|   Severity      |   Criteria    |  Response Time  |
| --------------  | ------------- |  -------------- |
|  Critical       |  Active compromise, data exfiltration indicators     | Immediate (<15 min) |
|  High           |  Successful unauthorized access, brute-force success | <1 hour |
|  Medium         |  Repeated failed attempts, suspicious scanning | <4 hours |
|  Low            |  Single anomaly, informational alert | <24 hours |

**Step 3: Initial Filtering**
- Check against known false-positive patterns
- Verify asset criticality (Production vs. test system)
- Cross-reference with recent related tickets

  **Step 4: Assignment**
  - Route to appropriate analyst/queue based on severity
  -  Document assignment in ticket
 
  ## Example (from my Suricata lab)
  > Alert: SID 1000002 "Potential Port Scan" - Source 192.168.56.102 - Destination 192.168.56.101
  > Initial Classification: **Medium** (reconnaissance activity, no successful access yet)
  > Action: Flagged for investigation, monitoring source IP for follow-up activity
