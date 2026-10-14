# BuildersUK (buildersuk.shmor.ai)

A Shmor marketplace (shared rules in `../../CLAUDE.md`): its own brand, design and SEO. Find trusted local builders and tradespeople across the UK: extensions, lofts, kitchens, roofing, electrics and more. Repo: `Shmorai/shmor-buildersuk` (private until launch). Status: **building**.

## Where things are
| What | Where |
|---|---|
| Card on shmor.ai, search keywords, **referral links**, offers, SEO defaults | `shmor-site.json` |
| Pages (1 JSON file = 1 Google landing page) | `content/` (`home.json` = homepage) |
| Design: header, logo, footer | `templates/layout.html` |
| Design: styles | `assets/site.css` (kit defaults; add this site's theme block at the bottom) |
| Generated output (don't edit by hand) | `index.html`, `*/index.html`, `sitemap.xml`, `robots.txt`, `404.html`, `search/` |

Replaced the planned "Shmor Pros" card on shmor.ai (UK tradespeople; plumbing stays with LocalPlumbers, business services with ProFinders).

## Pages (15)
Home · trades (directory hub, photo tiles) · builders · house-extensions · loft-conversions · kitchen-fitters · bathroom-fitters · roofers · electricians · plasterers · painters-decorators · landscapers · carpenters-joiners · choosing-a-builder (hiring guide: quotes, contracts, stage payments, Consumer Rights Act, 14-day cancellation) · how-it-works.
Each trade page: what they help with, when you need one, checks before you hire (Gas Safe, competent person schemes/Part P, FMB, TrustMark, NFRC, party wall, planning/Building Regs where relevant), what affects the cost (factors only, no prices), 3 FAQs, "Free / Compare / No obligation" highlights, related trades.
Top menu (`navOrder`): All trades, Builders, Extensions, Roofers, Electricians, Landscapers, Hiring guide, How it works.
Home blocks: trust strip (charcoal) → "Popular trades" photo mosaic (9 tiles, first is the 2×2 feature) → highlights → "How it works" steps. Tile counts are chosen so the 4-column grid has no gaps (home 9 with feature, hub 12 without).

## Design
"Site hoarding": warm concrete page #F6F4EF, white surfaces, charcoal #1B1E22 (top bar, strip, footer), hi-vis yellow #FFC20E for buttons/fills (hover #E5A800), brick orange #C2410C for links and text accents (yellow is never used as text on white). Fonts: Barlow Condensed 800 uppercase headings + Inter body. Hazard-stripe trims under the header, above the footer and on the yellow bottom CTA panel. Every hero is a photo with a dark left-to-right gradient and a white search panel. Bullet lists use yellow check boxes. Logo = yellow rounded square with a charcoal roof + brick courses, wordmark BUILDERS + "UK" badge.
**Photos:** free-licence Unsplash images (not Unsplash+), credited, in each page's `"image"`. All 29 checked loading. Mobile checked at 375px (no horizontal scroll).

## Commands (run here)
```bash
node tools/build.js           # rebuild after ANY change to content/, templates/ or shmor-site.json
node tools/serve.js <port>    # local preview (see the "buildersuk" preview config)
```
After changing `shmor-site.json`, also run `node tools/sync-network.js` in `../../shmor-ai`.

## Referral links
Add to `shmor-site.json` → `"links"`, list slugs in a page's `"partners"` (or add `"offers"`), rebuild, sync the master, then commit both repos.

## Referral link plan
None yet. Natural fits are UK trade quote platforms with partner/affiliate programmes. The user needs to join one and supply the exact tracking link; then add it to `"links"`, list it in each trade page's `"partners"` (headings already set, e.g. "Get free quotes from roofers"), and optionally set `"fallback"`.
