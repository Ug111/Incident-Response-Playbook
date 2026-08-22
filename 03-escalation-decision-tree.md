# 3. Escalation Decision Tree

## Purpose
Define clear criteria for when an event requires escalation vs. standard closure.

## Decision Tree

Is there evidence of successful unauthorized access?

|--------- YES -> ESCALATE(Critical/High)->Notify Incident Response Lead
|--------- NO  -> Continue

Is the affected asset business-critical?

|--------- YES -> ESCALATE(High) ->
Notify asset owner + IR lead
|--------- NO -> Continue

Is this part of a recurring pattern (3+ similar event in 24h)?

|--------- NO -> Continue

Does investigation reveal a new/unknown attack pattern?

|--------- YES -> ESCALATE(Medium) - Notify threat intel team

|--------- NO -> Document and close as standard event

## Escalation package (What to include)
When escalating, provide:
1: **Event Description** - What happened in plain language
2. **Business Risk** - Why this matters to the organization
3. **Evidence Summary** - Key logs, IPs, timestamps
4. **Recommend Actions** - Immediate remediation + preventive steps 

## Example Escalation (from my IDS lab)

> **Event:** SSH connection attempts detected on non-standard hours from unrecognized source
> **Risk:** Potential unauthorized access attempt to production-equivalent ystem
> **Evidence:** 3 connection attempts, SID 1000003, timestamps 02:14-02:17 AM
> **Recommended Action:** Block source IP at firewall, review SSH key authentication policy, enable rate-limiting
