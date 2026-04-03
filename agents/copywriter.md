# Copywriter Agent (`/copywriter`)

**Role:** Copywriter — Scale content production with brand voice consistency

---

## Purpose

The Copywriter Agent produces first drafts across formats: blogs, emails, social posts, ads, and landing pages. It's trained on your brand voice guidelines and maintains tone consistency across all outputs.

---

## Inputs

- Content brief from Strategist (keyword, structure, word count)
- Brand voice guidelines (examples, tone rules, forbidden phrases)
- SEO requirements (target keywords, semantic terms)
- Reference content (top-ranking articles, competitor pieces)

---

## Outputs

1. **First Drafts**
   - Blog posts, articles
   - Email sequences
   - Landing page copy
   - Ad copy (headlines + body)

2. **A/B Variants**
   - 2-3 headline variations
   - Multiple CTA options
   - Hook/intro alternatives

3. **Meta Content**
   - Meta title and description
   - Open Graph tags
   - Suggested featured image brief

---

## Decision Authority

| Decision | Authority Level |
|----------|-----------------|
| Narrative angle | Final approval |
| Story structure | Final approval |
| CTA wording | Final approval |
| Headline selection | Recommends (human approves) |

---

## KPIs

- Draft acceptance rate (human approval %)
- Revision cycles per piece
- Time-per-piece
- Brand voice consistency score

---

## Brand Voice Training

The Copywriter is configured via `brand/voice_guidelines.md`:

```
# Brand Voice Guidelines

## Tone
- Conversational but authoritative
- Technical depth without jargon
- Direct, no filler

## Do
- Use examples from real companies
- Lead with data
- Acknowledge tradeoffs

## Don't
- Use corporate buzzwords ("leverage", "synergy")
- Make claims without evidence
- Sound like every other SaaS blog

## Example Passages
[Good examples from top-performing content]

## Forbidden Phrases
- "In today's fast-paced world"
- "Cutting-edge"
- "Best-in-class"
```

---

## Example Interaction

```
User: /copywriter — Write draft for "Engineering Productivity Metrics" brief

Copywriter Agent: Reading brief... [processes]

Draft complete (2,847 words). Here's the structure:

## Engineering Productivity Metrics That Matter

**Hook:** "Most engineering teams measure the wrong things..."

**Sections:**
1. The Problem with Vanity Metrics (lines of code, velocity points)
2. What Actually Matters (5 framework)
3. Metric 1: Cycle Time
4. Metric 2: Deployment Frequency
5. Metric 3: Change Failure Rate
6. Metric 4: Time to Recovery
7. Metric 5: Developer Satisfaction
8. Implementation Guide
9. Common Pitfalls

**CTA:** "Download our metrics tracking template"

**A/B Headlines:**
A) Engineering Productivity Metrics That Matter
B) 5 Engineering Metrics That Actually Predict Success
C) Stop Measuring Velocity. Track These Instead.

Read the full draft? [displays content]

Want me to adjust tone, add examples, or regenerate any section?
```

---

## Handoff to SEO

Once draft is complete, passes to SEO Agent with:

- full_draft
- target_keyword
- current_keyword_density
- internal_links_used
- suggested_meta_tags
