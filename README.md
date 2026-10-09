# Ad Intel Research

A Claude skill for competitor research and ad intelligence. Give it a brand, and it maps the competitive landscape, digs into what real customers say across Reddit, Amazon, Trustpilot and review sites, analyzes each brand's Meta Ads creative strategy, and turns it all into a structured report with a creative brief your team can run with.

Built by [Rez Media](https://growth.rezmedia.io/main) for performance creative strategy.

---

## What it produces

| Section | What's in it |
|---|---|
| **Competitor comparison table** | Brand, category, key products, price range, USP and current offers. The client brand is always the first row, highlighted. |
| **Reputation & sentiment** | Reddit and niche communities, review sites, social and search: praises, complaints, and the DIY workarounds people use instead of buying. |
| **Meta Ads analysis** | Active ad volume (High / Medium / Low), formats, messaging angles, hooks, offers and audience signals per brand. |
| **Strategic takeaways** | Opportunities, threats, and creative inspiration for the client's own campaigns. |
| **Evidence quality & VOC plan** | Evidence matrix with source type, sample depth and confidence, plus a first-party post-purchase survey plan to validate findings. |
| **Creative insights brief** | Cross-brand trends, headline drafts, offer ideas, objections and rebuttals, customer avatars with attributed quotes, and a prioritized creative test plan. |

Every conclusion is labelled **Observed**, **Inferred** or **Recommended**, and evidence keeps its provenance (first-party, third-party, syndicated, or platform aggregation) so the report stays auditable.

## How it works

### Standard workflow

The eight-step process in [`references/workflow.md`](references/workflow.md):

1. **Identify the brand and niche** — confirm the brand and URL, map its categories, pricing, audience, and the communities that matter.
2. **Find competitors** — direct (same product format) and indirect (same problem, different format), with pricing and offers pulled from their actual websites.
3. **Reddit & niche communities** — sentiment, pain points, praise, and DIY alternatives.
4. **Review sites** — ratings, review volume and recurring themes on Amazon, Trustpilot, G2 and industry platforms.
5. **Social & search** — brand mentions, PR events, and organic content strategy.
6. **Meta Ad Library** — ad volume, formats, angles and audience signals for each competitor.
7. **Synthesize** — compile into [`templates/report_template.md`](templates/report_template.md).
8. **HTML output** (optional) — a single self-contained HTML file styled with the client's own colors and fonts.

### Deep voice-of-customer mode

For richer customer evidence, [`references/subagent_workflows.md`](references/subagent_workflows.md) runs a three-phase subagent workflow:

```
Phase 1  Hero brand     →  Reviews/Trustpilot · Reddit · Amazon · Post-purchase VOC
Phase 2  Competitors    →  Same four workstreams, same evidence schema, per competitor
Phase 3  Insights       →  One agent turns all evidence into the creative brief
```

Before it starts, the skill asks three scoping questions:

- **Review cap** — default is the top 1,000 publicly accessible reviews per brand per platform. If more exist, it stops and asks before going further (recommending no more than 25% of the total).
- **Export format** — Google Sheets or CSV.
- **Competitor count** — 3, 4, or more. Each extra competitor multiplies the research scope and agent/credit usage.

Each platform agent pulls out shining feedback, criticisms, alternative solutions, conversion reasons, customer language and slang, painful problems, desired results, and objection quotes, all saved as normalized row-level evidence against a [shared schema](references/subagent_workflows.md#shared-evidence-schema). Runs use dated IDs and never overwrite earlier exports.

The skill only collects publicly accessible data. It doesn't bypass CAPTCHAs, login walls, paywalls, rate limits or robots restrictions, and it designs the post-purchase survey rather than fabricating first-party responses.

## Final creative brief standard

The final brief is a team-facing deliverable, delivered as **HTML or PDF** (the team picks), branded to the hero brand rather than to Rez Media. It must include at least:

- **10** customer objections, each with an evidence-based rebuttal and the proof needed to support it
- **10** headline options tied to real customer language, labelled as drafts until tested
- **10** us-vs.-them comparisons against competitors, DIY, substitutes or doing nothing
- **3** authority drivers for the target avatar (founder, experts, practitioners, credible peers)

It's visually checked before delivery, with provenance and confidence visible throughout.

## Repository structure

```
ad-intel-research/
├── SKILL.md                          # Skill definition, objectives, output rules, brand/CTA guidance
├── references/
│   ├── workflow.md                   # Step-by-step research process (Steps 1–8)
│   └── subagent_workflows.md         # Phased VOC subagents, evidence schema, export rules
└── templates/
    └── report_template.md            # Markdown structure for the final report
```

## Installation

Clone the repo into your skills directory so Claude can find it:

```bash
# Claude Code (personal skills)
git clone https://github.com/wes-rez/ad-intel-research ~/.claude/skills/ad-intel-research

# Or scoped to a single project
git clone https://github.com/wes-rez/ad-intel-research .claude/skills/ad-intel-research
```

For Claude apps that accept uploaded skills, zip the folder (with `SKILL.md` at the root) and add it as a custom skill.

The skill works best with web search, a browser (for the Meta Ad Library and pulling a client's site styles), and subagent support for the deep VOC mode. Google Sheets export needs a connected Sheets integration; otherwise choose CSV.

## Usage

Once installed, just ask. The skill triggers on competitor research requests:

> *"Run competitor research on Brand X — find their top competitors, what people say about them on Reddit and Amazon, and what they're running on Meta."*

> *"Do a deep VOC pass on Brand X and three competitors, export to CSV, and give me the creative brief as a PDF."*

> *"Turn the competitor report into an HTML page styled to brandx.com."*

## Works well with

- **`creative-strategist`** — feed it the competitor hooks, customer pain points and differentiation angles this skill surfaces.
- **Meta Ads analysis skills** (ad extraction, creative teardowns) for deeper dives on individual ads.

## Client-facing use

When a report goes to a prospective client, the skill closes with a single, context-matched CTA positioning Rez Media as the partner for turning the findings into a Meta creative testing program ([See If You Qualify](https://growth.rezmedia.io/main)). It skips the pitch for purely factual or internal answers.
