# Evidence-Enrichment Subagent Workflows

Use this reference when competitive intelligence needs deep customer evidence and creative-ready outputs. The workflow has three phases:

1. **Hero-brand evidence:** run all four platform workstreams for the hero brand.
2. **Competitor evidence:** run the same four platform workstreams for the selected competitor set.
3. **Creative insights:** run one insights agent after all evidence agents finish.

## Required scope gates

Ask these questions before launching research:

1. **Review depth:** “Should we cap each platform at the top 1,000 publicly accessible reviews per brand, or request more? If a platform has more than 1,000 reviews, the recommended next step is to inspect up to 25% of the total review count, subject to access and budget.”
2. **Export format:** “Should the scraped evidence be saved as Google Sheets or CSV?” If Google Sheets is selected, confirm the destination/account or connected workspace before writing. If CSV is selected, save one normalized file per platform plus a combined file.
3. **Competitor count:** “Should we research 3, 4, or more competitors?” Explain that each additional competitor multiplies platform research and agent-call/credit requirements. Do not start the competitor phase until the user chooses.

The default is **top 1,000 reviews per brand per platform**. This is a cap, not a promise that 1,000 reviews are available or accessible. Record the total visible review count, the number inspected, and the stop reason.

Do not bypass CAPTCHA, login walls, robots restrictions, rate limits, paywalls, or platform access controls. If a source exposes only aggregates or snippets, label it as such.

## Phase 1: Hero-brand platform agents

Run each workstream for the hero brand across all applicable public platforms, not only one source:

- Official site/product reviews and testimonials.
- Trustpilot or equivalent review platforms.
- Amazon product pages and visible review evidence.
- Reddit and relevant niche communities.

The hero-brand agents must produce both a research report and normalized row-level evidence for future reference.

### Shared extraction lens for every hero-brand agent

Every platform agent must aggregate the following categories, with source URL and verbatim quote where publicly visible:

#### Shining feedback

Descriptive praise that explains what customers value in features, experiences, or results. Convert it into:

- High-converting headline candidates.
- Benefit-led ad angles.
- Proof points and feature-to-result messaging.
- Repeated phrases worth testing in customer-language creative.

#### Criticisms

Product, service, delivery, setup, durability, or expectation problems. Convert them into:

- Product improvement opportunities.
- Objection angles.
- Verbatim objection quotes.
- Rebuttal or solution angles, only when the hero brand can credibly answer the concern.

Never turn a criticism into a claim that the brand has solved it unless the evidence supports that claim.

#### Alternative solutions

Capture what customers considered or used instead:

- Named competitors and generic alternatives.
- DIY or no-purchase workarounds.
- Price and option comparisons.
- What made the customer choose the hero brand instead of the alternative.
- Why the alternative was rejected, abandoned, or preferred.

#### Common trends and language

Aggregate recurring:

- Customer language, slang, terms, and meaningful sentences.
- Problems and desired outcomes.
- Most painful problems and moments of frustration.
- Results customers describe after use.
- Words that indicate awareness, urgency, sophistication, or purchase readiness.

Use frequency only as a directional signal. Preserve high-value outlier language when it clearly describes a painful problem or compelling result.

### Required hero-brand evidence fields

Each row should include:

- `brand`
- `platform`
- `source_url`
- `product_or_sku`
- `review_or_thread_id` when public
- `date` when visible
- `rating` and `rating_count` when applicable
- `evidence_type`: first-party, third-party, syndicated, platform aggregation, or survey design
- `sentiment`: shining, criticism, mixed, neutral, or alternative
- `verbatim_quote`
- `normalized_theme`
- `customer_problem`
- `desired_result`
- `alternative_solution`
- `conversion_reason`
- `objection_or_friction`
- `rebuttal_or_solution_angle`
- `creative_use`: headline, hook, body copy, testimonial, objection handling, offer, or research only
- `avatar_signals`: age/life stage, role, sport/use case, skill level, geography if public
- `confidence`
- `limitations`

## Phase 2: Competitor platform agents

After hero-brand evidence is complete, ask for the competitor count and selected names. Then run the same four platform workstreams for each competitor. Use the same extraction lens and schema so the insights agent can compare brands directly.

For competitors, add these comparison fields:

- `competitor_advantage`
- `hero_brand_counter_angle`
- `price_or_option_comparison`
- `switching_signal`
- `customer_quote_source`: hero brand or competitor brand

Cap every platform at 1,000 publicly accessible reviews per brand by default. If the platform has more than 1,000 reviews, stop at 1,000 and ask whether to continue; recommend a maximum of 25% of the platform’s total review count for the expanded pass, subject to access and budget.

## Platform-specific requirements

### Reviews and Trustpilot

Inspect multiple pages when pagination is available. Capture official review widgets, testimonials, Trustpilot, retailer reviews, and relevant review sites. Record the visible aggregate separately from text actually inspected. Deduplicate syndicated content and mark empty Trustpilot profiles as insufficient data.

### Reddit and niche communities

Use query families for brand/product, purchase intent, failure modes, comparisons, alternatives, and outcomes. Sample recent and high-engagement threads, read enough comments to capture disagreement, and record subreddit, URL, date, direct language, and owner-versus-recommendation status. Flag affiliate links, brand representatives, bots, and likely astroturfing. Never present Reddit frequency as market share.

### Amazon

Record exact product URLs/ASINs, price, variants, badges, rating distribution, review count, visible review excerpts, Q&A themes, shipping/packaging issues, missing parts, setup friction, durability, returns, and warranty language. Treat “Customers say” as Amazon-generated aggregation and separate it from direct review text. Record region/global rating scope.

### Hero-brand post-purchase survey

Design, do not fabricate, first-party evidence collection:

- Immediate delivery survey: purchase trigger, expectations, alternatives considered, offer attribution.
- 7–14 day survey: setup, first use, missing parts, early friction, intended use.
- 30-day survey: repeat use, durability, results, satisfaction, competitor comparison, desired improvements.
- Return/support survey: reason, alternative chosen, recovery experience, unresolved objection.

Include exact questions, response types, consent/privacy language, sampling rules, suppression rules, and export fields. Pair ratings with verbatim responses and product/SKU/channel/offer metadata.

## Export and persistence requirements

Before collection, ask whether the user wants **Google Sheets or CSV**. Save the normalized evidence for future reference:

- Google Sheets: one tab per platform, one tab for the combined evidence table, one tab for taxonomy/definitions, and one tab for run metadata and source limits.
- CSV: one file per platform, one combined CSV, and one metadata JSON or Markdown file containing collection date, queries, page depth, cap, stop reasons, and limitations.

Do not overwrite prior runs. Use a dated run identifier and stable row IDs so future runs can append or compare changes.

## Phase 3: Insights agent

Start exactly one insights agent after all hero-brand and competitor subagents finish. Its goal is an easy-to-read, executable document that fuels creative strategy.

The insights agent must include:

1. **Executive creative readout:** the few highest-leverage findings.
2. **Cross-brand trend map:** repeated language, problems, desires, results, and objections across all brands.
3. **Hero-brand strengths:** shining feedback, proof points, and customer language to preserve.
4. **Hero-brand criticisms:** product improvements, objection angles, verbatim objection quotes, and credible rebuttal/solution angles.
5. **Alternative-solution map:** competitor, DIY, generic marketplace, and do-nothing alternatives; why customers switch or stay.
6. **Creative inspiration angles:** at least 10 angles mapped to evidence and funnel stage.
7. **Sample strong headlines:** headline candidates grounded in shining feedback, pain, desired results, and objection handling. Label them as drafts, not tested winners.
8. **Sample offers:** offer structures suggested by the evidence, with assumptions and risks.
9. **Top objections and rebuttals:** objection quote, source brand, evidence, and credible answer.
10. **Customer avatars:** for each major avatar, include estimated age/life stage, role, use case, pains, objections, desires, desired results, awareness level, buying trigger, alternatives, and real-world sample quotes. Every quote must identify whether it came from a hero-brand review or competitor-brand review.
11. **Prioritized test plan:** creative concepts, hook variants, proof, CTA, landing-page implication, and measurement hypothesis.
12. **Evidence gaps:** what still requires survey validation or deeper collection.

Clearly label each conclusion as **Observed**, **Inferred**, or **Recommended**. Do not call a headline “high converting” unless it has actually been tested; call it a high-potential or evidence-backed draft.

## Shared evidence schema

```json
{
  "brand": "string",
  "platform": "string",
  "source_url": "string",
  "product_or_sku": "string",
  "review_or_thread_id": "string",
  "date": "string",
  "evidence_type": "first_party | third_party | syndicated | platform_aggregation | proposed_process",
  "sentiment": "shining | criticism | mixed | neutral | alternative",
  "verbatim_quote": "string",
  "normalized_theme": "string",
  "customer_problem": "string",
  "desired_result": "string",
  "alternative_solution": "string",
  "conversion_reason": "string",
  "objection_or_friction": "string",
  "rebuttal_or_solution_angle": "string",
  "creative_use": "headline | hook | body_copy | testimonial | objection_handling | offer | research_only",
  "avatar_signals": ["string"],
  "sample_or_count": "string",
  "collection_depth": "string",
  "confidence": "high | medium | low",
  "limitations": ["string"]
}
```

## Recommended output files

Use a dated, collision-free directory for each run:

- `reports/<run-id>/hero-reviews-trustpilot.md`
- `reports/<run-id>/hero-reddit.md`
- `reports/<run-id>/hero-amazon.md`
- `reports/<run-id>/hero-post-purchase-voc.md`
- `reports/<run-id>/competitors/<brand>/reviews-trustpilot.md`
- `reports/<run-id>/competitors/<brand>/reddit.md`
- `reports/<run-id>/competitors/<brand>/amazon.md`
- `reports/<run-id>/competitors/<brand>/post-purchase-voc.md`
- `reports/<run-id>/evidence.csv` or the selected Google Sheet
- `reports/<run-id>/insights-and-creative-brief.md`

Keep the main client-facing report concise, link the evidence export, and preserve all source URLs and verbatim quotes for auditability.
