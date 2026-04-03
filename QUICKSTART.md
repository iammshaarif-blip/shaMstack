# ShaMstack Quick Start

Get your marketing AI team running in 5 minutes.

---

## Step 1: Clone ShaMstack

```bash
git clone --single-branch --depth 1 https://github.com/iammsha/shamstack.git ~/.claude/skills/shamstack
cd ~/.claude/skills/shamstack
```

---

## Step 2: Configure Your First Agent

Start with the CMO Agent to set your strategy:

```
/cmо

I want to set up my content marketing strategy.

Business goals: [Your ARR target, growth rate]
Target audience: [Your ICP - role, company size, industry]
Budget: [Monthly marketing budget]
Current stage: [Seed, Series A, growth, etc.]
```

The CMO Agent will ask clarifying questions, then generate your quarterly strategy.

---

## Step 3: Generate Your First Content Plan

```
/strategist

Based on the CMO strategy, generate topic briefs for this month.
Focus on: [Specific content pillar or let AI decide]
```

The Strategist will identify high-opportunity topics with keyword data and briefs.

---

## Step 4: Create Your First Piece of Content

```
/copywriter

Write a first draft for: [Topic from Strategist brief]
Tone: [Reference the brand voice guidelines]
```

The Copywriter generates the full draft with brand voice consistency.

---

## Step 5: Optimize and Publish

```
/seo

Optimize this draft for search: [paste draft or reference]
Target keyword: [From brief]

/brand

Review for brand compliance: [optimized draft]

[Publish to your CMS]
```

---

## Step 6: Distribute

```
/social

Create posts for: [published URL]
Platforms: LinkedIn, X, Threads

/email

Add this to the weekly newsletter: [published URL]
```

---

## Step 7: Track Performance

```
/analytics

Show me performance for: [content/campaign]
Time period: Last 30 days
```

---

## Your First Week

| Day | Action |
|-----|--------|
| 1 | Run `/cmo` — Set quarterly strategy |
| 2 | Run `/strategist` — Generate topic briefs |
| 3 | Run `/copywriter` — Create 2-3 drafts |
| 4 | Run `/seo` + `/brand` — Optimize and approve |
| 5 | Publish + `/social` + `/email` — Distribute |
| 7 | Run `/analytics` — Check initial performance |

---

## Configuration Files

Edit these to customize ShaMstack:

- `brand/voice_guidelines.md` — Your brand voice rules
- `brand/cmo_config.json` — Business goals and budget (create after running `/cmo`)
- `workflows/content_creation.yaml` — Workflow steps and approval gates

---

## Need Help?

- See [README.md](./README.md) for full documentation
- See [ARCHITECTURE.md](./ARCHITECTURE.md) for how ShaMstack works
- Open an issue on GitHub for bugs or feature requests

---

**You now have a 9-person marketing AI team. Start using it.**
