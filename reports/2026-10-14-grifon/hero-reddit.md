# Hero Brand & Category — Reddit

## Status: NOT COLLECTED (platform blocked in this environment)

Reddit was explicitly required for this run. Every route was tried and refused by the environment:

| Route | Result |
|---|---|
| WebFetch `www.reddit.com/search` | "unable to fetch from www.reddit.com" |
| WebFetch `old.reddit.com/search` | "unable to fetch from old.reddit.com" |
| WebSearch with `allowed_domains: reddit.com` | API 400: "domains are not accessible to our user agent: reddit.com" |
| WebSearch `site:reddit.com …` | No reddit.com URLs returned |
| Shell `curl reddit.com/search.json` | Proxy 403 |
| Third-party Reddit archive API | Host not resolvable |

Under the evidence rules we did **not** try to get past these access controls, and we did **not** invent Reddit evidence. No finding in this report is attributed to Reddit.

**Brand-level expectation (Inferred):** across 30+ open-web queries, no Grifon mention appeared on any forum, Q&A or community site (RedFlagDeals, Houzz, forums). Grifon probably has little or no Reddit footprint, which is common for a regional DTC brand. Category threads (sink material, workstation sinks, gauge, Kraus vs Ruvati) are certainly plentiful and are where the useful VOC will be.

## Proxy evidence used instead (labelled as non-Reddit)
Category-level customer language was taken from Houzz discussions, retailer reviews and buying guides. Those items are tagged with their real platform in `evidence.csv`.

## Manual / browser pass: ready-to-run query plan

Run in a browser with Reddit access (e.g., Claude in Chrome), capped at 1,000 comments total. Record subreddit, URL, date, owner vs recommender, and affiliate/astroturf flags.

| Family | Queries | Subreddits |
|---|---|---|
| Brand | `grifon sink`, `grifon évier`, `granite grifon boisbriand` | r/montreal, r/Quebec, r/PersonalFinanceCanada, r/HomeImprovement |
| Purchase intent | `best undermount sink canada`, `where to buy kitchen sink montreal`, `évier cuisine recommandation` | r/kitchenremodel, r/HomeImprovement, r/montreal, r/askTO |
| Failure modes | `stainless sink scratches regret`, `granite composite sink stain white`, `composite sink chipped`, `sink rust spots new` | r/HomeImprovement, r/Plumbing, r/CleaningTips |
| Comparisons | `kraus vs ruvati`, `blanco silgranit vs kraus`, `16 vs 18 gauge sink`, `workstation sink worth it` | r/kitchenremodel, r/HomeImprovement |
| Alternatives | `amazon kitchen sink good`, `lordear sink`, `ikea sink`, `costco sink` | r/kitchenremodel, r/BuyItForLife |
| Outcomes | `workstation sink love`, `quiet sink`, `sink cutting board ledge` | r/kitchenremodel, r/Cooking |

When the pass is done, append rows to `evidence.csv` with `platform=Reddit`, then re-run the insights sections marked "Reddit validation needed" in `report.md`.
