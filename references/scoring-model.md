# Scoring Model

Use this reference when the user wants to score, benchmark, or QA a prompt set.

The goal is not to reward bigger prompt lists. The goal is to reward prompt systems that are balanced, monitor-worthy, and useful for optimization.

## 1. Score Dimensions

Use a 100-point model by default.

### Layer balance: 20 points

Check whether the set roughly follows the intended mix:

- `60-70%` non-brand discovery
- `20-25%` competitor comparison
- `10-20%` brand defense

Score down when:

- brand prompts dominate
- there are no comparison prompts
- the set is almost entirely upper-funnel or lower-funnel

### Funnel coverage: 20 points

Check whether the set covers:

- problem awareness
- solution education
- category evaluation
- brand comparison
- purchase decision
- use / implementation / expansion

Score down when the set misses whole stages.

### Business-model fit: 20 points

Check whether the prompts fit the client’s real business model and conversion path.

Score down when:

- ecommerce phrasing is used for SaaS
- content-site prompts are used for industrial products
- service prompts are used for marketplaces

### Prompt quality: 15 points

Check whether prompts:

- sound like real AI questions
- avoid keyword-fragment phrasing
- avoid repetitive near-duplicates
- include useful context when needed

### Monitoring value: 15 points

Check whether prompts can reveal something useful over time.

Strong monitoring prompts:

- expose competitive substitution
- reveal whether the brand enters new answer spaces
- show branded trust or decision-stage shifts

### Actionability: 10 points

Check whether poor performance on a prompt would point to a real optimization action.

Examples:

- add a category page
- create a comparison page
- improve product-line entity language
- strengthen reviews or evidence

## 2. Suggested Output

Use these score buckets:

- `90-100`: strong, benchmark-worthy set
- `75-89`: usable but needs selective tuning
- `60-74`: weak in one or two structural areas
- `<60`: not reliable enough for serious GEO monitoring

## 3. Common Reasons A Set Scores Poorly

- too many branded prompts
- no real discovery prompts
- weak or missing competitor set
- no product-line grouping
- funnel collapse into one stage
- low monitoring value
- prompts that cannot map to any page or asset strategy

## 4. Suggested Output Fields

Use `schemas/prompt-scorecard.schema.json` when the user wants a structured scorecard.

Recommended fields:

- overall_score
- layer_balance_score
- funnel_coverage_score
- business_model_fit_score
- prompt_quality_score
- monitoring_value_score
- actionability_score
- top_findings
- keep_doing
- fix_next

## 5. Important Rule

Do not confuse `high search volume` with `high GEO monitoring value`.

A strong GEO prompt set should help the team understand:

- where the brand can grow
- where the brand is losing comparisons
- where the brand narrative is weak
- what to build next
