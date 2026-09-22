---
name: PhyloCrates
description: A lab instrument's control surface for hypothesis refinement in phylogenetic comparative biology.
colors:
  navy: "#2C3E50"
  gray: "#ECF0F1"
  white: "#FFFFFF"
  turquoise: "#18BC9C"
  turquoise-ink: "#0D6D5A"
  amber: "#F39C12"
  amber-ink: "#7A4E00"
typography:
  display:
    fontFamily: "IBM Plex Sans, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: "clamp(1.5rem, 1.05rem + 1.6vw, 2.35rem)"
    fontWeight: 600
    lineHeight: 1.32
    letterSpacing: "-0.015em"
  headline:
    fontFamily: "IBM Plex Sans, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: "clamp(1.35rem, 1.15rem + 0.7vw, 1.75rem)"
    fontWeight: 700
    letterSpacing: "-0.01em"
  title:
    fontFamily: "IBM Plex Sans, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: "1.05rem"
    fontWeight: 600
  body:
    fontFamily: "IBM Plex Sans, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: 1.6
  label:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "0.72rem"
    fontWeight: 500
    letterSpacing: "0.02em"
rounded:
  sm: "4px"
  md: "6px"
  lg: "8px"
spacing:
  container-pad: "1.25rem"
  section-pad: "3.5rem"
  container-max: "1180px"
components:
  tag-neutral:
    backgroundColor: "{colors.white}"
    textColor: "{colors.navy}"
    rounded: "{rounded.sm}"
    padding: "0.3rem 0.55rem"
  tag-turquoise:
    backgroundColor: "{colors.turquoise}"
    textColor: "{colors.navy}"
    rounded: "{rounded.sm}"
    padding: "0.3rem 0.55rem"
  tag-amber:
    backgroundColor: "{colors.amber}"
    textColor: "{colors.navy}"
    rounded: "{rounded.sm}"
    padding: "0.3rem 0.55rem"
  protocol-chain:
    backgroundColor: "{colors.white}"
    textColor: "{colors.navy}"
    typography: "{typography.label}"
    rounded: "{rounded.md}"
    padding: "1rem 1.1rem"
---

# Design System: PhyloCrates

## Overview

**Creative North Star: "The Instrument Panel"**

PhyloCrates is documented as a lab instrument's control surface, not sold as a SaaS product. The page reads like the front panel of a piece of protocol equipment: a stage rail that mirrors the eight-stage pipeline literally, rectangular status tags instead of marketing badges, a monospaced protocol chain that looks like an actual state trace, and a scope boundary rendered as in/out columns with status-colored headers rather than persuasive copy. Nothing on the page tries to sell; it reports.

The palette and geometry are Bootstrap Flatly's own tokens, used as shipped rather than reinterpreted: navy, cool-gray, white, and two status accents (turquoise, amber) with darkened -ink variants reserved for small text and markers that need to hold contrast on colored or light surfaces. Corners are small (4–8px), borders are hairline, and the one shadow in the system is a flat 1px paper edge — never a soft ambient blur. Confirmed visual rejection: no pill-shaped tags, no decorative glyph icons, no kicker/eyebrow labels anywhere in the built page. One narrow exception: the masthead's GitHub credit tag carries a single-color line-art platform mark (the standard octocat), because it identifies a specific external service rather than standing in for a concept — it is not license for an icon system elsewhere.

**Key Characteristics:**
- Stage-rail and stage-list numbering are literal pipeline position indicators, not decoration.
- Turquoise and amber are status colors only (in-scope/resolved vs. out-of-scope/warning) — never decorative accents on neutral content.
- Rectangular tag badges throughout; no rounded pill shape exists in the build.
- Flat 1px "paper" shadow only; no blur, no ambient glow, anywhere.
- IBM Plex Mono marks anything protocol-like: stage numbers, the protocol chain, tags, stage outputs, code, footer.

## Colors

Flatly's stock palette, used unmodified, plus two darkened -ink variants introduced specifically to hold AA contrast where turquoise/amber sit under small text.

### Primary
- **Navy** (`#2C3E50`): body text, headings, primary background for the stage rail and the "Get it" section, focus outlines, selection color.

### Secondary
- **Turquoise** (`#18BC9C`): in-scope status only — the "In scope" tag background in the scope-boundary block. Never used as a decorative accent; a stray use on a neutral platform-name tag was found and reverted during finishing.
- **Amber** (`#F39C12`): out-of-scope/warning status only — the "Out of scope" tag background, the same block.

### Neutral
- **Cool Gray** (`#ECF0F1`): page background, masthead background, stage-number chip fill, boundary-block fill.
- **White** (`#FFFFFF`): card/panel backgrounds (protocol chain, neutral tags), text-on-navy contexts.
- **Turquoise Ink** (`#0D6D5A`): darkened turquoise for text-weight use — the in-scope list-item markers and the "In scope" tag border, where full-saturation turquoise would fail AA for small marks.
- **Amber Ink** (`#7A4E00`): darkened amber for the same reason — out-of-scope list-item markers and the "Out of scope" tag border.

### Named Rules
**The Status-Only Accent Rule.** Turquoise and amber never appear on neutral content (platform names, generic labels, decoration). They exist solely to mark in-scope/resolved vs. out-of-scope/warning state. A neutral tag is always white or gray, never tinted.

**The Ink-Variant Rule.** Any small text or marker sitting on or near a turquoise/amber surface uses the darkened `-ink` variant, not the base hue, to hold ≥4.5:1 contrast.

## Typography

**Display/Body Font:** IBM Plex Sans (with -apple-system, BlinkMacSystemFont, sans-serif fallback)
**Label/Mono Font:** IBM Plex Mono (with ui-monospace, SFMono-Regular, Menlo, monospace fallback)

**Character:** IBM Plex Sans carries prose and headings with a plain, technical-document voice; IBM Plex Mono marks anything that represents protocol state, sequence, or a machine-legible value — never used for ordinary sentences.

### Hierarchy
- **Display** (600, `clamp(1.5rem, 1.05rem + 1.6vw, 2.35rem)`, line-height 1.32): the hero thesis statement only.
- **Headline** (700, `clamp(1.35rem, 1.15rem + 0.7vw, 1.75rem)`, letter-spacing -0.01em): section `h2` headings.
- **Title** (600, 1.05rem): `h3` component/stage titles.
- **Body** (400, 16px, line-height 1.6): all prose; prose blocks capped at 74ch.
- **Label** (500, 0.72–0.85rem, letter-spacing 0.02em, uppercase for short tags): tags, stage numbers, stage outputs, protocol chain, footer credit.

### Named Rules
**The Mono-Means-Protocol Rule.** IBM Plex Mono is reserved for anything that represents pipeline state or a discrete token: stage numbers, the protocol chain, tag text, stage-output lines, inline code, footer version string. Prose is always IBM Plex Sans.

## Layout

Single-column document flow, `max-width: 1180px` (1280px above 1400px viewport width), centered, with consistent horizontal padding of `1.25rem` (`1.1rem` under 720px). Sections stack vertically, separated by a hairline top border (`.section + .section`), each with `3.5rem` vertical padding (`2.5rem` on narrow viewports). Prose-bearing sections cap content width at `74ch` for readability. The scope-boundary grid is two equal columns that collapse to one under 720px; the "Get it" grid is an auto-fit card grid (`minmax(220px, 1fr)`) that reflows by content width rather than a fixed breakpoint. The stage rail scrolls horizontally on overflow instead of wrapping, keeping the eight-stage sequence intact at any width.

## Elevation & Depth

The system is flat by default; depth is conveyed through hairline borders and a single non-blurred "paper" shadow, never ambient glow.

### Shadow Vocabulary
- **Paper** (`box-shadow: 0 1px 0 rgba(44, 62, 80, 0.18)`): a flat 1px offset with zero blur, applied to the protocol-chain panel and the scope-boundary blocks. Reads as a physical edge, not a lift.

### Named Rules
**The No-Blur Rule.** Every shadow in the system is a hard 1px offset with no blur radius. Any softened/diffuse shadow is foreign to this world.

## Shapes

Corners are small and consistent: 4px (`--radius-sm`) for tags and stage-number chips, 6px (`--radius-md`) for the protocol-chain panel, 8px (`--radius-lg`) for boundary blocks and the "Get it" card grid. Borders are hairline (1px), in two strengths: `rgba(44,62,80,0.16)` for section dividers and `rgba(44,62,80,0.28)` for structural edges (masthead, boundary blocks, tags). Tags are strictly rectangular with small radius — pill shape does not exist anywhere in the build.

## Components

### Tags
- **Shape:** rectangular, 4px radius, 1px border. Never a pill.
- **Neutral:** white background, navy text, `border-strong` border — used for version/platform labels.
- **Turquoise / Amber:** status-only variants; background is the base hue, border is the matching `-ink` variant, text stays navy.

### Protocol Chain
- **Shape:** 6px radius, 1px `border-strong`, flat paper shadow.
- **Style:** IBM Plex Mono, white background, reads as a literal state-trace string (`Stage → Stage → Stage`).

### Boundary Blocks (signature component)
Two-column in/out scope panels: 8px radius, `border-strong`, gray fill, paper shadow. Each carries one status tag as its header (turquoise for "In scope", amber for "Out of scope") and a list whose `::marker` color is the matching `-ink` token — the ink variants exist specifically to make these markers legible at list-marker size.

### Transcript (signature component)
Alternating researcher/agent turn blocks: 1px-gap grid (same technique as the "Get it" card grid), gray fill for researcher turns, white for PhyloCrates turns. Each turn carries a small IBM Plex Mono role label (`ROLE`, 0.8 opacity navy, matching the muted-text floor) and IBM Plex Sans prose. A turn that hits the scope boundary carries the existing `.tag--amber` "Out of scope" status tag inline — a genuine status use marking a real moment in the transcript, not decoration.

### Record YAML panel
Reuses the `.file-tree` mono-panel pattern (gray fill, hairline border, paper shadow) for a taller, scrollable artifact: `max-height` capped with `overflow-y: auto`, and carries `tabindex="0"`/`role="region"` so keyboard users can reach the scrolled content via the sitewide `:focus-visible` outline. Any caption claiming a shown panel is "exact" or "unedited" must be true of what's actually rendered, not the underlying source it's condensed from — if content is trimmed for length, the caption says so.

### Seed Quote
A flat bordered panel (1px `border-strong`, `--radius-md`, paper shadow, gray fill), italic Plex Sans. No border-left/border-right accent — that pattern was considered and rejected during this component's build as a craft-floor violation (an accent border above 1px on a callout).

### Navigation
- **Site nav (tab bar):** white background, hairline bottom border, one entry per page (Overview, Example, Docs & install). Inactive tabs are navy text at 0.8 opacity; the active tab is full-opacity navy with a 2px navy bottom border. Text-only, no icons, no pill shape.
- **Masthead:** sticky, gray background, text-only wordmark (no mark/logo beside it) + a version tag, a GitHub credit tag (octocat mark + label, currently a placeholder link), and a name tag, hairline bottom border. On narrow viewports the tags stack one per line below the wordmark, deterministically (not relying on inline wrap), so a long tag never overflows the viewport.

## Do's and Don'ts

### Do:
- **Do** use turquoise/amber exclusively as in-scope/out-of-scope status signals, never as decoration on neutral content.
- **Do** use the `-ink` color variants for any text-weight or marker-weight use of turquoise/amber (list markers, tag borders).
- **Do** keep tags rectangular with 4px radius; never round them into pills.
- **Do** keep all shadows flat 1px offsets with no blur.
- **Do** reserve IBM Plex Mono for protocol-like content (stage numbers, tags, code, the protocol chain); keep prose in IBM Plex Sans.

### Don't:
- **Don't** apply turquoise or amber to neutral labels (a stray turquoise platform-name tag was shipped and reverted during finishing — it is not a pattern to repeat).
- **Don't** introduce soft/ambient/blurred shadows; the world's only shadow vocabulary is the flat 1px paper edge.
- **Don't** drop text below 0.8 opacity on navy-on-light or gray-on-navy combinations; three instances fell under AA and were raised to 0.8 (verified ≥4.5:1) during finishing — treat 0.8 as the floor for muted text, not a target to erode further.
- **Don't** add kickers, eyebrows, decorative glyph icons, or system display faces to this world; the one sanctioned exception is the masthead's GitHub platform mark, which identifies a specific external service and is not license for an icon system elsewhere.
