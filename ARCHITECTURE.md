# Architecture

This document explains **why** ShaMstack is built the way it is. For setup and commands, see README.md.

## The Core Idea

ShaMstack gives your AI assistant a persistent marketing team with nine specialized roles. The key insight: marketing isn't one task — it's a coordinated system of strategy, creation, distribution, and optimization. Just as gstack separates CEO/EM/QA roles for engineering, ShaMstack separates CMO/Strategist/Copywriter/SEO/Social/Email/Analytics/Competitor/Brand for marketing.

```
┌─────────────────────────────────────────────────────────┐
│                    ShaMstack Core                        │
│  ┌─────────────────────────────────────────────────┐   │
│  │              Orchestrator (Workflow Engine)      │   │
│  │  • Manages agent handoffs                       │   │
│  │  • Enforces tiered automation rules             │   │
│  │  • Maintains persistent state & memory          │   │
│  └─────────────────────────────────────────────────┘   │
│                         │                                │
│  ┌─────────┬─────────┬─────────┬─────────┬─────────┐   │
│  │  CMO    │Strategist│Copywriter│  SEO   │ Social  │   │
│  └─────────┴─────────┴─────────┴─────────┴─────────┘   │
│  ┌─────────┬─────────┬─────────┬─────────┐             │
│  │  Email  │Analytics│Competitor│ Brand   │             │
│  └─────────┴─────────┴─────────┴─────────┘             │
└─────────────────────────────────────────────────────────┘
                         │
         ┌───────────────┼───────────────┐
         │               │               │
    ┌────▼────┐     ┌────▼────┐     ┌────▼────┐
    │  CMS    │     │  CRM    │     │Analytics│
    │WordPress│     │HubSpot  │     │  GA4    │
    └─────────┘     └─────────┘     └─────────┘
```

## Why Role-Based Agents

### The Problem with Generic Marketing AI

Most marketing AI tools are generalists. They try to do everything: write copy, suggest strategy, analyze data, schedule posts. The result is mediocre output across all dimensions because:

1. **Context dilution** — Strategy requires business model understanding. Copy requires brand voice. Analytics requires statistical reasoning. One context window can't excel at all three.
2. **No accountability** — When output is bad, who's responsible? A generic AI has no defined role or KPIs.
3. **No specialization** — Great SEO requires different expertise than great social media. Great email requires different expertise than great strategy.

### The ShaMstack Solution

Each agent has:
- **Defined role** — Clear boundaries on what they do (and don't do)
- **Specific KPIs** — Measurable success criteria
- **Decision authority** — Autonomy within their domain
- **Handoff protocols** — Standardized inputs and outputs

Example: The CMO Agent doesn't write copy. The Copywriter Agent doesn't set strategy. The Brand Guardian doesn't distribute content. Clear boundaries prevent context dilution.

## Workflow Orchestration

### gstack Uses Slash Commands (User-Triggered)

In gstack, the user types `/plan-ceo-review`, then `/plan-eng-review`, then `/ship`. Each command is explicit.

### ShaMstack Uses Workflow Triggers (System-Triggered)

Marketing workflows are more continuous. ShaMstack automates handoffs:

```
[Strategist] → brief → [Copywriter] → draft → [SEO] → optimized → [Brand] → approved → [Publish]
                                                                        ↓
                                                    [Social] + [Email] ← auto-triggered
```

The user approves strategy and major campaigns. The agents handle the rest.

## Tiered Automation

Not all content deserves equal effort. ShaMstack uses three tiers:

| Tier | Content Type | Workflow | Human Review |
|------|--------------|----------|-------------|
| **Tier 1** | Flagship campaigns, pillar content | Full agent chain | CMO + Brand approve |
| **Tier 2** | Standard blog posts, emails | Standard chain | Strategist approves topics |
| **Tier 3** | Social snippets, quick updates | Copywriter → Social | 10% Brand spot-checks |

This matches how real marketing teams operate. Senior strategists focus on flagship content. Junior marketers (or AI) handle routine updates.

## Closed-Loop Optimization

### The Problem

Most marketing tools are open-loop. You create content, publish it, and... nothing. No feedback to strategy. No learning from performance.

### The ShaMstack Solution

The Analytics Agent continuously feeds performance data back to the CMO and Strategist:

```
[Content Published] → [Analytics tracks] → [30 days later] → [Report to CMO]
                                                                    ↓
                                          [Adjusts Q2 strategy based on Q1 results]
```

This creates a learning system. The team gets smarter over time.

## Persistent State

### What Persists

- **Brand Voice** — Examples, tone rules, forbidden phrases
- **Performance History** — What content worked, what didn't
- **Audience Segments** — CRM-derived personas and behaviors
- **Campaign Archive** — All past campaigns with results

### Why It Matters

Without persistent state, every session starts from zero. The agent forgets your brand voice. It doesn't know last quarter's winner. It can't learn.

ShaMstack stores state externally (vector database + PostgreSQL) so agents have institutional memory across sessions.

## Integration Architecture

ShaMstack connects to your existing marketing stack via APIs:

```
[ShaMstack Agents] ←→ [Integration Layer] ←→ [External APIs]
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
   ┌────▼────┐          ┌────▼────┐          ┌────▼────┐
   │  REST   │          │  OAuth  │          │Webhooks │
   │  APIs   │          │  Auth   │          │ (real-time)
   └─────────┘          └─────────┘          └─────────┘
```

Not all integrations are required. Start with what you use (e.g., WordPress + GA4 + LinkedIn). Add more as needed.

## Security Model

### API Credentials

- Stored in environment variables or secret manager
- Never committed to repo
- Per-agent scoping (Social agent doesn't need CRM access)

### Content Approval

- Tier 1 content: Human approval required before publish
- Brand Guardian can block non-compliant content
- Audit log of all published content

### Data Privacy

- Customer data from CRM is processed, not stored
- PII is masked in analytics reports
- Compliance with GDPR/CCPA via data minimization

## Comparison: gstack vs ShaMstack

| Dimension | gstack (Engineering) | ShaMstack (Marketing) |
|-----------|---------------------|----------------------|
| **Workflow** | Linear: plan → build → review → ship | Cyclical: strategy → create → distribute → analyze → adjust |
| **Triggers** | User types slash commands | Workflow-triggered handoffs |
| **Output** | Code, tests, docs | Content, posts, emails, reports |
| **Feedback** | Test pass/fail | Engagement, conversions, revenue |
| **Integrations** | GitHub, CI/CD, deploys | CMS, CRM, social, email, analytics |
| **Cadence** | Per-PR, per-sprint | Continuous, always-on |

---

**ShaMstack is a marketing team, not a marketing tool.**
