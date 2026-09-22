# Competitor Intelligence Workflow

This workflow guides the process of gathering comprehensive intelligence on a competitor brand.

## Step 1: Identify the Competitor and Niche
1. Confirm the target competitor brand name and URL with the user.
2. Visit the brand's website to understand their product categories, pricing, and positioning.
3. Identify the primary industry, niche, and target audience.
4. Determine the most relevant subreddits, review sites, and social platforms for this niche.

## Step 2: Identify Competitors
1. Use the `search` tool to find direct and indirect competitors in the same niche.
2. Visit each competitor's website to extract: key products, price range, USP, and current offers/promotions.
3. Build a competitor list covering both direct (same product format) and indirect (same problem, different format) competitors.
4. Include the client's own brand as the first row for easy comparison.

## Step 3: Reddit & Niche Community Research
1. Use the `search` tool to find discussions about each brand on Reddit (e.g., `site:reddit.com "Brand Name"`).
2. Search within specific subreddits identified in Step 1.
3. Analyze sentiment, common praises, and frequent complaints. Look for authentic user experiences and pain points.
4. Note DIY alternatives or workarounds users mention — these are often the real competition.

## Step 4: Review Site Analysis
1. Use the `search` tool to find brand profiles on Trustpilot, Amazon, G2, Capterra, or industry-specific platforms.
2. Note the overall rating and review volume.
3. Read a sample of positive and negative reviews to identify recurring themes.

## Step 5: General Social Media & Search Analysis
1. Use the `search` tool to find recent brand mentions on social media (Twitter, Facebook, TikTok) and news.
2. Assess overall public sentiment and any recent PR events or controversies.
3. Note TikTok/Instagram organic content strategy if paid ads are minimal.

## Step 6: Meta Ads & Creative Strategy Analysis
1. Navigate to the Meta Ad Library (https://www.facebook.com/ads/library/).
2. Search for each competitor's brand name.
3. For each competitor, analyze:
   - Volume of active ads (High/Medium/Low).
   - Primary ad formats (Video, Image, Carousel, UGC).
   - Core messaging angles, hooks, and offers.
   - Target audience signals (e.g., "Sports Moms," gym owners, teens).
4. Note any recurring patterns or successful hooks worth adapting.

## Step 7: Synthesize and Report
1. Compile all findings into the structured report using `templates/report_template.md`.
2. Always include the **Competitor Comparison Table** (brand, category, key products, price range, USP, current offers).
3. Highlight the client brand's row in the table for easy reference.
4. Synthesize actionable strategic takeaways: Opportunities, Threats, Creative Inspiration.

## Step 8: HTML Output (if requested)
If the user requests an HTML version styled to their brand:
1. Visit the client's website (or agency site) to extract the color scheme via browser JS:
   ```js
   // Run in browser console on their site
   document.querySelector(':root') // check CSS variables
   window.getComputedStyle(document.body) // get fonts, colors
   ```
2. Extract: background color, accent colors, font families, card/border styles.
3. Build a single self-contained `.html` file using those design tokens.
4. Key design elements to replicate: sticky nav, section labels, card grids, color-coded tags, footer.
5. Deliver the `.html` file as an attachment — no server required, opens in any browser.
