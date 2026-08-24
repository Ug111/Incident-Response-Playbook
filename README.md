# 🛡️ Incident Response Playbook - SOC Analyst

A documented incident response workflow demonstrating SOC analyst core competencies: event detection, triage, investigation, escalation, and closure. Built using real alert data from my Suricata IDS lab and Splunk SIEM lab as sample incident sources.

[![Version](https://img.shields.io/badge/Version-1.0.0-blue.svg)](https://github.com/Ug111/Incident-Response-Playbook)
[![Framework](https://img.shields.io/badge/Framework-NIST%20SP%20800--61-green.svg)](https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final)
[![Telemetry](https://img.shields.io/badge/Telemetry-MITRE%20ATT%26CK-orange.svg)](https://attack.mitre.org/)
[![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

---

## Overview

A documented incident response workflow demonstrating SOC analyst core competencies: event detection, triage, investigation, escalation, and closure. Built using real alert data from my Suricata IDS lab and Splunk SIEM lab as sample incident source.

**Event Detection** → **Triage & Filtering** → **Investigation** → **Escalation** → **Closure & Lessons Learned**

## Purpose
This playbook demonstrates my understanding of the full incident lifecycle - the same workflow used in production SOC environments (event detection - filtering - investigation - escalation - closure).

---

## Directory Structure

* **`01-detection-and-triage.md`** - How incidents are identified, filtered, and prioritized.
* **`02-investigation-workflow.md`** - Systematic investigation methodology and analysis steps.
* **`03-escalation-decision-tree.md`** - Clear criteria for when and how to escalate threats.
* **`04-sample-incident-tickets/`** - Sanitized example incident tickets based on lab scenarios.
* **`05-closure-and-lessons-learned.md`** - Incident closure criteria and post-incident review practices.

---

## Related Lab Projects

* [IDS-Threat-Detection-Lab](https://github.com/Ug111/IDS-Threat-Detection-Lab) - Primary source for Suricata network alert data.
* [SSH-Brute-Force-Detection-Splunk](https://github.com/Ug111/SSH-Brute-Force-Detection-Splunk) - Primary source for SIEM correlation data.

---

## Key Competencies Demonstrated
* ✅ Event detection and severity triage
* ✅ System investigation methodology
* ✅ Escalation decision-making
* ✅ Incident documentation and ticketing
* ✅ Root cause analysis
* ✅ Post-incident review & remediation
---

## MITRE ATT&CK® Coverage

* [x] **T1046** - Network Service Discovery (Port Scan)
* [x] **T1110.001** - Brute Force: Password Guessing (SSH)
* [ ] **T1566** - Phishing *(Planned)*
* [ ] **T1053** - Scheduled Task/Job *(Planned)*

---

## Related Projects
- [IDS-Threat-Detection-Lab](https://github.com/Ug111/IDS-Threat-Detection-Lab) - Source of Suricata alert data
- [SSH-Brute-Force-Detection-Splunk](https://github.com/Ug111/SSH-Brute-Force-Detection-Splunk) - Source of SIEM correlation data

---
