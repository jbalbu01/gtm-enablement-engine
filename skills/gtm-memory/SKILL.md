---
name: gtm-memory
description: Persistent intelligence layer that accumulates deal knowledge, competitive intel, product context, and team patterns over time — making every other skill smarter with use. This skill should ALWAYS be checked at the start of any GTM-related task. It reads from and writes to a structured knowledge base so that insights from one conversation carry into the next. Use this skill on every interaction that involves sales, marketing, CS, partnerships, or RevOps context. Also trigger proactively when the user shares deal outcomes, competitive intel, product updates, rep feedback, or customer insights — capture it even if they didn't ask you to.
---

# GTM Memory

The intelligence backbone of the sales enablement system. Every other skill reads from this memory and writes back to it, creating a compounding loop where the system gets smarter with every deal, call, and interaction.

## Why This Exists

Traditional enablement creates content and hopes people use it. This system learns from what actually happens in the field — which talk tracks win deals, which discovery questions reveal the most, which objections trip reps up, which competitors keep winning in specific segments — and feeds those insights back into every future interaction.

The result: a plugin that's meaningfully better on day 90 than day 1.

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                      GTM MEMORY                                   │
├─────────────────────────────────────────────────────────────────┤
│  KNOWLEDGE STORE (persists across sessions)                      │
│  📁 memory/                                                      │
│  ├── product.md        — Product details, features, pricing      │
│  ├── competitors.md    — Competitive landscape + intel log       │
│  ├── icp.md            — ICP definition + refinements over time  │
│  ├── deal-patterns.md  — Win/loss patterns, what works           │
│  ├── objections.md     — Objection library with effectiveness    │
│  ├── team.md           — Rep profiles, strengths, development    │
│  ├── content-registry.md — All enablement assets + freshness    │
│  └── changelog.md      — All updates with timestamps             │
├─────────────────────────────────────────────────────────────────┤
│  WORKING MEMORY (CLAUDE.md — always in context)                  │
│  • Current priorities and focus areas                            │
│  • Recent insights not yet integrated                            │
│  • Active deals requiring attention                              │
│  • Stale content flags                                           │
│  • Cross-references to memory/ files                             │
└─────────────────────────────────────────────────────────────────┘
```

---

## How It Works

### Reading (Before Any Task)

Before generating any enablement content, check relevant memory files:

1. **Building a battle card?** → Read `competitors.md` + `deal-patterns.md` + `objections.md`
2. **Prepping discovery?** → Read `icp.md` + `deal-patterns.md` + `team.md` (for rep's skill level)
3. **Coaching a rep?** → Read `team.md` (rep profile) + `deal-patterns.md`
4. **Building a proposal?** → Read `product.md` + `icp.md` + `competitors.md`
5. **Any task?** → Read `CLAUDE.md` for current context and priorities

This means a battle card built on day 90 incorporates 90 days of deal outcomes, competitive encounters, and field feedback — not just what the user told you in this one conversation.

### Writing (After Any Interaction)

After completing any GTM task, capture new intelligence:

```
Did we learn something new about:
✓ A competitor? → Update competitors.md
✓ What works in deals? → Update deal-patterns.md
✓ An objection and what beats it? → Update objections.md
✓ A rep's skill gap or strength? → Update team.md
✓ The product or pricing? → Update product.md
✓ The ICP or personas? → Update icp.md
✓ A new content asset was created? → Update content-registry.md
Always → Add timestamped entry to changelog.md
```

### Proactive Capture

When the user shares information casually — "we lost the Acme deal to Competitor X because of their API" — capture it even if they didn't ask you to. Say: "Got it — I've logged that competitive loss pattern. This will inform future battle cards and deal reviews."

---

## Memory File Formats

### product.md
```markdown
# Product Knowledge

**Last Updated:** [Date]

## Product Overview
[What we sell, in one paragraph]

## Key Features
| Feature | Description | Differentiator? |
|---------|-------------|----------------|
| ... | ... | Yes/No |

## Pricing
[Current pricing model and tiers]

## Recent Changes
| Date | Change | Impact on Selling |
|------|--------|------------------|
| ... | ... | ... |

## Value Propositions (Ranked by Effectiveness)
1. [VP that wins most often] — Win rate: [X]%
2. [VP2] — Win rate: [X]%
```

### competitors.md
```markdown
# Competitive Intelligence

**Last Updated:** [Date]

## [Competitor A]
**Last Intel:** [Date]
**Win Rate Against:** [X]%
**Key Differentiators:** [Theirs vs ours]

### Recent Intel
| Date | Source | Intel | Impact |
|------|--------|-------|--------|
| ... | Deal: [Name] | [What we learned] | [Updated battle card?] |

### What Beats Them
[Patterns from won deals]

### Where They Beat Us
[Patterns from lost deals]
```

### deal-patterns.md
```markdown
# Deal Patterns

**Last Updated:** [Date]
**Deals Analyzed:** [N]

## Win Patterns
1. [Pattern] — Confidence: [High/Med] — Evidence: [N] deals
2. ...

## Loss Patterns
1. [Pattern] — Confidence: [High/Med] — Evidence: [N] deals
2. ...

## Stage Conversion Insights
| Stage Transition | Success Factor | Failure Factor |
|-----------------|----------------|----------------|
| Discovery → Demo | [What works] | [What fails] |
| Demo → Proposal | ... | ... |

## Emerging Trends
[New patterns not yet confirmed]
```

### content-registry.md
```markdown
# Content Registry

All enablement assets with freshness tracking.

| Asset | Type | Created | Last Updated | Freshness | Trigger for Refresh |
|-------|------|---------|-------------|-----------|-------------------|
| [Battle Card: CompA] | battle-card | [Date] | [Date] | 🟢🟡🔴 | [Competitor news, lost deal] |
| [Playbook: Enterprise] | playbook | [Date] | [Date] | 🟢🟡🔴 | [Process change, win rate drop] |
```

---

## Initialization

When used for the first time:

1. Ask the user about their product, team, and current state
2. Create the `memory/` directory and seed each file with initial context
3. Create `CLAUDE.md` with working memory summary
4. Log initialization in `changelog.md`

On subsequent uses:
1. Read `CLAUDE.md` first (always in context)
2. Read relevant memory files based on the current task
3. After the task, update memory files with new learnings

---

## Compounding Loop

```
User interaction
    ↓
Read relevant memory → Better context → Higher quality output
    ↓
Capture new insights from the interaction
    ↓
Update memory files
    ↓
Next interaction starts with richer context
    ↓
Repeat (system gets smarter with every use)
```

This is what Matthew means by "infrastructure that compounds" — the plugin isn't just generating content, it's building an institutional knowledge base that makes every future interaction better.

---

## Related Skills

Every other skill in this plugin reads from and writes to GTM Memory:
- **battle-cards** → reads competitors.md, writes back competitive intel
- **deal-qualification** → reads deal-patterns.md, writes back deal outcomes
- **sales-coaching** → reads team.md, writes back skill assessments
- **content-health** → reads content-registry.md, flags stale assets
- **All skills** → read CLAUDE.md for current context
