# Example Output: Coofandy

This example shows how the system should behave when a client provides product lines but not a fully developed topic map.

The right behavior is:

1. use product lines as topic seeds
2. generate missing topics around use case, occasion, trust, channels, and competitors
3. generate prompts inside each topic instead of producing one flat keyword-like list

## Input Summary

- Brand: `Coofandy`
- Website: `https://coofandy.com`
- Business model: `ecommerce / marketplace-led men's apparel brand`
- Target market: `United States`
- Priority channels: `Amazon`, `Walmart`
- Weak AI surface: `Google AI Overviews`
- Product-line seeds:
  - mens shirts
  - mens pants
  - 2 piece set
  - mens matching sets
  - mens turtleneck sweater
- Competitor set:
  - high: Men's Wearhouse, Express
  - medium-high: Banana Republic, Nautica
  - medium: Ralph Lauren, Gap, Tommy Hilfiger, Zara, Levi's, Calvin Klein, Steve Harvey

## Why This Client Needs Topic Generation

If the system only uses the provided product lines, it will miss important monitoring space such as:

- hot-weather fabric and comfort questions
- business-casual versus vacation use cases
- Amazon and Walmart trust and purchase-channel questions
- value comparisons against better-known mall and department-store brands
- fit, sizing, and outfit-building prompts

So the final prompt set should not be:

`product line -> prompts only`

It should be:

`product line seeds -> topic map -> prompts by topic`

## Topic Map

| Topic | Topic Type | Topic Source | Related Product Lines | Why This Topic Exists |
|---|---|---|---|---|
| summer business-casual shirts | product-category | derived-from-product-line | mens shirts | Core volume topic with strong overlap between workwear and casual styling. |
| lightweight pants for hot weather and travel | product-category | derived-from-product-line | mens pants | Strong commercial topic tied to comfort, travel, and summer office wear. |
| vacation-ready 2 piece sets | product-category | derived-from-product-line | 2 piece set | Signature Coofandy category with strong resort and easy-outfit intent. |
| matching sets for easy outfit formulas | product-category | derived-from-product-line | mens matching sets | High-fit category for AI recommendation flows around convenience and styling. |
| smart-casual turtleneck layering | product-category | derived-from-product-line | mens turtleneck sweater | Seasonal topic for fall and winter smart-casual positioning. |
| affordable premium-looking menswear | competitor-alternative | inferred | mens shirts, mens pants, matching sets | Coofandy competes on value against better-known brands with more premium perception. |
| hot-weather fabric, breathability, and comfort | use-case | inferred | mens shirts, mens pants, matching sets | Repeated user intent cluster across shirts, pants, and sets. |
| vacation, brunch, and date-night dressing | use-case | inferred | 2 piece set, mens matching sets, mens shirts | Occasion-driven topic where outfit recommendations matter more than product taxonomy. |
| Amazon / Walmart purchase confidence | channel-marketplace | inferred | all | Marketplace visibility and trust are part of the purchase path. |
| fit, sizing, and outfit-building confidence | trust-evaluation | inferred | all | Essential brand-defense topic for apparel purchase decisions and returns risk. |

## Topic Strategy By Layer

### Non-brand discovery

Use non-brand prompts to test whether Coofandy enters answer spaces such as:

- best men's shirts for hot weather
- best affordable business-casual pants
- best matching sets for vacation
- best men's turtleneck sweaters for layering

These are the prompts that measure GEO expansion, not just brand recall.

### Competitor comparison

Use comparison prompts to test whether Coofandy appears against:

- Express
- Banana Republic
- Men's Wearhouse
- Nautica
- Gap
- Zara

The point is not just `Coofandy vs X`.

It is also whether Coofandy enters prompts like:

- best alternatives to Banana Republic for affordable business casual
- what brands offer vacation-ready men's matching sets besides Zara

### Brand defense

Use brand-defense prompts to test:

- quality perception
- sizing clarity
- whether Amazon or Walmart listings support the brand story
- whether Coofandy is framed correctly for business casual, vacation, and value-conscious buyers

## Prompt Slice By Topic

Below is a compact example output. A full production run would usually generate many more prompts per topic.

| Topic | Layer | Funnel | Prompt | Why It Matters |
|---|---|---|---|---|
| summer business-casual shirts | Non-brand discovery | Problem awareness | What are the best men's shirts for hot weather that still look business casual? | Core discovery prompt for summer workwear visibility. |
| summer business-casual shirts | Competitor comparison | Brand comparison | Which brand is better for affordable business-casual men's shirts: Coofandy, Express, or Banana Republic? | Tests whether Coofandy enters mainstream comparison sets. |
| summer business-casual shirts | Brand defense | Purchase decision | Are Coofandy men's shirts good for business casual offices in hot weather? | Validates brand fit for the most important use case. |
| lightweight pants for hot weather and travel | Non-brand discovery | Solution education | What are the best men's pants for summer travel that still look polished? | Connects pants to travel + appearance intent. |
| lightweight pants for hot weather and travel | Competitor comparison | Category evaluation | What are the best affordable alternatives to Banana Republic men's summer pants? | Tests substitution into premium-value comparison space. |
| lightweight pants for hot weather and travel | Brand defense | Purchase decision | Are Coofandy men's pants worth buying for hot-weather travel and all-day wear? | Tests comfort and value narrative together. |
| vacation-ready 2 piece sets | Non-brand discovery | Category evaluation | What are the best men's 2 piece sets for vacation and resort wear? | High-intent discovery prompt around a signature category. |
| vacation-ready 2 piece sets | Competitor comparison | Brand comparison | Coofandy vs Zara for men's 2 piece sets: which is better for summer vacations? | Tests whether Coofandy can compete in fashionable vacation intent. |
| vacation-ready 2 piece sets | Brand defense | Purchase decision | Are Coofandy 2 piece sets breathable enough for beach trips and summer travel? | Strong brand-defense prompt tied to climate and travel. |
| matching sets for easy outfit formulas | Non-brand discovery | Solution education | What are the best men's matching sets if I want easy outfits that do not look sloppy? | Captures convenience-led outfit intent. |
| matching sets for easy outfit formulas | Competitor comparison | Brand comparison | Which brand makes better men's matching sets for adults: Coofandy, Nautica, or Express? | Tests positioning beyond trend-led fashion brands. |
| matching sets for easy outfit formulas | Brand defense | Purchase decision | Are Coofandy men's matching sets worth it for travel and capsule wardrobes? | Measures if the brand owns convenience and versatility. |
| smart-casual turtleneck layering | Non-brand discovery | Category evaluation | What are the best men's turtleneck sweaters for smart-casual outfits and layering? | Core seasonal prompt for fall and winter styling. |
| smart-casual turtleneck layering | Competitor comparison | Brand comparison | Coofandy vs Ralph Lauren for men's turtleneck sweaters: which is better value? | Tests value-versus-premium comparison entry. |
| smart-casual turtleneck layering | Brand defense | Purchase decision | Are Coofandy turtleneck sweaters good for layering under a blazer? | Checks if AI connects the brand to the right styling use case. |
| affordable premium-looking menswear | Non-brand discovery | Problem awareness | What men's clothing brands look more expensive than they actually are? | Broad value-style discovery prompt with strong brand-entry potential. |
| affordable premium-looking menswear | Competitor comparison | Brand comparison | What are the best affordable alternatives to Banana Republic and Express for men's business casual? | Important competitor-set prompt for value positioning. |
| affordable premium-looking menswear | Brand defense | Purchase decision | Is Coofandy a good brand if I want affordable clothes that still look polished? | Directly tests brand narrative control. |
| hot-weather fabric, breathability, and comfort | Non-brand discovery | Solution education | What fabrics are best for men's summer shirts, pants, and matching sets? | Educational prompt that can open multiple topic surfaces. |
| hot-weather fabric, breathability, and comfort | Competitor comparison | Category evaluation | Which menswear brands are best for breathable summer outfits without paying premium prices? | Tests category entry through comfort and value. |
| hot-weather fabric, breathability, and comfort | Brand defense | Purchase decision | Are Coofandy clothes good for hot and humid weather? | Important brand-defense question for US summer markets. |
| vacation, brunch, and date-night dressing | Non-brand discovery | Problem awareness | What should men wear on vacation if they want easy outfits that still look put together? | Occasion-led discovery prompt outside rigid product taxonomy. |
| vacation, brunch, and date-night dressing | Competitor comparison | Brand comparison | Which brands are best for men's vacation outfits: Coofandy, Zara, or Tommy Hilfiger? | Tests if Coofandy appears in style-oriented comparisons. |
| vacation, brunch, and date-night dressing | Brand defense | Use / implementation / expansion | What Coofandy pieces are best for beach dinners, brunch, and casual date nights? | Connects the brand to real-life outfit planning. |
| Amazon / Walmart purchase confidence | Non-brand discovery | Category evaluation | What are the best men's clothing brands on Amazon for business casual and vacation wear? | Measures marketplace-led discovery, not just website visibility. |
| Amazon / Walmart purchase confidence | Competitor comparison | Purchase decision | Which men's clothing brand on Walmart gives better value: Coofandy, Nautica, or Gap? | Tests channel-specific comparison behavior. |
| Amazon / Walmart purchase confidence | Brand defense | Purchase decision | Should I buy Coofandy from Amazon, Walmart, or the official site? | Critical brand-defense and channel-trust prompt. |
| fit, sizing, and outfit-building confidence | Non-brand discovery | Solution education | How do I build a simple men's summer wardrobe around shirts, pants, and matching sets? | Captures outfit-building intent that can drive multiple product exposures. |
| fit, sizing, and outfit-building confidence | Competitor comparison | Brand comparison | Which men's brands are best for easy sizing and low-risk online shopping? | Strong comparison prompt around trust and returns anxiety. |
| fit, sizing, and outfit-building confidence | Brand defense | Purchase decision | Does Coofandy run true to size for shirts, pants, and matching sets? | High-monitoring-value brand-defense prompt for ecommerce. |

## Priority Monitoring List

### Top Topics

- summer business-casual shirts
- vacation-ready 2 piece sets
- matching sets for easy outfit formulas
- affordable premium-looking menswear
- Amazon / Walmart purchase confidence

### Top Non-Brand Discovery Prompts

- What are the best men's shirts for hot weather that still look business casual?
- What are the best men's 2 piece sets for vacation and resort wear?
- What men's clothing brands look more expensive than they actually are?
- What are the best men's clothing brands on Amazon for business casual and vacation wear?

### Top Competitor Comparison Prompts

- Which brand is better for affordable business-casual men's shirts: Coofandy, Express, or Banana Republic?
- What are the best affordable alternatives to Banana Republic and Express for men's business casual?
- Which men's clothing brand on Walmart gives better value: Coofandy, Nautica, or Gap?

### Top Brand Defense Prompts

- Are Coofandy men's shirts good for business casual offices in hot weather?
- Is Coofandy a good brand if I want affordable clothes that still look polished?
- Should I buy Coofandy from Amazon, Walmart, or the official site?
- Does Coofandy run true to size for shirts, pants, and matching sets?

## Asset Implications

This topic map suggests that Coofandy would likely benefit from:

- stronger category pages for business-casual shirts and hot-weather pants
- more outfit and occasion pages for vacation, brunch, and date-night use cases
- stronger collection or editorial pages for matching sets and 2 piece sets
- more explicit fit, sizing, and material guidance
- stronger Amazon and Walmart listing language aligned with the same topics
- comparison and value-positioning assets against Banana Republic, Express, and similar brands

## Why This Example Matters

It shows the exact behavior the system should have:

- do not wait for the client to hand over perfect topics
- use product lines as topic seeds
- generate missing topics automatically
- build prompts under topics, not as a flat list
- make the final monitoring system more useful for later optimization
