# Incident Ticket #002

**Status:** Closed 
**Severity:** High (initial) -> Downgraded to Medium after investigation
**Detection Source:** Splunk SIEM (Custom SPL coorelation search)

## Summary
Repeated SSH authentication failures detected against service account , consistent with brute-force pattern.

## Timeline
|    Time  |   Event  |
| -----    | -------  |
| 09:14:00 | First failed login attempts recorded |
| 09:14:00-09:19:12  | 47 total failed attempts recorded |
| 09:19:15 | Splunk correlation search flagged threshold breach |
| 09:22:00 | Analyst acknowledged, began investigation  |
| 09:40:00 | Investigation completed |
| 09:45:00 | Ticket closed  |

## Investigation Findings 
- Source IP: no prior history in 50,000+ event authentication baseline
- Attempt pattern: sequential dictionary-style password guessing
- Target account: Valid service account (non-privileged)
- No successful authentication recorded across all 47 attempts

## Root Cause
External brute-force attempt against exposed service account; account lockout policy prevented escalation.

## Resolution
- Recommended source IP addition to blocklist
- Recommended review of account lockout threshold (currently allows 47+ attempts before any lockout trigger)

## Lessons Learned
Detection worked correctly, but investigation revealed a gap in account lockout policy - following up with recommendation to reduce lockout threshold to 5-10 attempts .
