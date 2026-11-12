# UnixMC Website UI Palette

An audit of every colour used by the unixmc.com website: **489 unique colours**. Nearly all of the interface comes from one token file (`uno.config.ts`) with two themes:

- **Overworld**: the light theme (parchment, ink, gold)
- **The End**: the dark theme (purple-black, lilac, bright gold)

> **Brand graphics use the [16-colour brand palette](../../docs/BRAND_GUIDELINES.md#4-colour). This audit documents the *website interface* only.** The two share the gold/night identity but are not the same colours (for example web gold `#FFAA00` vs. logo Clock Gold `#DC9613`).

## Files

| File | What it is |
|---|---|
| [`palette-table.md`](palette-table.md) | Full table: hex, swatch/variable name, role, mode, up to 3 places used, use count |
| [`palette-table-compact.md`](palette-table-compact.md) | Same table with the long illustration/dye/easter-egg tails collapsed into 3 summary rows |
| [`palette-table.json`](palette-table.json) | Machine-readable version (hex, role, count, names, modes, one file reference) |

> The "Where used" columns refer to the **website's source code**, not to files in this repository.

## How to read the tables

- **Uses** counts each literal colour plus every `var(--token)` that points to it. `#33352B (299)` means `--ux-ink` is referenced about 300 times.
- **Mode:** `light` / `dark` are the two themes. `both (band)` = the Nether / End page bands; `both (dark hero)` = the home hero. Those are dark in either theme. `light (email)` and `dark (OG card)` are colours copied into the newsletter template and the social share card.
- **Left out of the scan:** the vendored Starlight stylesheet (minified third party), tests, docs, and `#B47DC6` (an in-game punishment ID, not a colour).
- The site has no Tailwind palette classes, SCSS or LESS. Inline SVGs use `currentColor`; `public/favicon.svg` is the only SVG with colours of its own.

## Core palette

| Hex | Name | Role |
|---|---|---|
| `#F4EDDC` | Parchment ground | Light-mode page background; warm cream like paper |
| `#FBF7EC` | Card | Slightly lighter cream for panels; sits on the ground and on `#E7DCC0` slots |
| `#33352B` | Ink | Dark olive-charcoal body text; also used at low alpha for hairlines and shadows |
| `#D8CCAE` / `#A89B7D` | Edge / Edge-deep | Khaki 3 px borders and the offset pixel shadow that create the blocky Minecraft look |
| `#FFAA00` | Gold | Signature accent: buttons, focus rings, highlights (Minecraft's gold text colour) |
| `#835700` | Deep gold | Text-safe gold for accent text and warnings. Links use a related burnt orange, `#9C4A00` |
| `#4C6743` | Leaf | Muted grass green for headings and secondary accents |
| `#14101F` | End night | Dark-mode ground. Dark mode swaps the whole palette to purple-black: `#1C1729` cards, `#ECE6F8` ink, `#FFBF47` gold, `#C39BF0` lilac in place of leaf green |

### As CSS

```css
:root {
  /* Overworld (light) */
  --brand-ground:     #f4eddc; /* page background */
  --brand-surface:    #fbf7ec; /* cards, panels */
  --brand-ink:        #33352b; /* body text */
  --brand-edge:       #d8ccae; /* 3px pixel borders */
  --brand-edge-deep:  #a89b7d; /* offset block shadow */
  --brand-gold:       #ffaa00; /* signature accent: buttons, focus */
  --brand-gold-deep:  #835700; /* accent text, warnings (AA on cream) */
  --brand-leaf:       #4c6743; /* secondary accent, headings */
  --brand-link:       #9c4a00; /* links */
}

:root[data-theme='dark'] {
  /* The End (dark) */
  --brand-ground:     #14101f;
  --brand-surface:    #1c1729;
  --brand-ink:        #ece6f8;
  --brand-edge:       #352b4a;
  --brand-edge-deep:  #0c0914;
  --brand-gold:       #ffbf47;
  --brand-gold-deep:  #d99a1c;
  --brand-leaf:       #c39bf0;
  --brand-link:       #ffb347;
}
```

## Role groups in the full table

Backgrounds · surfaces/cards · text · muted text · borders · primary accent · secondary accent · links · hover · success · error · info · shadow/overlay, plus these specialised groups:

| Group | Count | Content |
|---|---|---|
| High-contrast overrides | 24 | Accessibility overrides of `--ux-*` (light and dark) |
| Tier / rank | 26 | `--tier-*`, store ranks, ladder ranks, podium medals |
| Profile themes | 59 | `--pt-{emerald,ocean,gold,nether,end,amethyst,crimson}-{link,bar,glow}`, showcase frames/banners |
| Rarity | 22 | Achievement rarity and item tooltips |
| Chart | 9 | `--viz-*` and leaderboard banner |
| Illustration | 174 | Town-scene pixel art; `--strata-*`, `--ore-*`, `--ux-toggle-*` |
| Minecraft dyes | 18 | Banner dye colours (game data) |
| Easter eggs | 23 | Hidden terminal and rabbit effects |

## Known near-duplicates (candidates to merge)

| Pair (ΔE\*) | Note |
|---|---|
| `#825700` `--ux-gold-deep` vs `#835700` `--ux-accent` (0.5) | Not visibly different. Pick one. |
| `#8F6000` vs `#825700` | `#8F6000` is an out-of-date fallback for `--ux-gold-deep`, copied elsewhere. |
| `#4F6B46` vs `#4C6743` `--ux-leaf` (1.6), also `#496440` `--rule-allowed` (1.2) | `#4F6B46` is the same kind of stale fallback. `--rule-allowed` could simply be `--ux-leaf`. |
| Store ranks `#8A5C00 #4E7440 #1F7A72 #2F6B8C` vs `--tier-*` `#835700 #46693A #1B6B64 #2C6585` | Two copies of the tier colours have drifted apart. |
| `#1C1729` `--ux-card` vs `#1D1729` `--lb-row-cell` (dark, 0.5) | Merge. |
| `#0C0914` `--ux-edge-deep` vs `#0B0814` `--end-edge-deep` vs `#0A0713` `--end-deep` (0.4–0.6) | Three near-identical blacks. |
| `#1B1430` `--end-band-from` vs `#1A1430` `--end-card` (0.4) | Merge. |
| `#100D19` `--ux-section` vs `#0F0B18` `--ux-footer-ground` (dark, 0.6) | Merge. |
| `#06040C` / `#04020A` / `#080204` (drop shadows) | Three shadow colours that can't be told apart at 55–60 % alpha. |
| `#F4EEDF` `--ux-footer-ink` vs `#F2ECDD` `--hero-ink` (0.7), both ≈ `#F4EDDC` | One "light ink on dark" token would do. |
| `#0D1410` `--hero-ground` vs `#0C120E` (0.9) | The hard-coded rgba should use the token. |
| `#6D1414` `--rule-permanent` vs `#6B1414` (1.0) | Merge. |
| `#B6ABC9` `--ux-ink-soft` vs `#B9AECB` `--ux-footer-muted` (dark, 1.2) | Merge. |
| `#FFC21A` / `#FFC428` / `#FFC533` | Three slightly different golds (glow, frame, emblem trim). |
| `#E3D98A` `--pt-end-link` vs `#E6D98A` `--rarity-uncommon` (1.3) | Merge. |
| `#D4A7FF` `--end-purple` vs `#CFA6FF` `--pt-amethyst-link` (1.6) | Merge. |

### Other inconsistencies

- The `themeColor` meta tag is `#171426`, but the manifest's `theme_color` is `#292820`. `#171426` matches no token.
- The favicon uses `#334155` (Tailwind slate-700) and white. Neither colour appears anywhere else in the brand.

These are notes for the website team, not brand rules. Until they are consolidated, treat the **core palette** above as the source of truth.
