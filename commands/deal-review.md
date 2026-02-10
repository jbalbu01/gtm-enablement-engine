---
description: Run a structured deal strategy session — assess deal health, identify risks, build a win plan, and assign next actions
argument-hint: "<deal name or context>"
---

# /deal-review

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Run a structured deal review and strategy session. This is the command reps and managers use to stress-test a deal, identify blind spots, and build a concrete action plan to win.

## Usage

```
/deal-review
```

Then describe the deal, paste CRM data, or upload a pipeline export.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                       DEAL REVIEW                                 │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                        │
│  ✓ Describe your deal and I'll run a structured review           │
│  ✓ MEDDIC qualification score with gap analysis                  │
│  ✓ Risk identification and mitigation strategies                 │
│  ✓ Competitive positioning assessment                            │
│  ✓ Stakeholder map and power analysis                            │
│  ✓ Win plan with specific next actions                           │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + CRM: Pull deal data, opportunity history, contact records     │
│  + Chat: Find internal discussions about this account            │
│  + Knowledge base: Reference existing playbooks and collateral   │
└─────────────────────────────────────────────────────────────────┘
```

---

## What I Need From You

Tell me about the deal. Include as much as you can:

- **Company and deal size** — Who and how much?
- **Current stage** — Where are you in the process?
- **Key contacts** — Who you're talking to and their roles
- **Competition** — Who else is in the running?
- **Timeline** — Expected close date and what's driving it
- **Challenges** — What's not going well or concerns you
- **History** — Key moments, meetings, demos that have happened

**Quick mode:** "Review my deal with Acme Corp — $150K, in proposal stage, competing with CompX, champion is their VP of Eng, close date end of Q2"

---

## Output

```markdown
# Deal Review: [Company Name]

**Date:** [Today]
**Deal Size:** $[amount]
**Stage:** [Current stage]
**Expected Close:** [Date]
**Win Probability:** [Assessed %]

---

## Deal Health Score: [X/100]

| Category | Score | Status |
|----------|-------|--------|
| Qualification (MEDDIC) | [X/30] | 🟢🟡🔴 |
| Stakeholder Engagement | [X/20] | 🟢🟡🔴 |
| Competitive Position | [X/20] | 🟢🟡🔴 |
| Process Control | [X/15] | 🟢🟡🔴 |
| Momentum | [X/15] | 🟢🟡🔴 |

---

## MEDDIC Assessment

| Criterion | Score | Evidence | Gap |
|-----------|-------|----------|-----|
| Metrics | [0-5] | [What we know] | [What's missing] |
| Economic Buyer | [0-5] | [Evidence] | [Gap] |
| Decision Criteria | [0-5] | [Evidence] | [Gap] |
| Decision Process | [0-5] | [Evidence] | [Gap] |
| Identify Pain | [0-5] | [Evidence] | [Gap] |
| Champion | [0-5] | [Evidence] | [Gap] |

---

## Stakeholder Map

| Person | Title | Role in Deal | Sentiment | Engaged? |
|--------|-------|-------------|-----------|----------|
| [Name] | [Title] | Champion / Decision Maker / Influencer / Blocker | Positive/Neutral/Negative | Yes/No |

**Power Analysis:** [Who has the real power, who can kill the deal, who's your strongest advocate]

---

## Risk Assessment

| Risk | Severity | Evidence | Mitigation |
|------|----------|----------|------------|
| [Risk 1] | 🔴 High | [Why this is a concern] | [What to do] |
| [Risk 2] | 🟡 Medium | [Evidence] | [Action] |
| [Risk 3] | 🟢 Low | [Evidence] | [Monitor] |

---

## Competitive Position

**Current Standing:** [Ahead / Behind / Even / Unknown]

**Our Advantages:**
1. [Advantage with evidence]
2. [Advantage]

**Their Advantages:**
1. [Competitor strength]
2. [Strength]

**Battleground:** [Where the decision will be made — the criteria where both solutions compete]

---

## Win Plan

### This Week
1. **[Action]** — [Owner] — [Why this matters now]
2. **[Action]** — [Owner] — [Rationale]

### Next 2 Weeks
1. **[Action]** — [Owner]
2. **[Action]** — [Owner]

### Before Close
1. **[Milestone that must happen]**
2. **[Milestone]**

---

## Questions to Answer

These are the unknowns that could make or break this deal:

1. [Critical question and how to get the answer]
2. [Question]
3. [Question]

---

## Recommendation

**Confidence Level:** [High / Medium / Low]
**Assessment:** [2-3 sentence honest assessment of where this deal stands and what it will take to win]
```

---

## Coaching Elements

When a manager is running the deal review:

I'll include coaching questions the manager can ask the rep:
1. "Walk me through the decision process — who signs, and what happens between now and signature?"
2. "If we lost this deal, what would be the reason?"
3. "What has the champion done to sell internally for us?"
4. "What does the economic buyer care about that we haven't addressed?"

---

## Tips

1. **Be brutally honest** — The value of a deal review is facing reality, not confirming optimism
2. **Focus on what you can control** — Don't dwell on competitor moves; focus on your actions
3. **Test your champion** — If they haven't done anything for you internally, they're not a champion
4. **Time-bound your plan** — "Soon" isn't an action. Every task needs a date and owner.
