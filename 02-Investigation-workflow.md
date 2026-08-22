# 2. Investigation Workflow

## Purpose
Systematic methodology for collecting evidence, analyzing relationships, and determining incident  scope.

## Investigation Steps

**Step 1: Gather Context**
- Pull full alert details (source/destination IP, ports, protocol, timestamp)
- Query SIEM for related events in surrounding time window (30 min)
- Check for repeated activity from same source

**Step 2: Establish Relationships**
Ask:
- Is this source IP associated with previous tickets?
- Does this affect a critical asset or service?
- Is there a pattern across multiple systems?

**Step 3: Determine Scope**
- Single event or part of a campaign?
- Internal or external source?
- Successful action or attempted only?

## Example Investigation (from my Splunk SIEM lab)

**Alert:** 47 failed SSH  login attempts from single source IP within 5 minutes

**Investigation findings:**
- Correlated against 50,000+ authentication events
-  Source IP: no prior history in environment
-  Target account: valid services account
-  Pattern: sequential password attempts (dictionary-style)
-  Outcome: No successful login recorded

**Conclusion:** Brute-force attempt, unsuccessful. Recommend IP blocklist + account lockout policy review.
