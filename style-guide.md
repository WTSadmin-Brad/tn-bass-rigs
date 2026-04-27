# style-guide.md

Visual style spec for the rig infographic series. Codifies the marker-rendering aesthetic, locks the per-rig color palette, defines the callout system, and provides the image prompt template plus calibration guidance.

Reference images live in `sources/style-references/` (glue gun, fire extinguisher, locking carabiner). The codification below is derived from those references — when in doubt, look at the actual references rather than relying on the description. Layout and callout inspiration images live separately in `sources/layout-references/`, including third-party rig diagrams that serve as baselines this project improves on. Consult those when working through composition or callout placement decisions.

## The aesthetic

Industrial design concept sketch. School: Spencer Nugent, Reid Schlegel, Sketch-A-Day-style portfolio rendering. Alcohol marker on white paper with confident black fineliner contours, white gouache highlights, and bold geometric background swatches.

This is a human-made aesthetic. The references are drawn by hand. Modern image generation tools tend to drift toward photorealism, vector cleanliness, or smooth digital rendering — all of which destroy the look. Fighting that drift is the central challenge of Phase 4 calibration. See "What to negative-prompt" below.

## Medium and surface

- **Medium:** alcohol marker (Copic-style), black fineliner pen, white gouache for highlights.
- **Surface:** white paper, plenty of unmarked space around the subject.
- **Stroke quality:** visibly streaky, not blended smooth. Strokes run roughly with the form they describe.
- **Stroke discipline:** strokes intentionally overshoot the silhouette as a stylistic choice. They look fast and confident, not contained. This overshoot is load-bearing — without it the rendering looks timid.

## Color logic

Each rig has one dominant chromatic accent. Warm and cool neutral grays carry the secondary parts (line, hooks, swivels, hardware). Black ink for contours and detail. White paper as the dominant background.

### Per-rig accent palette (proposed — confirm in Phase 0)

| Rig | Accent | Notes |
|---|---|---|
| Texas Rig | Crimson red | Classic, aggressive — fits the rig's power-fishing identity |
| Carolina Rig | Forest green | Echoes the soft plastics and grass-flat habitat |
| Free Rig | Burnt orange | Distinctive from the others, fits the "freedom of fall" identity |
| Drop Shot | Cobalt blue | Finesse, deep water, smallmouth association |
| Ned Rig | Teal | Finesse cousin to drop shot, clearly distinct |
| Shaky Head | Warm gray + olive | Subtle, finesse identity |
| Football Jig | Chocolate brown | Matches the dominant skirt color anyway |
| Tokyo Rig | Deep purple | Urban-named rig, modern aesthetic |
| Jika Rig | Mustard yellow | Distinctive from the others |
| Punch Rig | Magenta | Aggressive, hot — punching dense cover |

The palette serves memorization. When the kids see "the red one," they should know it's the Texas Rig before reading the title. Avoid color collisions across rigs that might appear on the same comparison sheet.

### The white halo (critical detail)

A thick white outline traces the entire silhouette of the rig, separating it from the marker swatches behind. Reads like white gouache, correction fluid, or a paper-mask reservation.

This is the single most important visual element. Without it, the marker swatches behind the object visually merge with the object itself and the whole composition collapses. It's also the detail image-gen models most reliably skip. Reinforce it explicitly in every prompt.

### Background marker swatch

Bold geometric blocks of marker color laid behind the object as backdrop. Same color family as the rig's accent. Often a combination of warm gray plus the accent color in layered rectangles. Strokes run primarily horizontal, layered, slightly offset. Visible as discrete brush passes, not a smooth wash.

## Linework

- Black fineliner, multiple weights.
- Heavier line weight on shadow side, lighter on highlight side.
- Construction lines visible on some forms (the carabiner reference shows them on the gate).
- Crosshatching for deep shadow detail (the rope knot shows this clearly).
- Confident, unbroken contours where the form is solid; stuttered or sketchy where it's unresolved.

## Highlights

- White gouache or white pencil, applied last.
- Long vertical streaks for glossy or cylindrical surfaces (fire extinguisher tank).
- Small bright dots for sharp specular hits (metal beads, swivel barrels, hook eyes).
- A cream or warm-white "core highlight" just inside the silhouette on rounded forms.

## Callout system

The reference images barely use callouts. We're adding them. Lock these conventions across the entire series so the kids learn to read the language quickly.

- **Leader lines:** thin black, single weight, drawn at consistent 30° angles. Pick a side (left or right) per component and stay consistent within a sheet.
- **Origin marker:** small filled black circle (~3–4 px equivalent) at the point on the rig where the leader line meets the component.
- **Label block:** at the end of each leader line. Industrial sans-serif (Helvetica Now, Inter Tight, or similar).
  - **Component name:** semibold, slightly larger.
  - **Spec line:** regular weight, smaller. Format: `Brand Model · Size · lb test`.
- **Optional secondary annotation:** small marker swatch (matching rig accent color) behind a tip, knot inset, or pro-tip box. Treated as a visual sub-element of the rig itself.
- **Numbering:** use numbered callouts (① ② ③) when the order matters (sequential rigging steps). Use lettered (A B C) or unnumbered when components are parallel.

## Sheet composition

### Single-rig sheet (default)

- Portrait orientation, 4:5 or 3:4 aspect.
- Rig laid out diagonal or vertical, taking up roughly the central 60% of the canvas.
- Callouts radiate left and right into the margins.
- Title in a corner (top-left or top-right), set in the same industrial sans-serif as the labels but larger.
- Bottom margin holds the "when to throw it" condensed reference (one line per condition).
- Watermark or signature lower right.

### Comparison sheet

- Landscape orientation, 16:9 or 16:10.
- Two or three rigs stacked or side-by-side.
- Shared callouts pointing to the *differences* — same components don't get duplicated labels.
- Title at top, condensed comparison table at bottom.

### Family poster

- Portrait, 11×17 or A3 proportion.
- All rigs in a family (e.g., "Weighted Soft-Plastic Rigs") at smaller scale, arranged in a grid.
- Single common reference key, no per-rig callouts at this scale.
- Designed for wall display rather than detailed memorization.

## Image prompt template (ChatGPT Image 2.0)

Default natural-language template. Tune syntax once Phase 4 calibration produces converging results. Document what works in `working-notes.md` for each rig and roll generalizable findings back into this file.

```
Industrial design concept sketch of a [RIG NAME] bass fishing rig, drawn in
the Spencer Nugent / Reid Schlegel marker rendering style. Alcohol marker
on white paper with visibly streaky strokes that intentionally overshoot
the silhouette of the subject. Black fineliner contour lines with variable
weight, heavier on the shadow side. White gouache highlights applied on
glossy surfaces and metallic components.

Color palette: dominant accent of [ACCENT COLOR] for the rig's primary
visual elements, warm and cool grays for the line, hook, and hardware,
black ink for outlines. Background composed of layered horizontal marker
swatches in the same accent color plus warm gray. A thick white halo
outlines the entire rig silhouette, separating it from the background
swatches — this halo is essential to the style.

Composition: [PORTRAIT/LANDSCAPE], rig laid out [DIAGONAL/VERTICAL/HORIZONTAL]
with the [HOOK/BAIT] in the upper [LEFT/RIGHT] and the [WEIGHT/TERMINAL END]
in the lower [LEFT/RIGHT]. Plenty of unmarked white space around the rig.
Soft drop shadow beneath. Realistic proportions of fishing tackle —
[HOOK SIZE], [WEIGHT SIZE], [LINE PROPORTIONS].

Components visible:
- [Component 1 with brand and spec]
- [Component 2 with brand and spec]
- [Component 3 with brand and spec]

Callout leader lines at consistent 30-degree angles, thin black, with small
filled circle markers at their origin points on the rig, pointing to each
labeled component. Industrial sans-serif labels in semibold. Render quality:
portfolio-grade hand-drawn industrial design sketch, confident and energetic,
not stiff or photorealistic.
```

### What to negative-prompt

The training-data bias of most image-gen models pulls toward clean, polished, photorealistic, or vector outputs. Push back explicitly. Adjust as Image 2.0's actual behavior reveals what it's drifting toward.

Negative prompt list (or anti-descriptors woven into the main prompt):

- photorealistic, photograph, photo
- vector art, flat illustration, clean digital illustration
- smooth blending, airbrushed, gradient mesh
- cartoon, anime, comic book style
- 3D render, CGI, CAD drawing, technical blueprint
- stiff, polished, corporate, generic
- AI-generated aesthetic, plastic-looking surfaces

### Calibration approach

Phase 4's job is to find the prompt syntax that actually produces the reference style with Image 2.0, not just the syntax that *describes* it. Expect a real iteration cycle.

Per-rig pilot procedure:

1. Generate v1 from the template above with the rig-specific values filled in.
2. Compare side-by-side with the reference images (carabiner, glue gun, fire extinguisher).
3. Note specific failures — "halo missing," "strokes too smooth," "background too clean," "looks like CGI."
4. Adjust the prompt for v2. Common adjustments:
   - Reinforce stroke overshoot if it's not appearing
   - Reinforce the white halo if it's missing
   - Add more anti-photorealism descriptors if it's drifting that way
   - Specify "hand-drawn" more aggressively if it looks too clean
5. Iterate until visual match is acceptable. Lock that prompt as the rig's locked template in `image-prompts.md`.
6. Roll generalizable findings back into this file's "What to negative-prompt" or main template.

If Image 2.0 cannot reach the reference quality after meaningful iteration, fall back to the human illustrator brief below.

## Fallback: human illustrator brief

If image generation hits a quality ceiling, the spec for handing this to a human illustrator is essentially this document plus the per-rig dossier. The illustrator brief should include:

- The reference images (all three).
- The rig's accent color from the table above.
- The component list from the dossier (brand, model, spec for each).
- The callout list — which components get labeled, in what positions, with what label text.
- The sheet composition spec (single-rig vs. comparison vs. family).
- A working-notes link for context on the rig.

A human marker artist working from this brief should be able to produce a finished sheet without further direction. If they can't, the brief has a gap worth fixing in this file.

## Things to avoid

- Letting the rendering get clean, polished, or photorealistic. The roughness is the style.
- Skipping the white halo. The composition collapses without it.
- Cluttering callouts. Aim for the maximum information density that preserves the art-piece quality. For single-rig sheets, that's typically 5–10 primary callouts plus secondary annotations (knot insets, pro-tip boxes, conditions reference). The constraint is the wall-hangable test — if a sheet stops looking like an art piece and starts looking like a reference card, density has crossed the threshold. When in doubt, push density up rather than down; Brad's stated preference is "the more info we can add while still feeling like art pieces, the better."
- Color collisions on comparison sheets. If two rigs share an accent color and end up on the same sheet, override the secondary one with its background swatch using the alternative.
- Inventing visual conventions that aren't in this file. Propose updates here first, then apply them to outputs.
