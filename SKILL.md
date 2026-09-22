---
name: ad-intel-research
description: Comprehensive competitor research and intelligence gathering. Use for finding a brand's competitors, analyzing their reputation on Reddit, review sites (Trustpilot, Amazon), social media, and search engines, assessing their current Meta Ads creative strategy, and producing a structured report with a competitor comparison table (pricing, USP, offers). Also handles HTML report output styled to the client's brand color scheme.
---

# Ad Intel Research

This skill guides the process of gathering comprehensive intelligence on competitor brands, producing a structured report with actionable strategic takeaways.

## Core Objective

Produce a complete competitive picture covering:
1. **Competitor Discovery:** Identify direct and indirect competitors across all relevant product categories.
2. **Comparison Table:** Side-by-side breakdown of each brand's key products, price range, USP, and current offers/promotions.
3. **Reputation & Sentiment:** How brands are perceived on Reddit, niche subreddits, Amazon/Trustpilot reviews, and social media.
4. **Advertising Strategy:** Active Meta Ads volume, creative formats, messaging angles, and target audience signals.
5. **Strategic Takeaways:** Opportunities, threats, and creative inspiration for the client's own campaigns.

## Workflow

Follow the step-by-step process in [references/workflow.md](references/workflow.md).

### Key Investigation Areas

- **Competitor Websites:** Always visit each competitor's site to extract real pricing, key SKUs, and current promotions before writing the comparison table.
- **Reddit & Niche Communities:** Search for authentic user discussions, pain points, and praises. Note DIY alternatives users prefer — these are often the real competition.
- **Review Sites:** Amazon, Trustpilot, G2, or industry-specific platforms. Note rating, volume, and recurring themes.
- **Meta Ads Library:** Assess active ad volume (High/Medium/Low), primary formats, core messaging angles, and target audience signals (e.g., "Sports Moms," gym owners).
- **DIY Alternatives:** Identify cheap workarounds users mention on Reddit — critical for positioning the client brand against non-brand competitors.

## Output Format

Always produce a structured Markdown report using [templates/report_template.md](templates/report_template.md).

The report MUST include:
- **Competitor Comparison Table** — brand, category, key products, price range, USP, current offers. Always include the client's own brand as the first row for reference.
- **Sentiment section** per competitor with pros/cons.
- **Meta Ads section** with volume estimate and creative angle analysis.
- **Strategic Takeaways** with Opportunities, Threats, and Creative Inspiration.

### HTML Output

If the user requests an HTML version styled to their brand/agency site:
1. Visit the client's website and extract the color scheme (CSS variables, fonts, accent colors) via browser JS console.
2. Build a single self-contained `.html` file — no server required, opens in any browser.
3. Apply: sticky nav, section labels, card grids, color-coded category tags, and the client's exact font stack and color tokens.
4. Highlight the client brand's row in the comparison table (e.g., tinted background).

See [references/workflow.md](references/workflow.md) Step 8 for the HTML extraction method.

## Integration with Creative Strategist

When used alongside the `creative-strategist` skill, pass these outputs directly:
- Competitor's successful ad angles and hooks → use as inspiration for new creatives.
- Customer pain points from Reddit/reviews → use as direct response hooks.
- Competitor weaknesses (e.g., lack of dermatological credibility) → use as differentiation angles.
