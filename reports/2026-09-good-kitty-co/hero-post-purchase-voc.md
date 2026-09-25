# Hero-Brand Post-Purchase VOC Design — Good Kitty Co

**Run ID:** 2026-09-good-kitty-co · **Status:** Proposed process only. No first-party responses have been collected — Good Kitty Co would need to actually field this survey against its own customer list. Nothing in this file is a real survey result; it is an instrument design, per `evidence_type: proposed_process`.

This is the first-party validation layer for the public-source hypotheses raised in `hero-reviews-trustpilot.md`, `hero-reddit.md`, and the main report (e.g., "does the perimenopause angle actually convert," "is the antibiotic-recurrence-cycle story the real purchase trigger," "does the packaging/design story matter as much as testimonials suggest").

## Immediate delivery survey (triggered on delivery confirmation, ~1–3 days post-order)

**Goal:** capture purchase trigger and expectations while still fresh; identify offer attribution.

| # | Question | Response type |
|---|---|---|
| 1 | What finally made you decide to try Good Kitty now? | Open text |
| 2 | Which of these had you tried before this? (select all) | Multi-select: prescription antibiotics (preventive), cranberry juice, cranberry pills/other brand (please name), d-mannose alone, probiotics, nothing yet |
| 3 | How would you describe your UTI history? | Single select: occasional (1–2/year), recurrent (3+/year), currently in an active flare, post-antibiotic and worried about recurrence, other |
| 4 | Where did you first hear about Good Kitty? | Single select: Instagram, a friend/referral, a podcast/influencer code, search, press article, other (open text) |
| 5 | What almost stopped you from ordering? | Open text |

## 7–14 day first-use survey

**Goal:** ritual adherence and early friction, before recall fades.

| # | Question | Response type |
|---|---|---|
| 1 | Has the daily routine (canister + capsule) fit into your day so far? | 1–5 scale + open text |
| 2 | Any issues opening, using, or refilling the canister/pouch? | Open text |
| 3 | Have you noticed any side effects? | Open text (flag for support follow-up if reported) |
| 4 | Have you had a UTI since starting? | Yes/No + open text if yes |

## 30-day usage survey

**Goal:** the core efficacy/retention/competitive-switching data point.

| # | Question | Response type |
|---|---|---|
| 1 | Compared to before you started, has your UTI frequency changed? | Single select: much better, somewhat better, no change, worse, too early to tell |
| 2 | If you'd used another product before (cranberry pill, Uqora, AZO, d-mannose, antibiotics), how does this compare? | Open text, tagged to named alternative |
| 3 | How likely are you to continue your subscription? | 1–10 scale |
| 4 | What would make you cancel? | Open text |
| 5 | What's one thing you'd change about the product or experience? | Open text |
| 6 | (If applicable) Are you in perimenopause/menopause, and if so, did that factor into why you looked for a UTI-prevention product? | Yes/No/Prefer not to say + open text — **this question directly tests the perimenopause-avatar hypothesis from the main report and should not be skipped** |

## Return / support-contact survey

**Goal:** understand loss reasons and unresolved objections.

| # | Question | Response type |
|---|---|---|
| 1 | What's the main reason you're cancelling/returning? | Single select + open text: didn't work, too expensive, side effects, forgot to use it, switched to another product (name it), no longer needed, other |
| 2 | What did you switch to, if anything? | Open text |
| 3 | Is there anything that would bring you back? | Open text |

## Sampling, consent, and suppression rules

- **Sampling:** send to 100% of customers at each trigger point (delivery, day 7–14, day 30, cancellation/return); this is a low-volume early-stage brand, so no sampling-down is needed yet.
- **Consent/privacy:** include a one-line notice at the top of every survey: "Your answers help us improve Good Kitty and may be used (anonymized, never with your name) in how we describe the product. You can skip any question." Do not require survey completion to access support.
- **Suppression:** do not send the 30-day survey to a customer who already submitted a return/cancellation survey in the same window (avoid double-asking); suppress all surveys for customers who have opted out of marketing communications, even though this is service-related.
- **Segments to compare:** age bracket (especially 40+ vs. under-40, to test the perimenopause avatar), prior product used, self-reported recurrence frequency, acquisition channel, and whether the customer cited the packaging/design in their reason for buying.

## Export fields (per response row)

`respondent_id`, `survey_stage` (delivery / 7–14 day / 30 day / return), `date_sent`, `date_responded`, `age_bracket` (self-reported, optional), `life_stage_flag` (perimenopause/menopause, self-reported, optional), `prior_product` (open text, taggable to a controlled list: Uqora, AZO, Utiva, Semaine, Winx, cranberry juice, d-mannose, antibiotics, none), `recurrence_frequency`, `acquisition_channel`, `verbatim_response` (per question), `sentiment_tag` (shining / criticism / mixed / neutral — coded manually or via the insights pass), `flagged_for_support` (boolean, true if a side effect or safety concern is mentioned).

## Next review date

Recommend fielding this within 30 days of any paid-creative launch that uses the angles in the main report's Section 9 / the insights brief, so the first cohort of survey responses can validate or kill the perimenopause and post-antibiotic-rebuild hypotheses before committing further budget to them.
