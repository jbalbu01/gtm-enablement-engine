---
name: handoff-builder
description: Create structured handoff documents between GTM functions — sales-to-CS, SDR-to-AE, AE-to-SE, sales-to-implementation. Captures deal context, customer expectations, success criteria, risk flags, and action items so nothing falls through the cracks. Use this skill whenever a deal is closing and needs to transition to CS or implementation, when an SDR qualifies a lead for an AE, when a rep needs SE support, or when someone says "hand off this deal", "create a CS transition doc", "pass this lead to [rep]", "implementation kickoff", or when building handoff templates for the team.
---

# Handoff Builder

Create seamless transitions between GTM functions. The handoff between sales and CS is where most customer relationships break — the customer repeats everything they already told sales, expectations get lost, and trust erodes. This skill prevents that.

## The Handoff Problem

Every GTM handoff is a moment of risk:
- **SDR → AE:** Context about the prospect's pain and urgency gets lost
- **AE → SE:** Technical requirements aren't fully communicated
- **Sales → CS:** Customer expectations don't match what was sold
- **Sales → Implementation:** Scope and timeline assumptions differ
- **CS → Sales:** Expansion opportunities don't get pursued

Bad handoffs cost deals, create churn, and destroy cross-functional trust.

---

## Handoff Types

### 1. SDR → AE Handoff
```markdown
# Lead Handoff: [Company Name]

**SDR:** [Name] | **AE:** [Name] | **Date:** [Date]

## Prospect Summary
| Field | Detail |
|-------|--------|
| Company | [Name, size, industry] |
| Contact | [Name, title, email, phone] |
| Source | [How they came in — inbound, outbound, event, referral] |

## Why They Took the Meeting
[What pain or interest did they express? Use their words.]

## Qualification Notes
| Criterion | What We Know |
|-----------|-------------|
| Pain | [Specific problem they mentioned] |
| Budget | [Any signal — allocated, looking for budget, unknown] |
| Authority | [Is this the decision-maker? Who else is involved?] |
| Timeline | [Any urgency driver or target date?] |

## Conversation History
[Summary of all touchpoints — emails, calls, content engagement]

## Suggested Approach for First Call
[Based on what the SDR learned, what should the AE focus on?]

## Red Flags
[Anything concerning — competitor already in play, low urgency, tire-kicking signals]
```

### 2. Sales → CS Handoff
```markdown
# Customer Handoff: [Company Name]

**AE:** [Name] | **CSM:** [Name] | **Date:** [Date]
**Deal Size:** $[amount] | **Contract Start:** [Date] | **Term:** [Duration]

## Customer Overview
| Field | Detail |
|-------|--------|
| Company | [Name, size, industry, HQ] |
| Primary Contact | [Name, title, email] |
| Executive Sponsor | [Name, title] |
| Technical Lead | [Name, title] |

## What They Bought and Why
[Clear description of: what was sold, which use cases they're deploying for, and the business problem they're solving. Don't just list SKUs — explain the intent.]

## Customer Expectations
[What did the customer explicitly say they expect to achieve? Use their words. This is the most important section — it's the promise CS needs to deliver on.]

### Success Criteria (Agreed with Customer)
1. [Specific, measurable outcome they expect]
2. [Second outcome]
3. [Third outcome]

### Timeline Expectations
| Milestone | Customer's Expected Date |
|-----------|------------------------|
| Go-live / first value | [Date] |
| Full rollout | [Date] |
| First business review | [Date] |

## Sales Cycle Context

### Key Decisions and Why
[What were the pivotal moments in the sale? What almost killed the deal? What won it?]

### Competitors Evaluated
[Who else they looked at and why they chose you — this helps CS reinforce the decision]

### Concerns Raised During Sales
[Any objections, hesitations, or risks the customer expressed. CS needs to know these so they don't resurface as churn risk.]

### Internal Champion
[Who advocated for you internally? CS should nurture this relationship.]

### Potential Blocker
[Anyone who was skeptical or opposed? CS should be aware.]

## Technical Context
| Item | Detail |
|------|--------|
| Integration requirements | [What needs to connect] |
| Data migration | [Scope of migration] |
| Technical constraints | [Known limitations or requirements] |
| Security/compliance | [Any special requirements] |

## Expansion Opportunity
[What wasn't included in this deal but could be a future upsell? What signals to watch for.]

## Risk Flags
| Risk | Severity | Mitigation |
|------|----------|------------|
| [Risk] | 🔴🟡🟢 | [What CS should do] |

## Attachments / References
- [Link to proposal]
- [Link to SOW]
- [Link to call recordings]
- [Link to CRM opportunity]
```

### 3. AE → SE Handoff
Brief but precise — what the SE needs to prep a demo or POC.

### 4. Sales → Implementation Handoff
Scope, timeline, technical requirements, customer expectations, and known risks.

---

## Handoff Quality Score

Every handoff gets scored on completeness:

| Section | Weight | Score |
|---------|--------|-------|
| Customer context | 20% | [Complete / Partial / Missing] |
| Expectations & success criteria | 25% | [Score] |
| Risk flags | 15% | [Score] |
| Technical requirements | 15% | [Score] |
| Relationship context | 15% | [Score] |
| Action items | 10% | [Score] |

**Overall:** [X/100] — handoffs below 70 get flagged for additional information.

---

## Related Skills

- **deal-qualification** → Qualification data feeds directly into handoff context
- **proposal-builder** → Proposal content referenced in handoff
- **expansion-playbook** → Expansion opportunities identified during handoff
- **gtm-memory** → Handoff context stored for future reference
