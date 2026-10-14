# Hero Brand — Post-Purchase VOC Survey Design (Grifon)

This is a **proposed process**, not collected data. No first-party responses were fabricated.

Bilingual (FR first for Québec, EN). Send from Shopify order events via Klaviyo or a similar tool. Consent line on every survey:
> « Vos réponses nous aident à améliorer nos produits. Elles sont confidentielles et peuvent être citées de façon anonyme. » / "Your answers help us improve. They're confidential and may be quoted anonymously."

## 1. Delivery survey (trigger: delivered + 1 day)
| # | Question | Type |
|---|---|---|
| 1 | What made you start looking for a new sink? (reno / replacing broken / countertop install / new build / other) | Single select + other |
| 2 | Which other brands or stores did you consider? (Kraus, Ruvati, Blanco, Kindred, Home Depot/Rona house brands, Amazon brand, IKEA, Costco, none) | Multi select |
| 3 | What was the main reason you chose Grifon? | Open text |
| 4 | How did you first hear about us? (Instagram/Facebook ad, Google, showroom, countertop installer, Amazon, friend) | Single select |
| 5 | Did it arrive undamaged and complete? | Yes/No + photo upload |
| 6 | Did an offer influence you? (10% sign-up, sale price, free shipping over $350, bundle) | Multi select |

## 2. Install / first use (trigger: delivered + 10 days)
| # | Question | Type |
|---|---|---|
| 1 | Who installed it? (myself, plumber, countertop installer/Grifon, contractor) | Single select |
| 2 | How easy was installation? | 1–5 |
| 3 | Was anything missing or unclear (template, clips, drain, accessories)? | Open text |
| 4 | Which included accessories do you actually use? | Multi select |
| 5 | What countertop is it paired with? (quartz, granite, laminate, butcher block) | Single select |

## 3. 30-day usage (trigger: delivered + 30 days)
| # | Question | Type |
|---|---|---|
| 1 | How satisfied are you? | 1–10 (NPS-style) |
| 2 | Compared with your old sink, what is noticeably better? | Open text |
| 3 | Any scratches, water spots, stains or chips so far? | Yes/No + text |
| 4 | How quiet is it compared with your old sink? | 1–5 |
| 5 | In one sentence, what would you tell a friend about this sink? | Open text (**headline mining**) |
| 6 | What would you improve? | Open text |
| 7 | May we contact you for a photo/video testimonial? | Yes/No |

## 4. Return / support (trigger: return or support ticket opened)
| # | Question | Type |
|---|---|---|
| 1 | Main reason for the return/ticket (damage, size, finish, gauge/quality, changed mind, install issue) | Single select |
| 2 | What will you buy instead? | Open text |
| 3 | How was the resolution experience? | 1–5 + text |
| 4 | What would have kept you? | Open text |

## Rules
- **Sampling:** all orders; at most 1 survey per customer per 21 days. Suppress the 30-day survey if a return is open.
- **Suppression:** skip B2B/contractor accounts for consumer-avatar coding (tag separately).
- **Export fields:** order_id (hashed), SKU, collection (Eterna/Hydra Tech/Azur/Bel Pro/Fireclay), channel (site/Amazon/showroom), offer used, province, countertop type, installer type, rating, verbatim, consent flag, date.
- **Coding taxonomy:** noise, scratches, spots/stains, chips, gauge/thickness, accessories, depth/size, countertop match, shipping damage, install, warranty, value, support, DIY/plumber.
- **Cadence:** review monthly. Refresh the headline bank quarterly from Q3-5 answers.
