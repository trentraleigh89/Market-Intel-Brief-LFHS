# Life Fitness / Hammer Strength — Weekly Competitive Intelligence Brief

**A single-file interactive prototype for weekly sales-rep-facing competitive intelligence.**

This is the preview site for the weekly LF/HS Intelligence Brief. It is a design and content prototype hosted here for internal review before the production pipeline goes live.

---

## What this is

A rep-facing weekly brief that surfaces industry intelligence across five verticals relevant to LF/HS commercial sales:

- Health Clubs (HVLP, mid-premium, premium/luxury)
- Hospitality (brand standard, loyalty, PIP cycles, urban and wellness positioning)
- Multi-Unit Housing (lease-up, BTR, senior living, portfolio procurement)
- Performance / Athletics (NCAA D1/D2/D3, pro leagues, S&C, sports science)
- Campus Recreation (bond-funded renovations, functional strength design)

Each week's brief includes a State of Play summary, One Big Idea, vertical insight tiles with rep-facing conversation starters, a Trending section for multi-week pattern recognition, and an Internal-Only Competitive Flags panel tracking tier-1 competitors.

## How to use the prototype

1. Open `index.html` in a browser. Desktop or mobile both work.
2. **Tap a tile** to flip it and reveal the competitive implication plus seller conversation starter.
3. **Tap the bookmark icon** (top right of any tile) to save an insight for later. Saved insights live in the "Saved" filter view.
4. **Rate insights** using the thumbs up/down below each tile's action buttons. Feedback is per-device and feeds the agent's learning loop when live.
5. **Switch weeks** using the week picker in the top right. The picker shows all available weeks including historical samples.
6. **Print** via the Print button in the header. The print view flattens flip cards and converts dark panels to light for toner readability.
7. **Filter** using the chips under the masthead. "Saved" shows only bookmarks, "Trending" shows only multi-week patterns, and each vertical chip filters to that section.

## Important: prototype vs. live content

This is a **preview site only**. The difference between the two content modes:

**Current week (Issue №16 / 2026)** uses real articles from verified publishers. Every source link points to a specific article, not a homepage. The agent pipeline that produces weekly briefs is being built in parallel; Issue №16 is a manual preview of what the live output will look like.

**Archive weeks (Issues №13, №14, №15 / 2026)** use illustrative prototype content from the design phase. These are clearly marked with a yellow "Sample" banner at the top of the brief and a "Sample" badge in the week picker. Source links on these weeks are not verified and should not be treated as authoritative. These weeks exist to demonstrate the archive mechanic and will be removed when the live pipeline begins publishing regular weekly content.

**When sharing this preview with reviewers**, direct them to Issue №16 for live content review and explain that older weeks are illustrative only. The sample banner will remind any new reader of the same thing.

## Preview hosting

This site is hosted via GitHub Pages. It is a single-file static HTML application using React and Babel loaded from CDN. No build step, no server, no backend. The entire experience is in `index.html`.

Browser support: modern Safari, Chrome, Edge, Firefox. Requires internet for the React CDN script on first load; everything else runs client-side. Bookmarks and ratings persist via localStorage per device.

## For reviewers

The primary review targets for this prototype are:

1. **Content quality**: do the insights feel like real competitive intelligence at the level a rep would act on, not industry news summaries? Issue №16 is the relevant week for this review.
2. **Rep action orientation**: each tile includes an implication and a conversation starter on the back face. Do these feel like they accelerate a rep's week, or do they read as generic advice?
3. **Source credibility**: clicking the "Read article" button should take you to the specific article referenced in the tile. If any link does not resolve to the specific article, flag it.
4. **Design clarity**: does the layout hold up on mobile? Does the flip interaction feel natural? Do the trending and flags sections read distinctly from the core insights?

Feedback on tile-level ratings (the thumbs up/down buttons) flows to the agent's improvement loop when the pipeline is live. Any comments beyond the thumbs should go to the team lead directly.

## Known limitations of the prototype

- Bookmarks and ratings are per-device, not synced across browsers or logins. Production will require a backend.
- The archive is fixed at 4 weeks for demonstration purposes. Production will rotate on a rolling schedule.
- There is no authentication gate. Anyone with the URL can view the site. For an internal product this is acceptable; for production anything beyond this preview should go behind SSO or a similar gate.
- All competitive data, including the Internal-Only flags panel, should be treated as sensitive and not shared outside LF/HS sales and marketing leadership.

## Related documentation

- `tag-taxonomy-guidelines.md` — the locked vocabulary of content tags allowed per vertical. This file defines what the agent pipeline is permitted to output and what content reviewers should enforce.

## Contact

For questions about the prototype, design, or content, contact the project owner directly. For bugs or broken source links, note the specific week and tile headline and send that with a brief description.

---

**Status**: Prototype. Not an active production product.
**Last substantive update**: April 19, 2026 (Issue №16 rebuild with real sources).
