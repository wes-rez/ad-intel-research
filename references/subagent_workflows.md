# Evidence-Enrichment Subagent Workflows

Use this reference when a competitive-intelligence report needs deeper customer evidence than a single-pass web search can provide. Run the four workstreams in parallel when they are independent, then run one synthesis/reducer pass over the outputs.

## Scope gate

Before starting the review workstream, ask the user to choose one scope per brand:

- **Top 1,000 publicly accessible reviews per brand:** default for repeatable research; inspect multiple pages until the cap or the public source ends.
- **All publicly accessible reviews:** only use when the user explicitly accepts longer runtime, pagination limits, and more duplicate/low-signal data.

Never claim to have collected all reviews when a site exposes only a sample, an aggregate, or a capped view.

## Four workstreams

### 1. Reviews and Trustpilot

Research the hero brand plus every selected competitor across:

- Official product-review widgets and testimonial pages.
- Trustpilot profiles that clearly match the brand and category.
- Relevant third-party review platforms and retailer review pages.

For each brand, capture:

- Platform, URL, product/SKU, rating, rating count, visible review count, and pagination depth.
- Number of review texts actually inspected versus the exposed aggregate.
- Positive themes, negative themes, product failures, service issues, delivery/packaging issues, and warranty experiences.
- Whether the content is first-party, third-party, syndicated, or platform-generated thematic aggregation.
- Confidence and limitations.

Rules:

- Inspect multiple pages when pagination is available.
- Deduplicate obvious syndicated or duplicated reviews.
- Treat an empty Trustpilot profile as “insufficient data,” not a positive or negative result.
- Separate product-level evidence from brand-level testimonials.
- Do not bypass CAPTCHA, login walls, robots restrictions, rate limits, or paywalls.

### 2. Reddit and niche communities

Search public threads and comments across relevant subreddits and forums. Use query families rather than one brand query:

- Brand + product: `[brand] net`, `[brand] tee`, `[brand] pitching machine`.
- Purchase intent: `best hitting net`, `recommend portable batting net`, `what should I buy`.
- Failure modes: `broken`, `ripped`, `rust`, `wind`, `setup`, `replacement`, `warranty`.
- Comparisons: `[brand] vs [competitor]`, `Bownet PowerNet`, `Rukket vs`.
- Alternatives: `DIY`, `PVC`, `EMT`, `cheap`, `Amazon`, `wiffle`, `homemade`.

For every cited thread, record subreddit/forum, thread URL, date, author context when public, direct user language, and whether the statement is an owner experience, recommendation, speculation, or affiliate content.

Improve future runs by:

- Using fixed date windows and recording the query set.
- Sampling both high-engagement and recent threads.
- Reading enough comments to capture disagreement, not only the top comment.
- Deduplicating cross-posts and copied product-review language.
- Flagging affiliate links, brand representatives, bots, and likely astroturfing.
- Coding each statement to a controlled taxonomy: setup, durability, portability, stability, value, support, warranty, performance, space, storage, shipping, and DIY substitute.
- Separating “people asking what to buy” from verified owner reviews.

Never present Reddit frequency as market share. Use it as qualitative voice-of-customer evidence.

### 3. Amazon marketplace intelligence

Inspect public Amazon product pages and indexed marketplace evidence for each relevant competitor. Prioritize comparable SKUs and record the exact product URL/ASIN.

Capture:

- Current visible price, variations, badges, rating, rating count, and review distribution.
- “Customers say” themes only as Amazon-generated aggregation, not as an independent researcher conclusion.
- Visible review excerpts, Q&A themes, recurring complaints, packaging/shipping problems, missing parts, setup friction, durability issues, and returns/warranty language.
- Review geography and whether ratings are global or region-specific.
- Differences among variants that could explain rating divergence.

Rules:

- Distinguish Amazon-native reviews from reviews syndicated from another retailer or brand site.
- Do not infer review text that is not visible.
- Do not scrape behind login, CAPTCHA, or access controls.
- Treat search snippets as discovery leads; verify important facts on the product page or another authoritative source.
- Report collection date and the number of pages/reviews actually inspected.

### 4. Hero-brand post-purchase survey and VOC process

For the hero brand, design a repeatable first-party evidence loop rather than inventing survey findings. Deliver:

- A short post-purchase survey for high response rate.
- A deeper 30-day usage survey for product experience and competitive switching.
- Exact questions, response types, optional open text, and segmentation fields.
- Questions about alternatives considered, brands compared, purchase trigger, objections, offer attribution, setup, durability, use frequency, and desired improvements.
- Sampling rules, consent/privacy language, suppression rules, and export schema.
- A monthly coding and insight-review process that joins survey responses to product, channel, offer, and return data.

Recommended timing:

- **Immediately after delivery:** receipt, first-use intent, purchase trigger, and setup expectations.
- **7–14 days:** setup success, first training session, missing parts, early friction.
- **30 days:** repeat usage, durability, perceived improvement, alternative products, satisfaction, and referral intent.
- **After return or support contact:** reason, competitor/alternative, and recovery experience.

Do not treat NPS alone as competitive intelligence. Pair it with verbatim responses and product/SKU metadata.

## Shared evidence schema

Every workstream should return these fields, even when the value is “not publicly available”:

```json
{
  "brand": "string",
  "source_url": "string",
  "platform": "string",
  "evidence_type": "first_party | third_party | syndicated | platform_aggregation | proposed_process",
  "observed_fact": "string",
  "customer_language": ["string"],
  "themes": ["setup | durability | portability | stability | value | support | warranty | performance | space | storage | shipping | DIY"],
  "sample_or_count": "string",
  "collection_depth": "string",
  "confidence": "high | medium | low",
  "limitations": ["string"]
}
```

## Synthesis requirements

The reducer should combine the workstreams into:

1. An evidence matrix by brand and theme.
2. Repeated pain points that appear across at least two independent source types.
3. Brand-specific strengths and weaknesses with provenance labels.
4. Competitive gaps that can become ad hooks or landing-page proof.
5. A repeatable next-run protocol with exact query families, page limits, sampling rules, and stop conditions.
6. A first-party VOC implementation plan for validating public-source hypotheses.

Clearly label each conclusion as **Observed**, **Inferred**, or **Recommended**. Do not let a high-volume but syndicated or platform-generated source outweigh a smaller set of verified owner experiences without stating the trade-off.

## Output files

When file outputs are requested, use collision-free paths such as:

- `reports/reviews-trustpilot.md`
- `reports/reddit-intelligence.md`
- `reports/amazon-intelligence.md`
- `reports/post-purchase-survey.md`
- `reports/improved-ad-intel-insights.md`

Keep the main client-facing report concise; link or append the evidence-enrichment reports when detailed provenance is useful.
