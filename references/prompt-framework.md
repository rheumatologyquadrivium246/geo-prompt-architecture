# Prompt Framework

Use this reference when generating a fresh GEO monitoring prompt set.

## 1. Inputs to extract first

Before writing prompts, normalize these inputs:

- website
- brand
- market
- target customer
- product lines
- competitors
- weak AI surfaces
- optional context: pricing, channels, audience segments, use cases, regions, existing assets

## 2. Three-layer prompt architecture

### Non-brand discovery

Use for new-answer-space coverage.

Best for:

- category discovery
- use-case discovery
- scenario and pain-point prompts
- educational prompts
- product-line prompts without the brand

Typical output share: `60-70%`

### Competitor comparison

Use for competitive visibility.

Best for:

- `brand vs competitor`
- `best alternatives to competitor`
- `which brand is better for [use case]`
- competitor-cluster prompts built around user-provided rivals

Typical output share: `20-25%`

### Brand defense

Use for narrative control and lower-funnel monitoring.

Best for:

- `is [brand] good quality`
- `does [brand] run true to size`
- `should I buy [brand] on Amazon or the official site`
- `is [brand] good for [use case]`
- `[brand] vs [competitor]`

Typical output share: `10-20%`

Avoid low-value brand navigation prompts unless the user explicitly wants them.

## 3. Funnel mapping

Every strong prompt set should cover:

1. `Problem awareness`
2. `Solution education`
3. `Category evaluation`
4. `Brand comparison`
5. `Purchase decision`
6. `Use / implementation / expansion`

Recommended bias by layer:

- non-brand discovery: stages 1-3
- competitor comparison: stages 3-5
- brand defense: stages 4-6

## 4. Prompt categories

Useful categories:

- problem-identification
- solution-exploration
- category-search
- scenario / use-case
- audience / segment
- competitor comparison
- decision / evaluation
- brand validation
- buying / channel
- usage / styling / implementation

## 5. Prompt quality rules

Strong prompts:

- sound like real questions asked to AI tools
- include useful context
- reveal visibility, preference, or replacement behavior
- map clearly to a product line or business goal

Weak prompts:

- are just keyword fragments
- are generic navigational brand queries
- repeat the same phrasing with tiny edits
- have no monitoring or action value

## 6. Recommended fields

For structured outputs, use:

- prompt
- layer
- funnel_stage
- category
- product_line
- target_customer
- business_value
- geo_priority
- monitoring_value
- answer_entry_mode
- why_it_matters

Useful `answer_entry_mode` values:

- direct recommendation
- candidate list
- comparison target
- alternative option
- case-study citation
- methodology citation
- review / rating citation

## 7. Priority rules

Prioritize prompts that are:

- commercially meaningful
- likely to change content or asset decisions
- likely to show visibility movement over time
- specific enough to reveal competitive substitution
- aligned to the user’s weak AI surface
