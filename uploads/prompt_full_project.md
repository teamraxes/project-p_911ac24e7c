# Belbes Studio — Site Generation Prompt

**Project:** `p_911ac24e7c`
**Tariff:** landing
**Niche:** plumbing-supply

This prompt drives Claude Design's Pages generation, **after** the Design System is published. Attached files (paperclip): `composition.json`, `brief.json`, `creative_direction.json`. The DS already encodes typography/colors/components — this prompt focuses on layout grid, sitemap, и per-page content briefs.


---

## Grid Logic

*Component:* `cmp_full_bleed_editorial_pacing@1.0.0`

# Magazine-spread full-bleed hero rhythm

**Axis:** `grid_logic`
**Component ID:** `cmp_full_bleed_editorial_pacing`

## When this component is selected

См. `vector_centroid` (density=0.32 → sparse band) + `niche_affinity`.

## Pattern signals

- `full-bleed-hero` (3×)
- `low-density-editorial` (2×)
- `vertical-sidebar-nav` (1×)
- `asymmetric-vertical-nav` (1×)
- `magazine-pacing-rhythm` (1×)
- `full-bleed-aerial-hero` (1×)
- `3-col-sub-brand-section` (1×)
- `manifest-footer-display` (1×)
- `5-section-low-density` (1×)
- `full-bleed-interior-hero` (1×)

## Grid directives 

**Column structure:**
- Columns: **2**
- Breakpoints: [320, 768, 1024, 1440] (mobile / tablet / laptop / desktop)
- Hero layout: **full-bleed**

**Density profile (`sparse`):**
- Row rhythm: 24px baseline grid
- Gutter: 48px between columns
- Margin: 96px page padding
- Section count target: ~6 sections
- Rhythm: **accelerating**

**Section pacing details:**
- Accelerating — sections shorter as user scrolls deeper (editorial)

## Anti-patterns

- вертикальный sidebar nav требует серьёзного UX-investment; без продуманной реализации сбивает пользователей, ожидающих стандартную топ-навигацию
- tracklist layout works только для venue с реальной music programming; для cafe/restaurant без концепции = неуместно

---

## Sitemap


- **/** (?) — TBD


---

## Brief Highlights


**Main message:** Specialty plumbing for the East Bay since 1980 — come touch the premium brands at our Oakland showroom.


**CTA goal:** visit_showroom


**Target audience:** East Bay Area contractors (quick price/availability checks) + new residential customers (Google searches for Kohler/Grohe in Oakland) — both need to feel they're talking to a real specialty supplier, not a chain.


**Key offers:**
- Kohler kitchen and bathroom fixtures (showroom-displayed)
- Grohe faucets and shower systems
- A.O. Smith and Takagi tankless water heaters
- Flexible piping, fittings, and standard plumbing supply


**Required sections:**
- hero
- brands
- showrooms
- family_history
- what_we_sell
- contact



## Image Briefs


### 1. role=?

```json
{
  "id": "img_hero_showroom_fixture",
  "purpose": "hero",
  "placement": "Hero section, full-bleed or right-aligned editorial composition.",
  "subject": "Single Kohler kitchen or bathroom fixture (faucet or sink) photographed in the actual Moran Supply Oakland showroom, treated as a design object — not a catalog render and not a smiling-stock-family scene. Soft natural daylight from showroom front window; warm-neutral wall behind (cream/off-white); brushed-nickel or chrome finish on fixture catches light. Composition leaves negative space for headline overlay.",
  "style_anchors": [
    "editorial product photography (think Bon Appétit / Kinfolk product shots)",
    "Kohler official lifestyle imagery — but shot in this specific Oakland showroom",
    "warm-neutral cream environment, not white seamless"
  ],
  "must_avoid": [
    "stock-photo families",
    "contractor-with-clipboard tropes",
    "manufacturer catalog renders",
    "blue-tinted plumbing-trade photography",
    "1990s plumbing-shop tropes"
  ],
  "aspect_ratio": "16:10",
  "approx_resolution": "2400x1500",
  "alt_text_seed": "Kohler kitchen faucet displayed in the Moran Supply Oakland showroom, warm cream wall and natural light"
}
```



---

## Output Format

Generate a complete static multi-page website implementing the Design System и this site brief.

**Required pages:** /.
**Required asset:** `assets/styles.css` (shared CSS with semantic tokens matching the published Design System).

Constraints:
- All HTML must be valid HTML5 with semantic landmarks (`<header>`, `<main>`, `<footer>`, `<nav>`).
- All inter-page links must be relative.
- Do NOT use Tailwind utility classes — write plain CSS only.
- Do NOT use Lorem ipsum — use real content driven by the brief.
- Hero must surface main_message in <30s scan.
