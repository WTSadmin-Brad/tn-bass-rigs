# CLAUDE.md

## Project

Tournament-winning bass rig research and infographic production for Tennessee reservoirs. Largemouth-primary, smallmouth and other allowable TN species treated as variants. Workflow per rig: research → working notes → dossier → image prompts → final infographic assets.

This file is a router, not an encyclopedia. Specifics live in pointer files (see folder map). Keep this file short.

## Hard rules — non-negotiable

**Verification rule.** If Brad sends a video, article, or link and you cannot access the actual content, STOP. Say so directly and ask for a transcript, screenshots, or paste. Do not infer from a URL or title. Do not substitute related content. Same applies to any source you would cite — if you cannot read it, do not use it.

**Phase awareness.** Do not begin per-rig dossier work until scope is explicitly confirmed for the current session. Do not research ahead of confirmed scope. If Brad opens a session with "let's work on X," restate the scope and confirm before pulling sources.

**Cite as you go.** Every factual claim in a dossier needs an inline citation. Format: `[Source Name, YYYY](URL)`. For community-consensus claims, cite at least two independent sources and tag `[community-consensus]`. Flag uncertain or context-dependent claims using the inline marker system — see `schema.md` for the full flag inventory (`[CONTESTED]`, `[THIN]`, `[STALE]`, `[TN-LOCAL]`, `[community-consensus]`, `[SPONSOR-FLAG]`). Tier-by-tier source ranking lives in `source-hierarchy.md`.

**No generic placeholders.** "3/0 EWG hook" fails the bar. "Owner Jungle Flippin' 4/0" passes. Every component spec gets a brand and a model.

## Folder map

```
tn-bass-rigs/
├── CLAUDE.md              # This file. Router only.
├── README.md              # Human-facing overview.
├── schema.md              # Dossier schema. Single source of truth for output structure.
├── style-guide.md         # Visual style codification, per-rig palette, callout system, image prompt template.
├── pro-roster.md          # Named pros, sponsorship flags, TN relevance notes.
├── source-hierarchy.md    # Source ranking. @bassniper weighting and rationale.
├── decisions.md           # Rejected ideas + scope changes. Append-only log.
├── sources/
│   ├── style-references/  # Marker-rendering aesthetic refs (glue gun, fire extinguisher, carabiner). Project-wide.
│   ├── layout-references/ # Callout, composition, and infographic-layout inspiration. Includes third-party rig diagrams used as baselines to improve on.
│   ├── transcripts/       # YouTube transcripts. Heavy on @bassniper.
│   ├── articles/          # Editorial full-text saves.
│   ├── tournament-reports/# BASS, MLF, NPFL, regional TN circuits.
│   └── research-log.md    # Chronological dig log.
├── rigs/
│   └── <rig-name>/
│       ├── working-notes.md     # Open questions, contradictions, sources to chase.
│       ├── dossier.md           # Synthesized output. Follows schema.md exactly.
│       ├── image-prompts.md     # Versioned ChatGPT Image 2.0 prompts + iteration notes.
│       ├── reference-photos/    # Product/component photos specific to this rig.
│       └── prompt-iterations/   # Image-gen outputs during calibration (v1.png, v2.png...).
└── outputs/
    └── final-assets/      # Locked finished infographic sheets. Copied from rig folders once approved.
```

## Per-rig workflow

When working on a rig, follow this order. Do not skip steps.

1. **Load context.** Read `schema.md`, `pro-roster.md`, `source-hierarchy.md`, and `style-guide.md` if not already loaded this session. Skim `decisions.md` for prior scope calls that may affect this rig.
2. **Open or create `rigs/<rig-name>/working-notes.md`.** Log every source consulted with date, link, and a one-line takeaway. Open questions and contradictions live here, not in the dossier. This step catches problems before they get baked into the final output. Skipping it produces dossiers that paper over disagreements.
3. **Build the dossier in `rigs/<rig-name>/dossier.md`.** Follow `schema.md` exactly — same headers, same order, same fields. Cite inline. Flag contested claims with `[CONTESTED]`. Surface @bassniper findings that contradict pro consensus as feature moments, not footnotes (see `source-hierarchy.md`).
4. **Pause for Brad's review.** Do not draft image prompts before the dossier is reviewed. Calibration after the first dossier prevents repeated structural errors across the series.
5. **Draft image prompts in `rigs/<rig-name>/image-prompts.md`.** Use the template from `style-guide.md`. Version each iteration as `## v1`, `## v2`, with a one-line note on what changed.
6. **Append learnings to `decisions.md`.** Anything that affects future rigs — rejected approaches, scope clarifications, surprising findings, methodological corrections.

## Context efficiency — what to load when

**Every session, before starting work:**
- `CLAUDE.md` (this file)
- `decisions.md` (recent entries for context on prior calls)
- The relevant `rigs/<rig-name>/` folder if continuing work

**Load on demand:**
- `schema.md` when writing or revising a dossier
- `style-guide.md` when drafting image prompts or making visual decisions
- `pro-roster.md` when validating sources or checking sponsor relationships
- `source-hierarchy.md` when ranking source quality or resolving a citation question
- Specific files in `sources/` when extracting data for a dossier

Loading everything every session burns context budget you will need for synthesis. Pull on demand.

## Output conventions

**Markdown only** for all notes, dossiers, and logs. No HTML.

**File and folder naming.** Lowercase, hyphenated. `drop-shot/`, not `DropShot/` or `drop_shot/`.

**Dossier structure.** Match `schema.md` exactly. If a rig genuinely needs a section the schema doesn't have, propose the schema change to Brad first — don't fork silently.

**Working notes entries.** Date-stamped, append-only:
```
## YYYY-MM-DD
- Source: [name](url)
- Takeaway: <one line>
- Open question: <if any>
```

**Image prompt versioning.** Each iteration gets its own `## vN` heading with a brief change note. Do not delete old versions — the iteration history is the calibration record.

**Decisions log entries.** Date-stamped, append-only:
```
## YYYY-MM-DD — <short title>
**Context:** <one or two sentences>
**Decision:** <what we decided>
**Rationale:** <why>
**Affects:** <which rigs or files>
```

## Things to avoid

Sponsored content treated as neutral evidence. Sponsor relationships get flagged — see `pro-roster.md` for known affiliations. Sponsorship doesn't disqualify a source, but it must be visible.

AI-generated SEO content, affiliate listicles, and brand-owned content masquerading as editorial. The avoid list lives in `source-hierarchy.md`.

Bloating CLAUDE.md. New conventions go in the right pointer file. This file routes — it doesn't accumulate.

Skipping `working-notes.md`. Every dossier session starts there. Going straight to dossier.md hides contradictions instead of surfacing them.

## When in doubt

Ask Brad before guessing. Especially on: scope additions, schema changes, visual style decisions, anything that affects multiple rigs. A short clarifying exchange is cheaper than an output that has to be redone.
