# 463 Connecticut Street

Interactive schematic-design model of a three-level residence in Potrero Hill,
San Francisco. Modeled from sheets SK-5.1–5.3, Foust Architecture
(project 2611, issued 08.28.26).

**Live:** https://bersonperson.github.io/463-connecticut/

No build step and no dependencies beyond Google Fonts. `index.html` is the
viewer; `model-data.js` and `plans.js` carry the geometry.

## What you can do

| Control | What it does |
| --- | --- |
| Drag / scroll / shift-drag | Orbit, zoom, pan. Pinch to zoom on a touch screen |
| **Levels** | Show or hide each floor |
| **Separate levels** | Pull the floors apart into an exploded axonometric |
| **Cut above** | Slice a live horizontal section at any height |
| **Open the 2D plan** | The original sheet, redrawn as vectors — pan, zoom, switch levels. `P` opens it, `Esc` closes it |
| **Walk through** | Drop to eye level and walk the rooms. `WASD` to move, drag to look, `1` `2` `3` to jump to a level, `Esc` to leave. On a phone an on-screen pad appears |
| **Roof / Glazing / Edges / Labels** | Toggle each layer |
| **Axon / Street / Rear / Side / Plan** | Preset viewpoints |

On a narrow screen the control panel collapses to a bar at the bottom — tap
**Controls** to open it. The 2D sheet turns on its side automatically so a
landscape drawing fills a portrait screen.

## How it was built

The source PDF is vector CAD output, so walls, openings and room boundaries are
taken from the drawing's own line geometry at its stated scale of 1/4" = 1'-0",
not traced by eye. Door and window openings come from the gaps in the drawn wall
faces. The 2D sheets are that same linework, packed as Int16 deltas and gzipped.

Checked against 17 of the dimension strings printed on the sheets — overall
size, every labelled room, the garage door and the deck. Largest deviation: 1".

## Assumptions

The sheets are plans only, with no section, so every vertical dimension is
assumed:

- Floor-to-floor 10'-0"
- Window heads 7'-0", sills 2'-6", doors 6'-10"
- Both stairs are switchbacks: the run drawn on the first-floor sheet
  (11 treads at 10 1/8"), a half-landing at the east end, then a return flight
  west — 17 risers at 7 1/16" per level
- The office's rear wall is modelled solid; the sketch does not detail glazing there
- Furniture, fixtures and cabinetry are omitted

## Three things the model surfaced

1. **Stairwell headroom.** The opening as drawn leaves 5'-11 1/2" at its west
   edge, about 8" under the 6'-8" minimum. Carrying the opening roughly 1'-6"
   further west clears it.
2. **Return-flight treads** come out at 9 1/4", just under the 10" minimum — the
   shaft is about a foot shorter than 17 risers want at this floor height.
3. **The first-floor hallway wall** has to stop at the stairwell for the return
   flight to pass over it. The sheet draws it running through.

All three follow from the 10'-0" assumption and may shrink or disappear against
the real heights.

## Privacy

The repository is public because GitHub Pages on a free plan requires it.
`robots.txt` asks search engines to stay away, so the page is shareable by link
without being indexed.
