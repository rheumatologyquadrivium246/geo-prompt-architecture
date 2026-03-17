---
name: geo-prompt-architecture
description: Use when the user wants to generate, structure, score, or audit GEO monitoring prompts for a client. Trigger when building prompt sets from a website, brand, market, customer, product lines, and competitors; when balancing non-brand, comparison, and brand-defense prompts; or when turning AI visibility monitoring results into prompt and content optimization actions.
---

# GEO Prompt Architecture

Build GEO prompt systems that fit the client’s real business, not generic keyword lists.

## Overview

Use this skill to generate and audit AI visibility monitoring prompts for GEO programs. It turns a client brief into a prompt architecture across non-brand discovery, competitor comparison, and brand defense, then helps translate monitoring results into concrete optimization actions.

When the work needs structured product inputs or outputs, use the JSON schemas in `schemas/`.
When the client model is unclear or highly verticalized, use the examples in `examples/` and the playbooks in `references/`.

## Best For

- GEO software teams onboarding new clients
- GEO agencies building prompt sets at scale
- operators who need better prompt coverage by product line and funnel stage
- teams that want to rebalance prompt libraries away from brand-heavy bias
- teams that want monitoring prompts tied to later content and asset optimization

## Start With

```text
Use $geo-prompt-architecture to generate GEO monitoring prompts for this client.
```

```text
Use $geo-prompt-architecture to review this prompt set and rebalance brand vs non-brand prompts.
```

```text
Use $geo-prompt-architecture to turn these monitoring results into prompt and content recommendations.
```

## External Access And Minimum Credentials

This skill can work from a pasted brief, screenshots, exports, or a website URL.

- no private credentials are required for basic prompt generation or review
- live browsing is helpful when the client website, product lines, or competitor overlap must be validated
- do not assume access to analytics, Search Console, CRM, AI monitoring dashboards, or private docs unless explicitly provided

## Core Model

Always frame GEO prompts as a three-layer system:

1. `Non-brand discovery`
   Users do not know the brand yet. These prompts measure whether the brand can enter new answer spaces.
2. `Competitor comparison`
   Users are comparing brands, alternatives, or solution routes. These prompts measure competitive visibility.
3. `Brand defense`
   Users already know the brand and are validating fit, quality, pricing, sizing, shipping, returns, or worth. These prompts measure narrative control and decision-stage performance.

Default target mix:

- `60-70%` non-brand discovery
- `20-25%` competitor comparison
- `10-20%` brand defense

Do not let brand prompts dominate unless the user explicitly asks for a brand-defense-only set.

## Workflow

### 1. Reconstruct the client model

Before generating prompts, identify:

- business model
- market and language
- target customer
- core product lines
- conversion path
- key competitors
- weak AI surfaces, if provided

Useful business-model labels:

- SaaS / software
- ecommerce / DTC
- services / consultancy
- marketplace / aggregator
- content / media

If inputs are incomplete, infer carefully and label the inference.

If the user wants a standard onboarding shape, use [schemas/client-brief.schema.json](schemas/client-brief.schema.json).

If the business model is ambiguous, read [references/vertical-templates.md](references/vertical-templates.md) and compare against the sample cases in:

- [examples/trip-com-consumer-travel-marketplace.md](examples/trip-com-consumer-travel-marketplace.md)
- [examples/movinghead-stage-lighting.md](examples/movinghead-stage-lighting.md)

### 2. Map the funnel

Prompt sets must cover the funnel, not just high-intent terms:

- `Problem awareness`
- `Solution education`
- `Category evaluation`
- `Brand comparison`
- `Purchase decision`
- `Use / implementation / expansion`

Read [references/prompt-framework.md](references/prompt-framework.md) when you need the full generation framework.

### 3. Generate prompt sets by product line

When the user gives multiple product lines, generate a prompt set for each product line. Keep the layers separate:

- non-brand discovery prompts
- competitor comparison prompts
- brand defense prompts

Prompt rules:

- write natural-language user questions, not SEO fragments
- prefer prompts that fit AI conversations and recommendation flows
- include scenarios, constraints, audiences, budgets, regions, or channels when useful
- avoid low-value navigational brand variants

### 4. Add GEO judgment, not just prompts

For each prompt, include enough structure to make the set operational. Default fields:

- prompt
- layer
- funnel stage
- category
- product line
- target customer
- business value
- GEO priority
- monitoring value
- likely answer-entry mode
- why it matters

If the user wants a compact output, keep the fields but shorten the explanations.

If the user wants a product-ready response shape, use:

- [schemas/prompt-set-output.schema.json](schemas/prompt-set-output.schema.json)
- [schemas/prompt-scorecard.schema.json](schemas/prompt-scorecard.schema.json)

### 5. Audit and rewrite existing prompt sets

When reviewing an existing prompt list, do not regenerate everything by default. For each prompt:

- keep
- optimize
- downgrade
- delete
- replace

Common failure modes:

- too many brand prompts
- no comparison prompts
- no true non-brand discovery prompts
- off-funnel or synthetic phrasing
- prompts that fit search engines better than AI answers
- prompts that mismatch the client’s real product line or market

### 6. Reverse-optimize from monitoring results

When the user brings AI monitoring results, use them to improve both content and the prompt library.

Track at least:

- was the brand mentioned?
- how was it mentioned?
- which brands replaced it?
- what source types were cited?
- what loss reason best explains the miss?

Then propose:

- content actions
- page / asset actions
- evidence / entity actions
- prompt-set changes

Read [references/reverse-optimization.md](references/reverse-optimization.md) when you need the loss-reason model or the reverse-optimization loop.
Read [references/scoring-model.md](references/scoring-model.md) when the user wants prompt-set QA, scorecards, or benchmark-style review.

## Output Patterns

Default output order:

1. client model summary
2. prompt strategy by layer
3. prompt set by product line
4. priority prompts
5. optional reverse-optimization actions

When auditing, prefer tables like:

| Original | Action | Final | Reason |
|---|---|---|---|
| Prompt A | Keep | Prompt A | Fits the product line and funnel |
| Prompt B | Optimize | Better Prompt B | Original is too generic or too brand-heavy |
| Prompt C | Delete | — | Low monitoring value |

## Guardrails

- Do not treat prompt generation as generic keyword research.
- Do not over-index on brand terms.
- Do not collapse every prompt into bottom-funnel buying language.
- Do not invent product lines, channels, or competitors without labeling the inference.
- Do not assume every prompt should become an article; some should map to category pages, comparison pages, FAQs, reviews, or marketplace listings.
- When the user asks for monitoring prompts, bias toward prompts that can reveal visibility movement over time.
- Do not apply an ecommerce prompt pattern to a marketplace, SaaS, or industrial manufacturer without checking business-model fit first.
