# LF/HS Intelligence Brief — Tag Taxonomy Guidelines

**Version 1.0 · Locked**

Purpose: the tags that appear on each insight tile are a controlled vocabulary. These tags are for rep-level scannability, not comprehensive content description. Two tags per insight maximum. Tags must come from the approved list for that vertical only. No improvisation.

These guidelines apply to:
- The agent pipeline that generates weekly briefs (as a constraint in the generation prompt)
- Content reviewers validating briefs before publication
- Any manual edits or drafts

---

## Rules

1. **Each insight gets 1-2 tags. Never 0, never 3+.**
2. **Tags must come from the allowed vocabulary for the insight's vertical.** No cross-vertical borrowing.
3. **Tags display as ALL CAPS in the UI.** Source data should store them in the exact casing below for consistency with the guidelines.
4. **Tags are segment + trigger hybrids.** They answer one or both of: "Who is this about" (segment) or "Why now" (trigger/topic).
5. **When in doubt, use the most specific allowed tag.** Generic tags like GROWTH should be a second tag, rarely a first.
6. **The Tag component auto-uppercases via CSS,** but source data stays in the canonical casing below.

---

## Allowed Vocabulary by Vertical

### Health Clubs
| Tag | Meaning / When to use |
|---|---|
| `PREMIUM` | Premium-tier operators (Equinox-adjacent, luxury boutique, high-dues mid-premium chains) |
| `MID-PREMIUM` | Mid-tier operators between HVLP and luxury (Gold's, LA Fitness, YouFit, regional independents) |
| `HVLP` | High-volume, low-price operators (Planet Fitness, EOS, Crunch, Snap, Blink) |
| `CAPITAL` | Capital events: M&A, IPOs, debt refinancing, PE transactions, funding rounds |
| `LUXURY` | Ultra-premium operators (Life Time, Equinox, ultra-high-dues clubs) — use when specifically about this tier |
| `GROWTH` | Unit expansion, member growth, revenue-per-member gains, new markets |

### Hospitality
| Tag | Meaning / When to use |
|---|---|
| `BRAND STANDARD` | Brand-level amenity/design requirements updated by the franchisor |
| `WELLNESS` | Wellness-positioned amenity strategy, recovery, spa-adjacent programming |
| `LOYALTY` | Loyalty-tier economics driving fitness investment |
| `BRAND CFO` | Signals the decision has moved from asset management to brand-level finance |
| `PIP` | Property Improvement Plan cycles, compliance timelines |
| `URBAN` | Urban-lodging-specific trends, downtown properties, business-traveler markets |
| `BRAND` | Brand-level strategic positioning not captured by BRAND STANDARD or BRAND CFO |
| `AIA` | Architect-influenced insights; hospitality design community sources |

### Multi-Unit Housing
| Tag | Meaning / When to use |
|---|---|
| `LEASE-UP` | Lease-up competitive differentiation, occupancy driving amenity decisions |
| `SENIOR LIVING` | Active senior living operators, 65+ demographic programming |
| `PROGRAMMING` | Programming-led (not just equipment) amenity strategies |
| `STUDENT HOUSING` | Purpose-built student housing developers |
| `RFP` | Active procurement windows, RFP-driven buying |
| `BTR` | Build-to-rent developers, regional SFR portfolios |
| `PORTFOLIO` | Portfolio-level procurement decisions, master contracts, standardization across properties |
| `AIA` | Architect-influenced insights; multifamily design community sources |

### Performance / Athletics
| Tag | Meaning / When to use |
|---|---|
| `RFP` | Active procurement windows — military, collegiate, or pro |
| `D1/D2/D3` | NCAA division context; use as single tag regardless of specific division |
| `WOMEN'S SPORTS` | Women's program-specific budgets, facilities, or procurement |
| `LEAGUE-LEVEL` | League-office procurement decisions (MLS, NFL, NBA consolidation to central buying) |
| `COLLEGIATE` | NCAA-affiliated programs, conference-level dynamics |
| `PRO SPORTS` | Professional leagues and franchises (NFL, NBA, MLB, NHL, MLS) |
| `SPORTS SCIENCE` | Sports science investment, data and performance technology |
| `S&C` | Strength and conditioning focus |
| `AIA` | Architect-influenced insights; athletic facility design community |

### Campus Recreation
| Tag | Meaning / When to use |
|---|---|
| `BOND-FUNDED` | Student fee bonds, bond-funded renovation cycles |
| `LONG CYCLE` | Multi-year design-bid-build cycles, procurement influence windows 9-12 months ahead |
| `COMMUNITY COLLEGE` | Community college rec facilities (distinct from four-year D2/D3) |
| `GROWTH` | Facility spending growth trends across institution types |
| `DESIGN` | Design-forward renovation trends, functional vs selectorized layouts |
| `SPEC` | Spec-line procurement, rack/platform footprint modeling |
| `AIA` | Architect-influenced insights; campus rec design community |

---

## Tag Selection Decision Tree

When generating or validating a tag for an insight:

1. **Identify the vertical first.** The tag must come from that vertical's list.
2. **First tag: pick the most specific segment or trigger.** What's the core "who" or "why now"?
3. **Second tag (optional): pick a complementary angle.** Rule of thumb: if the first tag is a segment, the second should be a trigger/topic, and vice versa.
4. **Avoid tag redundancy.** `BRAND STANDARD + PIP` is fine (distinct concepts). `BRAND + BRAND STANDARD` is redundant.
5. **If no allowed tag fits the insight cleanly, the content may not belong in that vertical.** Reconsider placement before stretching the taxonomy.

---

## What Changed From the Previous (Unconstrained) State

| Previous tag | Resolution |
|---|---|
| `Mid-Market` | → `MID-PREMIUM` (Health Clubs) |
| `M&A` | → `CAPITAL` (Health Clubs) |
| `2027 Pipeline` | → `GROWTH` (Health Clubs) |
| `ROI` | → `AIA` where content cites architect sources; `LEASE-UP` where content is about rental-market competitive positioning (Multi-Unit Housing) |
| `Military`, `Tactical`, `Q2 RFP` | → `RFP, S&C` (Performance) — no dedicated Military tag |
| `MLS` | → `PRO SPORTS` (Performance) |
| `SEC/ACC` | → `COLLEGIATE` (Performance) — conference specificity moves into the headline, not the tag |
| `D1` | → `D1/D2/D3` (Performance) — consolidated |
| `D2/D3` used in Campus Rec | → `GROWTH, SPEC` (Campus Rec) — D1/D2/D3 is a Performance-vertical tag only |

---

## Known Taxonomy Gaps Flagged for Future Review

These are cases where the current allowed vocabulary did not cleanly fit an observed insight type. Worth revisiting quarterly.

1. **No dedicated Military / Tactical tag in Performance.** Currently routed to `RFP, S&C`. If military tactical fitness becomes a recurring vertical for the brief, consider adding `MILITARY` or `TACTICAL` to the Performance allowed list.

2. **No D2/D3 rec facility tag in Campus Rec.** The `D1/D2/D3` tag is Performance-only. If Campus Rec insights frequently cover D2/D3 institutions' rec facility spending (distinct from athletics), consider adding `D2/D3-REC` or moving the division tag to shared use.

3. **No PE / Transaction tag.** `CAPITAL` in Health Clubs covers M&A, IPOs, and refinancing under one umbrella. If the brief later needs to distinguish these, consider splitting.

4. **`GROWTH` appears in two verticals** (Health Clubs, Campus Rec). Meaning is consistent but this is the only repeated tag across verticals. Intentional.

---

## Implementation Notes for the Agent Pipeline

When the agent generates weekly briefs, the generation prompt must include:

```
TAG CONSTRAINT: For each insight in vertical [X], select 1-2 tags from this list ONLY:
  [paste the vertical's allowed list]

Rules:
- Store tags in the exact casing shown (UPPERCASE with apostrophes and slashes preserved).
- Never invent new tags.
- If no allowed tag fits cleanly, reconsider whether the insight belongs in this vertical.
- Prefer specific segment/trigger tags over generic ones like GROWTH.
```

The content reviewer should reject any brief draft containing tags not in the allowed vocabulary for the insight's vertical. No exceptions without updating this guidelines document first.
