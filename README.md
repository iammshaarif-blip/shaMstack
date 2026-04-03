# ShaMstack

> A role-based multi-agent marketing team, built on GitHub, with pre-defined specialist roles, workflow orchestration, and closed-loop optimization.

**ShaMstack** transforms your AI assistant into a virtual marketing team — a CMO who sets strategy, a Content Strategist who identifies opportunities, a Copywriter who creates at scale, an SEO Specialist who optimizes for search, a Social Media Manager who distributes across platforms, an Email Marketer who personalizes sequences, an Analytics expert who tracks performance, a Competitor Intelligence agent who monitors the market, and a Brand Guardian who ensures quality.

Nine specialists. All slash commands. All Markdown. All free. MIT license.

---

## Quick Start

1. **Clone ShaMstack** (30 seconds)
2. **Run `/cmo`** — Define your business goals and target audience
3. **Run `/strategist`** — Generate quarterly content strategy
4. **Run `/copywriter`** — Create content at scale
5. **Run `/seo`** — Optimize for search visibility
6. **Run `/social`** — Distribute across platforms
7. **Stop there.** You'll know if this is for you.

---

## Install

**Requirements:** Claude Code (or compatible AI agent), Git, Node.js or Bun

### Step 1: Install ShaMstack

```bash
git clone --single-branch --depth 1 https://github.com/iammsha/shamstack.git ~/.claude/skills/shamstack
cd ~/.claude/skills/shamstack
./setup
```

### Step 2: Add to your repo (optional, for teams)

```bash
cp -Rf ~/.claude/skills/shamstack .claude/skills/shamstack
rm -rf .claude/skills/shamstack/.git
cd .claude/skills/shamstack
./setup
```

---

## The Nine Marketing Agents

| Agent | Command | Purpose |
|-------|---------|---------|
| **CMO** | `/cmo` | Strategy, planning, budget allocation |
| **Content Strategist** | `/strategist` | Topic selection, briefs, calendar |
| **Copywriter** | `/copywriter` | Content creation, brand voice |
| **SEO Specialist** | `/seo` | Search optimization, AEO |
| **Social Media Manager** | `/social` | Multi-platform distribution |
| **Email Marketer** | `/email` | Segmentation, personalization |
| **Analytics** | `/analytics` | Performance tracking, ROI |
| **Competitor Intelligence** | `/competitor` | Market monitoring, alerts |
| **Brand Guardian** | `/brand` | Quality control, compliance |

---

## The Marketing Sprint

**Strategy → Ideation → Creation → Optimization → Distribution → Analytics → Feedback**

```
/cmo         → Sets quarterly strategy
/strategist  → Generates topic briefs
/copywriter  → Produces first drafts
/seo         → Optimizes for search
/brand       → Approves for compliance
[publish]
/social      → Creates platform posts
/email       → Adds to newsletter
/analytics   → Tracks performance
```

---

## Architecture

ShaMstack is built on the same principles as gstack (Garry Tan's engineering agent system), but specialized for marketing workflows:

- **Role-based agents** — Each agent has distinct responsibilities and KPIs
- **Orchestrated handoffs** — Agents pass work sequentially
- **Persistent state** — Brand voice, performance history persist
- **Closed-loop optimization** — Analytics feeds back to strategy

---

## License

MIT License — Fork it. Improve it. Make it yours.

---

**Built for marketing teams who want to ship like a department of twenty.**
