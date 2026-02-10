---
name: win-loss-analysis
description: Analyze won and lost deals to identify patterns, improve win rates, and refine sales strategy. Use this skill whenever a rep or manager wants to understand why deals were won or lost, identify trends in pipeline outcomes, review deal performance over time, says "why did we lose that deal", "analyze our win rate", "what do our wins have in common", "post-mortem on this deal", or when conducting quarterly business reviews. Also trigger when someone uploads CRM export data for deal analysis, or when building training materials based on historical deal outcomes.
---

# Win/Loss Analysis

Turn deal outcomes into actionable insights. Understanding why you win and lose is the fastest way to improve your sales process, coaching, and competitive strategy. This isn't about blame — it's about patterns.

## Why This Matters

Most teams track win rate as a number but don't systematically learn from it. Win/loss analysis reveals:
- Which competitors you beat and which beat you (and why)
- What discovery patterns lead to wins vs. losses
- Where deals stall and die in your pipeline
- Which rep behaviors correlate with better outcomes
- How pricing, timing, and stakeholder engagement affect close rates

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                    WIN/LOSS ANALYSIS                               │
├─────────────────────────────────────────────────────────────────┤
│  MODES                                                            │
│  1. Single Deal — Post-mortem on one specific deal               │
│  2. Batch Analysis — Analyze a set of deals from CSV/CRM         │
│  3. Pattern Finder — Identify trends across wins and losses      │
│  4. Competitive Insight — Win/loss rates by competitor            │
│  5. Rep Performance — Analysis by rep (for managers)             │
├─────────────────────────────────────────────────────────────────┤
│  INPUT OPTIONS                                                    │
│  • Describe a deal and what happened                             │
│  • Upload a CSV export from your CRM                             │
│  • Paste deal notes or CRM data                                  │
│  • Connect CRM for automatic data pull                           │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

- "We lost the Acme deal — help me understand why"
- "Analyze these 50 deals and tell me what our wins have in common"
- "What's our win rate against Competitor X?"
- "Why do our deals stall at the proposal stage?"
- "Build a win/loss report for Q4"

---

## Single Deal Post-Mortem

### What I Need

Tell me everything about the deal:
- Company, deal size, timeline
- Who was involved (your side and theirs)
- What happened at each stage
- Why it was won or lost
- Competitors involved
- Any red flags you noticed in hindsight

### Output Format

```markdown
# Deal Post-Mortem: [Company Name]

**Outcome:** [Won / Lost / No Decision]
**Deal Size:** $[amount]
**Sales Cycle:** [Duration]
**Competitor:** [Who you competed against]
**Rep:** [Name]

---

## Timeline

| Date | Event | Impact |
|------|-------|--------|
| [Date] | [First meeting] | [Initial impression] |
| [Date] | [Key event] | [Positive/negative turning point] |
| [Date] | [Decision] | [Outcome] |

---

## What Went Right
1. [Strength — with specific evidence]
2. [Strength]

## What Went Wrong
1. [Issue — with specific evidence and what could have been done differently]
2. [Issue]

## Root Cause Analysis

**Primary reason for [win/loss]:** [The single biggest factor]

**Contributing factors:**
- [Factor 1]
- [Factor 2]

---

## Qualification Assessment (Retroactive)

| MEDDIC Criterion | Score at Close | Should Have Been |
|-----------------|---------------|-----------------|
| Metrics | [0-5] | [0-5] |
| Economic Buyer | [0-5] | [0-5] |
| Decision Criteria | [0-5] | [0-5] |
| Decision Process | [0-5] | [0-5] |
| Identify Pain | [0-5] | [0-5] |
| Champion | [0-5] | [0-5] |

---

## Lessons Learned

1. **[Lesson]** — [How to apply this to future deals]
2. **[Lesson]** — [Application]
3. **[Lesson]** — [Application]

## If You Could Replay This Deal

[Specific advice on what to do differently, starting from the first interaction]
```

---

## Batch Analysis

When analyzing multiple deals (from CSV upload or description):

```markdown
# Win/Loss Analysis: [Period or Description]

**Deals Analyzed:** [Count]
**Win Rate:** [X]%
**Average Deal Size:** $[X] (Won) / $[X] (Lost)
**Average Cycle Length:** [X] days (Won) / [X] days (Lost)

---

## Win Patterns

Deals you won share these characteristics:
1. **[Pattern]** — Found in [X]% of wins vs [Y]% of losses
2. **[Pattern]** — [Evidence]
3. **[Pattern]** — [Evidence]

## Loss Patterns

Deals you lost share these characteristics:
1. **[Pattern]** — Found in [X]% of losses
2. **[Pattern]** — [Evidence]
3. **[Pattern]** — [Evidence]

## Competitive Breakdown

| Competitor | Deals | Wins | Losses | Win Rate | Key Differentiator |
|-----------|-------|------|--------|----------|-------------------|
| [Comp A] | [N] | [N] | [N] | [X]% | [Why you win/lose] |
| [Comp B] | [N] | [N] | [N] | [X]% | [Why you win/lose] |
| No Competitor | [N] | [N] | [N] | [X]% | [Status quo] |

## Stage Analysis

| Stage | Deals Entering | Conversion | Avg Time | Bottleneck? |
|-------|---------------|------------|----------|-------------|
| Discovery | [N] | [X]% | [Days] | [Yes/No] |
| Demo | [N] | [X]% | [Days] | [Yes/No] |
| Proposal | [N] | [X]% | [Days] | [Yes/No] |
| Negotiation | [N] | [X]% | [Days] | [Yes/No] |
| Closed | [N] | — | — | — |

---

## Recommendations

### Quick Wins (This Quarter)
1. [Actionable recommendation with expected impact]
2. [Recommendation]

### Strategic Changes (Next Quarter)
1. [Larger initiative based on patterns]
2. [Initiative]

### Enablement Gaps
1. [Training or tool need identified from analysis]
2. [Gap]
```

---

## CSV Format

If uploading a CRM export, the more fields the better. Useful columns include:
- Company name, deal size, close date
- Win/loss status, loss reason
- Competitor, rep name
- Days in pipeline, stage progression dates
- Number of stakeholders, champion identified
- Discovery quality score (if tracked)

I'll work with whatever columns you have.

---

## Related Skills

- **deal-qualification** — Apply lessons learned to better qualify future deals
- **sales-coaching** — Turn win/loss insights into coaching conversations
- **battle-cards** — Update competitive intel based on win/loss patterns
- **playbook-builder** — Refine playbooks based on what actually works
