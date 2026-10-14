# Run Metadata — Grifon (grifon.co)

| Field | Value |
|---|---|
| Run ID | `2026-10-14-grifon` |
| Collection date | 2026-10-14 |
| Hero brand | Grifon — grifon.co (DTC sinks, faucets, accessories); sister business Granite Grifon / grifon.ca (countertops, renovation), Boisbriand, QC |
| Competitor set (4) | Kraus, Ruvati, Blanco, Kindred, plus an "Amazon value workstation" bucket (Lordear, Sarlai) as the generic-marketplace alternative |
| Platforms | Brand site reviews, Trustpilot, Amazon (.ca / .com), Reddit, retailer reviews (Home Depot, Wayfair, Lowe's, Walmart, Canadian Tire, Rona, Perigold), Houzz, directories |
| Meta Ad Library | **Excluded by user instruction** ("bypass Meta ad library as well") |
| Review cap | 1,000 publicly accessible reviews per brand per platform (default). Never reached, see depth below |
| Export format | CSV (`evidence.csv`). Google Sheets was not used because no Sheets destination had been confirmed |
| Final brief format | HTML (`creative-brief.html`) |

Scope defaults were chosen without asking because the session ran unattended. Change any of them and re-run with a new run ID; this run does not overwrite earlier ones.

## Access conditions (read before using the findings)

| Source | Access in this environment | Effect |
|---|---|---|
| grifon.co / grifon.ca | **Blocked**: network policy returned 403 on CONNECT; WebFetch could not resolve the host | Hero site data comes from search-engine indexed snippets of grifon.co product and collection pages. Prices and review counts are cached snapshots and may be stale |
| Trustpilot | Accessible | Profiles checked directly (see hero and competitor files) |
| Amazon (.ca / .com) | Product pages not fetchable; only search-indexed listing snippets | Ratings and review counts are snippet-level. No review-text pagination was possible |
| **Reddit** | **Blocked for every tool**: WebFetch refuses reddit.com and old.reddit.com, WebSearch rejects the reddit.com domain, and the shell proxy returns 403 | **No Reddit thread text was collected.** We did not try to get around this. Reddit is logged as a required gap, and `hero-reddit.md` has a ready-to-run query plan for a manual or browser pass |
| Retailers (Home Depot, Wayfair, Lowe's, Walmart, Canadian Tire, Rona) | Search-indexed snippets only | Used as the main third-party VOC for competitors |

## Collection depth

| Brand | Platform | Visible count | Text inspected | Stop reason |
|---|---|---:|---:|---|
| Grifon | grifon.co product reviews | ~72 across GS430 (51), AZUR30 (14), AZUR33 (7) + 1–14 on other SKUs | ~8 excerpts | Indexed snippets only |
| Grifon | Trustpilot | 0 (no profile for grifon.co, www.grifon.co or grifon.ca) | 0 | No profile exists |
| Grifon | Amazon.ca | ~4 ratings total (GS425 1, GS328 1, 2 cutting boards 1 each, GS650 0) | 0 review text | Listings have almost no reviews |
| Grifon | Reddit | Unknown | 0 | Platform blocked |
| Granite Grifon | Google Business (via aggregator) | 177 reviews, 4.7/5 | Theme summary only | Aggregator snippet |
| Kraus | Trustpilot | 0 (kraususa.com, unclaimed) | 0 | No reviews |
| Kraus | Retail (Wayfair, Home Depot, Lowe's, Walmart, AJ Madison) | 2,566 / 633 / 290 / 186 / 112 | ~6 excerpts | Snippets |
| Ruvati | Trustpilot | No profile (404) | 0 | No profile |
| Ruvati | Retail (Wayfair, Home Depot, Walmart, Perigold, Lowe's) | 2,440 / 1,091 / ~140–170 | ~8 excerpts | Snippets |
| Blanco | Trustpilot (blanco.com) | 123 | ~20 titles + 5 body excerpts | Visible page 1 + 1–2★ filter |
| Blanco | Retail (Home Depot) | n/a | AI summary | Snippet |
| Kindred | Trustpilot | No profile | 0 | No profile |
| Kindred | Retail (Canadian Tire, Wayfair.ca, Home Depot.ca, Rona, Amazon.ca) | 27 / 1–5 / 1–6 / 4 / n/a | ~3 excerpts | Snippets |
| Lordear / Sarlai | Amazon.com | Best-seller rank and "bought in past month" badges | 0 | Snippets |
