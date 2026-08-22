# 5. Closure & Lessons Learned 

## Purpose
Define criteria for closing incidents and capturing knowledge for continuous improvement.

## Closure Criteria
An incident may be closed when:
- [ ] Root cause has been identified and document
- [ ] Immediate risk has been mitigated or confirmed as non-impactful
- [ ] Evidence has been archived for future reference
- [ ] Any recommended remediation actions have been documented and asisgned
- [ ] Stakeholders (if applicable) have been notified of resolution

## Post-Incident Review Questions
1. Did our detection rules perform as expected?
2. Was the investigation timeline efficient? What slowed it down ?
3. Did this reveal any policy or configuration gaps?
4. Should this incident inform new detection rules or thresholds?

## Lessons Learned Log (From My Lab Incidents)

|  Incident   | Key Takeaway  |
| ----------  | ------------- |
| Ticket #001 (Port Scan) | Threshold-based detection rules work well for reconnaissance activity; confirmed 100% detection accuracy  |
| Ticket #002 (SSH Brute-Force) | Detection succeeded, but exposed a policy gap - account lockout threshold too permissive (47 attempts allowed) |

## Continuous Improvement
Each closed incident feeds back into:
- Detection rule tuning ( reduce false positives / false negatives)
- Policy recommendations (e.g., lockout thresholds, firewall rules)
- Documentation updates for faster future investigation
