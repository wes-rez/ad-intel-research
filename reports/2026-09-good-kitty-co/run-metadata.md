# Run Metadata — 2026-09-good-kitty-co

**Collection date:** September 2026 (single-session run)
**Hero brand:** Good Kitty Co (goodkittyco.com)
**Competitor set (user-selected, 3 of 5 originally scoped):** Uqora, AZO, Utiva — selected as the closest direct competitors (pure prevention-supplement DTC/retail players). Winx Health and Semaine Health remain scoped from the first-pass report but were not put through the Phase 2 deep-evidence workstreams this run.
**Review cap:** Top 1,000 publicly accessible reviews per brand per platform (default) — **not reached for any brand or platform this run**; every platform/brand combination stopped well below the cap due to access constraints below, not because the cap was hit.
**Export format:** CSV (this file + `evidence.csv`) plus a best-effort single-tab Google Sheet (see note below).

## Tooling constraints encountered (read before trusting any "0 results" row)

1. **Direct site access blocked:** `goodkittyco.com`, `thingtesting.com`, `good-kitty-co.tenereteam.com`, `trustpilot.com` (all regional subdomains), `reddit.com`, and `amazon.com` were all confirmed blocked by this session's network egress policy (tested directly via `WebFetch`, not assumed).
2. **No browser-automation tool** (e.g., Playwright/Playwriter MCP) was available in this session, so no page could be scrolled, paginated, or interacted with even where a raw fetch might have partially worked.
3. **Search backend limitations:** the `WebSearch` tool used for all evidence in this run does not reliably honor `site:reddit.com` query restrictions — Reddit-targeted queries repeatedly returned Trustpilot, Walmart, and eBay results instead. This produced a consistent "0 Reddit threads found" result across all four brands (Good Kitty Co, Uqora, AZO, Utiva) checked, which should be read as **a tooling gap, not a market-sentiment finding** — see each brand's `reddit.md` for the specific caveat.
4. **Google Sheets export limitation:** the only connected Google tool this session is the generic Google Drive file connector (create/upload/search/read files). It can create a native Google Sheet, but only as a flat, single-tab document built from uploaded CSV content — there is no available tool for adding multiple named tabs, writing to specific cell ranges, or building the "one tab per platform + combined + taxonomy + run metadata" structure the workflow spec calls for. The Sheet created this run is a single-tab mirror of `evidence.csv`; the full per-platform CSV files and this metadata file remain the source of truth in the repo.

**Google Sheet (single-tab, combined evidence table):** https://docs.google.com/spreadsheets/d/11pPFTA1CQl5k-Rrznp12IsX3r80XDiSzHW7Qt4NXebk/edit — owned by admin@rezmedia.io, created directly from `evidence.csv`.

## Query families run (per workstream)

- **Hero-brand + brand/product:** `"Good Kitty" UTI`, `goodkittyco.com` variants, `"UTI Biome Shield"` variants
- **Comparison:** `"Good Kitty" vs Uqora OR AZO`
- **Purchase intent / category proxy:** `recurrent UTI prevention supplement recommendation "what actually worked"`
- **Competitor brand/product:** `Uqora review`, `AZO cranberry pills review`, `Utiva UTI supplement review` (each with `site:reddit.com`, `site:amazon.com`, and unrestricted variants)
- **Pricing:** targeted price/subscription queries per brand

## Stop reasons (all platforms, all brands)

Every workstream stopped due to **access constraint**, not due to hitting the 1,000-review cap. No platform in this run exposed anywhere near 1,000 inspectable items to this session's tools.

## Known limitations carried into every file in this run

- All customer-voice quotes are **search-engine paraphrases of pages this session could not open directly**, not confirmed verbatim text. Treat wording as directionally accurate, not exact.
- Rating/review-count figures (e.g., AZO's 58,608 Amazon ratings, Uqora's conflicting Trustpilot scores) came from search-result text and were not independently confirmed against a live page.
- The "0 results" Reddit finding across all four brands is very likely a search-tool limitation rather than a true absence of discussion, especially for the two large, established brands (Uqora, AZO).

## Next-run recommendations

1. Re-run with either broader network egress allowances or a session with direct browser access, prioritizing Trustpilot, Reddit, and Amazon direct page reads.
2. If Google Sheets with proper tab structure is required, connect a dedicated Google Sheets API-capable tool (not just Google Drive file upload) before the next run.
3. Revisit the two dropped competitors (Winx Health, Semaine Health) for the same Phase 2 treatment if budget allows.
