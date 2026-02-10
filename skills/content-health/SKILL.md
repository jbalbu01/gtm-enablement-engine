---
name: content-health
description: Self-healing content monitoring system that tracks freshness of all enablement assets, detects when content is stale, and triggers updates automatically. Use this skill whenever checking if enablement content is current, when a product change happens and assets need updating, when competitive landscape shifts, or when win rates drop (which may signal stale playbooks). Also trigger proactively when any enablement asset is older than 30 days, when a competitor makes news, when pricing changes, or when the user says "is our content up to date", "what needs refreshing", "we just launched a new feature", or "competitor just announced X". This is the self-healing engine that Matthew describes — content that knows when it's decaying.
---

# Content Health Monitor

The "self-healing" layer of the enablement system. Traditional enablement creates content once and hopes someone remembers to update it. This system actively monitors every asset, detects decay signals, and either auto-refreshes or flags content for human review.

## The Decay Problem

Enablement content has a half-life:
- **Battle cards** decay when competitors ship new features or change pricing (~30 days)
- **Playbooks** decay when win rates change or process evolves (~90 days)
- **Proposals** decay when product or pricing changes (~immediate)
- **Discovery guides** decay when ICP shifts or new personas emerge (~60 days)
- **ROI models** decay when benchmarks or pricing change (~90 days)
- **Buyer personas** decay when market conditions shift (~120 days)

If your battle card is 6 months old but your competitor shipped 3 features since then, the rep using that card is fighting with outdated intel.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                    CONTENT HEALTH                                  │
├─────────────────────────────────────────────────────────────────┤
│  MONITORING LAYERS                                                │
│                                                                   │
│  Layer 1: TIME-BASED                                              │
│  • Track age of every asset in content-registry.md               │
│  • Flag when assets exceed their freshness threshold              │
│  • Escalate overdue assets in weekly health reports              │
│                                                                   │
│  Layer 2: EVENT-DRIVEN                                            │
│  • Product change → Flag all assets referencing old info         │
│  • Competitor news → Flag related battle cards                   │
│  • Lost deal → Check if loss reason indicates stale content      │
│  • Win rate drop → Investigate if playbook needs refresh         │
│                                                                   │
│  Layer 3: OUTCOME-BASED                                           │
│  • Track which content gets used and which doesn't               │
│  • Identify assets with declining effectiveness                   │
│  • Surface "zombie content" that exists but nobody uses          │
│                                                                   │
│  RESPONSE                                                         │
│  • Auto-refresh: Update with new data (competitive intel, etc.)  │
│  • Flag for review: Alert human when judgment needed             │
│  • Propagate changes: When one thing changes, update downstream  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Content Registry

Every enablement asset is tracked in `memory/content-registry.md`:

```markdown
| Asset | Type | Created | Last Updated | Freshness Score | Max Age | Dependencies | Auto-Refresh? |
|-------|------|---------|-------------|-----------------|---------|-------------|---------------|
| Battle Card: CompA | battle-card | 2026-01-15 | 2026-01-15 | 🟢 95/100 | 30 days | competitors.md | Yes |
| Enterprise Playbook | playbook | 2025-12-01 | 2026-01-10 | 🟡 62/100 | 90 days | product.md, icp.md | No — needs review |
| SDR Discovery Guide | discovery | 2025-11-15 | 2025-11-15 | 🔴 28/100 | 60 days | icp.md | Yes |
```

### Freshness Score Calculation

```
Base Score: 100 (at creation/update)

Decay factors:
- Time: -1 point per day beyond 50% of max age
- Event-triggered: -20 points per relevant product/competitor change
- Outcome-based: -10 points if win rate in related deals drops >5%
- Usage: -15 points if asset hasn't been referenced in 30 days

Freshness thresholds:
🟢 70-100: Current — no action needed
🟡 40-69:  Aging — schedule refresh within 2 weeks
🔴 0-39:   Stale — refresh immediately or retire
```

---

## Decay Triggers

### Product Changes
When the user reports a product change (new feature, pricing update, positioning shift):

1. Scan content-registry.md for all assets with `product.md` as a dependency
2. Assess which assets are directly affected
3. For each affected asset:
   - If auto-refresh is possible → regenerate with updated info
   - If judgment needed → flag for review with specific change context
4. Update content-registry.md with new freshness scores
5. Log the propagation in changelog.md

**Example:**
> User: "We just raised our pricing by 15%"
> System: "Updated product.md. Flagging 4 assets for refresh: ROI Calculator (auto-refreshing now), Proposal Template (needs your review — value framing may change), Battle Card: CompA (auto-refreshing pricing comparison), Enterprise Playbook (pricing section needs manual update)."

### Competitor Changes
When competitive news is detected (via scheduled monitoring or user input):

1. Identify which competitor
2. Update competitors.md with new intel
3. Flag all battle cards for that competitor
4. Check if any playbooks reference this competitor's positioning
5. Assess if deal-patterns.md needs updating

### Deal Outcomes
When a deal is won or lost:

1. Check if the outcome reveals a content gap
2. If loss reason = "competitor had feature we didn't address" → Flag battle card
3. If loss reason = "prospect didn't see enough value" → Flag ROI calculator and proposal template
4. If win rate drops below threshold → Flag playbook for review

---

## Health Report

Generated on demand or via scheduled automation:

```markdown
# Enablement Content Health Report

**Date:** [Today]
**Total Assets:** [N]
**Health Distribution:** 🟢 [N] current | 🟡 [N] aging | 🔴 [N] stale

---

## Immediate Action Required (🔴 Stale)

| Asset | Age | Last Event | Recommended Action |
|-------|-----|-----------|-------------------|
| [Asset] | [X] days | [What triggered staleness] | [Refresh / Retire / Review] |

## Schedule Refresh (🟡 Aging)

| Asset | Freshness | Estimated Effort | Skill to Use |
|-------|-----------|-----------------|-------------|
| [Asset] | [Score]/100 | [Quick / Medium / Deep] | [battle-cards / playbook-builder / etc.] |

## Recently Refreshed

| Asset | Updated | By | Change |
|-------|---------|-----|--------|
| [Asset] | [Date] | [Auto / Manual] | [What changed] |

---

## Trends

- Content freshness trend: [Improving / Stable / Declining]
- Most frequently updated: [Asset] — [Why it changes often]
- Zombie content (exists but unused): [List]
- Missing content (gaps identified): [List]
```

---

## Change Propagation

When one piece of knowledge changes, the system traces downstream dependencies:

```
Product pricing changes
    ↓
├── ROI Calculator → Auto-refresh calculations
├── Proposal Template → Flag pricing section
├── Battle Card: CompA → Refresh pricing comparison
├── Playbook → Flag pricing objection section
└── Objection Library → Update "too expensive" responses
```

This is tracked via the Dependencies column in the content registry. Each asset declares what it depends on, and changes propagate through the dependency graph.

---

## Automation Integration

This skill works with scheduled shortcuts:

- **`/competitive-pulse`** → Feeds competitor intel into the decay engine
- **`/content-audit`** → Generates the full health report
- **Weekly automation** → Runs health check and sends summary

---

## Related Skills

- **gtm-memory** → Content registry lives in the memory system
- **battle-cards** → Most frequently refreshed asset type
- **playbook-builder** → Refreshes playbooks when patterns change
- **All content-generating skills** → Register their output in the content registry
