# TradesStation (tradesstation.shmor.ai)

A Shmor marketplace (shared rules in `../../CLAUDE.md`): its own brand, design and SEO. The UK’s one-stop place to find trusted tradesmen and builders: extensions, lofts, kitchens, roofing, electrics and more. Renamed from BuildersUK on 2026-10-14 (the user asked for a "TraderStation"-style one-stop brand; "TradesStation" was chosen to stay clear of the TradeStation trading-platform trademark). Repo: `Shmorai/shmor-tradesstation` (private until launch). Status: **building**.

## Where things are
| What | Where |
|---|---|
| Card on shmor.ai, search keywords, **referral links**, offers, SEO defaults | `shmor-site.json` |
| Pages (1 JSON file = 1 Google landing page) | `content/` (`home.json` = homepage) |
| Design: header, logo, footer | `templates/layout.html` |
| Design: styles | `assets/site.css` (kit defaults; add this site's theme block at the bottom) |
| Generated output (don't edit by hand) | `index.html`, `*/index.html`, `sitemap.xml`, `robots.txt`, `404.html`, `search/` |

Replaced the planned "Shmor Pros" card on shmor.ai (UK tradespeople; plumbing stays with LocalPlumbers, business services with ProFinders).

## Pages (22)
Home · trades (directory hub, photo tiles) · builders · house-extensions · loft-conversions · kitchen-fitters · bathroom-fitters · roofers · electricians · plasterers · painters-decorators · landscapers · carpenters-joiners · choosing-a-builder (hiring guide: quotes, contracts, stage payments, Consumer Rights Act, 14-day cancellation) · how-it-works · blog + 6 posts (extension planning rules, how to plan an extension, loft conversion types, loft permitted development, Building Regulations for extensions/lofts, party wall notices), each with official GOV.UK / Planning Portal / legislation.gov.uk sources. Home shows the 3 latest posts; the extensions and lofts pages link to the relevant posts.
Each trade page: what they help with, when you need one, checks before you hire (Gas Safe, competent person schemes/Part P, FMB, TrustMark, NFRC, party wall, planning/Building Regs where relevant), what affects the cost (factors only, no prices), 3 FAQs, "Free / Compare / No obligation" highlights, related trades.
Top menu (`navOrder`): All trades, Builders, Extensions, Roofers, Electricians, Landscapers, Hiring guide, Blog (How it works is footer-only).
Home blocks: trust strip (navy) → "Popular trades" photo mosaic (9 tiles, first is the 2×2 feature) → highlights → "How it works" steps. Tile counts are chosen so the 4-column grid has no gaps (home 9 with feature, hub 12 without).

## Design
"Professional trade station": cool light page #F4F6F9, white surfaces, deep navy #0E2238 / #16304D (top bar, trust strip, hero overlay, CTA panel, footer), amber #FFB300 for buttons and highlights (hover #E6A100), burnt amber #B45309 for links and the "Station" half of the wordmark (amber is never text on white). Fonts: Archivo 800 headings in sentence case + Inter body. Small amber rule above section headings; navy check bullets. Every hero is a photo with a navy left-to-right gradient and a white search panel. Logo = navy rounded square, amber roof chevron, white brick courses + "Trades**Station**" wordmark.
**Photos:** free-licence Unsplash images (not Unsplash+), credited, in each page's `"image"`. All 29 checked loading. Mobile checked at 375px (no horizontal scroll).

## Commands (run here)
```bash
node tools/build.js           # rebuild after ANY change to content/, templates/ or shmor-site.json
node tools/serve.js <port>    # local preview (see the "tradesstation" preview config)
```
After changing `shmor-site.json`, also run `node tools/sync-network.js` in `../../shmor-ai`.

## Referral links
Add to `shmor-site.json` → `"links"`, list slugs in a page's `"partners"` (or add `"offers"`), rebuild, sync the master, then commit both repos.

## Referral link plan
None yet. Natural fits are UK trade quote platforms with partner/affiliate programmes. The user needs to join one and supply the exact tracking link; then add it to `"links"`, list it in each trade page's `"partners"` (headings already set, e.g. "Get free quotes from roofers"), and optionally set `"fallback"`.
