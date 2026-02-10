# Connectors

## How tool references work

Plugin files use `~~category` as a placeholder for whatever tool the user connects in that category. For example, `~~CRM` might mean Salesforce, HubSpot, or any other CRM with an MCP server.

Plugins are **tool-agnostic** — they describe workflows in terms of categories (CRM, chat, email, etc.) rather than specific products. The `.mcp.json` pre-configures specific MCP servers, but any MCP server in that category works.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
|----------|-------------|-----------------|---------------|
| CRM | `~~CRM` | HubSpot, Salesforce | Close, Pipedrive, Copper, Freshsales |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Knowledge Base | `~~knowledge base` | Notion | Confluence, Guru, Coda, Slite |
| Meeting Transcription | `~~conversation intelligence` | Fireflies | Gong, Chorus, Otter.ai, Fathom |
| Data Enrichment | `~~data enrichment` | Clay, ZoomInfo | Apollo, Clearbit, Lusha, Cognism |
| Calendar | `~~calendar` | Microsoft 365 | Google Calendar |
| Email | `~~email` | Microsoft 365 | Gmail, Outreach, Salesloft |
| CS Platform | `~~CS platform` | Gainsight | ChurnZero, Vitally, Totango, Catalyst |
| Project Management | `~~project management` | Asana | Jira, Linear, Monday.com |

## What each connector enables

### CRM (Highest Impact)

The single most impactful connector. Enables:

- **Deal reviews:** Pull live deal data instead of manual input
- **Win/loss analysis:** Analyze pipeline data automatically
- **Qualification:** Pre-fill MEDDIC scores from CRM fields
- **Pipeline intelligence:** Real-time pipeline health, risk detection, coaching signals
- **Expansion plays:** Usage data and renewal dates for upsell timing
- **Rep dashboards:** Activity metrics, quota attainment, deal velocity per rep
- **Forecast:** Weighted pipeline and commit/upside breakdown
- **Scheduled automations:** Pipeline digest and deal signals run against live data

### Knowledge Base

Store and retrieve enablement content:

- **Playbooks:** Reference existing playbooks when building new ones
- **Battle cards:** Check if battle cards already exist before creating
- **Case studies:** Pull customer stories into proposals and talk tracks
- **Content health:** Scan the full content library for freshness scoring
- **Campaign-to-field:** Access campaign briefs and marketing materials to translate

### Conversation Intelligence

Analyze real calls for coaching and insights:

- **Call reviews:** Pull transcripts automatically instead of copy-paste
- **Coaching:** Identify patterns across many calls per rep
- **Win/loss:** Include call quality in deal analysis
- **Discovery quality:** Score discovery calls against best practice frameworks
- **Rep profiles:** Build skill assessments from actual call performance

### Chat

Access team knowledge, deliver briefings, and surface signals:

- **Battle cards:** Find competitive intel shared in team channels
- **Playbooks:** Capture tribal knowledge from team discussions
- **Coaching:** Reference internal discussions about deals
- **Competitive pulse:** Deliver weekly briefings to sales channels
- **Pipeline digest:** Post weekly digest to team channels
- **Deal signals:** Surface deal-related conversations and blockers
- **Handoffs:** Notify receiving team when handoff documents are ready

### Data Enrichment

Research prospects, companies, and market context:

- **Buyer personas:** Enrich personas with real firmographic and technographic data
- **Battle cards:** Research competitor details, tech stacks, and customer logos
- **Proposals:** Add prospect-specific context and personalization
- **Account research:** Company size, funding, tech stack, org charts
- **Expansion signals:** Hiring patterns, funding events, company news

### Calendar + Email

Context for meetings, outreach, and follow-ups:

- **Discovery prep:** Know who you're meeting and their prior correspondence
- **Onboarding:** Schedule training sessions and manager check-ins
- **Coaching:** Track follow-through on action items
- **Campaign-to-field:** Deploy email templates through existing outbound tools
- **Handoffs:** Schedule kickoff meetings as part of transition workflows

### CS Platform

Customer success data for retention and expansion:

- **Expansion playbook:** Health scores, usage trends, and adoption metrics to time upsell conversations
- **Handoff builder:** CS teams get full context when deals close
- **Renewal strategy:** Risk flags and renewal timing from CS data
- **Pipeline intelligence:** Existing customer pipeline tracked alongside new business
- **Content health:** Track which enablement content impacts customer outcomes

### Project Management

Track enablement initiatives and remediation tasks:

- **Content audit:** Create remediation tasks directly from audit findings
- **Onboarding plans:** Track new hire progress through milestones
- **Content health:** Auto-create refresh tasks when content goes stale
- **Campaign-to-field:** Track field readiness rollout across teams

## Connector Priority

If you're connecting tools for the first time, here's the recommended order:

1. **CRM** — Unlocks 80% of the value. Pipeline data powers everything.
2. **Chat** — Enables briefing delivery and captures team intelligence.
3. **Knowledge Base** — Content health and self-healing require knowing what content exists.
4. **Conversation Intelligence** — Transforms coaching from opinion-based to data-driven.
5. **Data Enrichment** — Enriches research, personas, and competitive analysis.
6. **CS Platform** — Critical for expansion and renewal workflows.
7. **Calendar + Email** — Contextual prep and outbound deployment.
8. **Project Management** — Task tracking for remediation and enablement programs.
