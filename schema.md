# schema.md

This file defines the dossier structure every rig follows. Same headers, same order, same fields, every time. Uniformity across the series is what makes the kids' memorization work — when "Top 3 baits" is always the fifth section, they know where to look.

If a rig genuinely needs a section this schema doesn't have, propose the schema change to Brad first. Do not fork silently. Schema changes go in `decisions.md` with rationale and an `Affects:` line listing rigs that need backfilling.

## Rules

**Headers are fixed.** Same H1 (rig name), same H2s, same H3s, same order, every dossier.

**Inline citations everywhere.** Citation format is `[Source Name, YYYY](URL)` per `CLAUDE.md`. The full flag inventory and their dossier-level meanings live below in the Special patterns section. Tier-by-tier source ranking lives in `source-hierarchy.md`.

**No empty sections.** If a section genuinely doesn't apply (e.g., no leader on a straight Texas rig), write `Not used in this rig — <one-line reason>`. Don't delete the heading.

**"If applicable" fields.** Some rigs have no leader, no terminal hardware, no smallmouth variant worth calling out. Use the "Not applicable" pattern above rather than omitting.

**@bassniper section is required.** Even if his channel hasn't covered this rig directly, write `No @bassniper coverage found as of <date>. Searched: <terms>.` Documenting the absence is part of the audit trail.

## Dossier template

Copy this into `rigs/<rig-name>/dossier.md` and fill it in. Don't reorganize the headings.

````markdown
# <Rig Name>

**Stability:** classic/stable | currently evolving
**Stability rationale:** <one sentence — why it's stable, or what's currently shifting>
**One-line definition:** <plain-language description, one sentence, written for a 10-year-old>

## Variants

- **<Variant 1 name>:** <what makes it different, when to use it>
- **<Variant 2 name>:** <...>

(If no meaningful variants, write "No variants — the standard rig is the only form in tournament use.")

## Components

### Mainline
- **Brand/model:** [Brand Model](url)
- **Type:** mono | fluoro | braid
- **Test:** X lb
- **Why this choice:** <reasoning with citation>
- **Smallmouth variant (if different):** <spec change + reasoning>

### Leader
- **Used?:** yes | no
- **Brand/model:** ...
- **Type:** ...
- **Test:** ...
- **Length:** ...
- **Why this choice:** ...
- **Smallmouth variant (if different):** ...

### Hook
- **Brand/model:** [Brand Model](url)
- **Style:** EWG | straight shank | offset round bend | drop shot | etc.
- **Size:** X/0 or #X
- **Why this choice:** ...
- **Smallmouth variant (if different):** ...

### Weight
- **Brand/model:** ...
- **Material:** tungsten | brass | lead
- **Style:** bullet | cylinder | drop-shot pencil | free-rig pencil | football | etc.
- **Weight range:** X oz – Y oz
- **When to size up vs. down:** ...
- **Smallmouth variant (if different):** ...

### Terminal hardware
- **Used?:** yes | no
- **Beads:** brand, size, color, purpose
- **Swivels:** brand, size, type (barrel | ball-bearing | snap)
- **Pegs/bobber stops:** brand, type, when used
- **Other:** snaps, clips, rings — brand and purpose

### Knots

Knots that materially affect performance for this rig. Skip knots that don't move the needle — listing every possible knot dilutes the signal.

- **Mainline-to-leader (if applicable):** <knot name> — <why it matters here, cited>
- **Hook-to-line:** <knot name> — <why it matters here, cited>
- **Other performance-critical:** <if any>

## Top 3 baits

Each bait gets a confidence tier, evidence, and sponsor flag if applicable. Default specificity is bait family / material level (e.g., "any premium 5-inch salt-impregnated stickbait, green pumpkin"). Brand-level specificity is reserved for cases where a specific product's action or material is genuinely distinct — the Keitech 2.8 swimbait is the canonical example — and requires either Tier A evidence or consensus across at least three Tier B sources from pros with different sponsorships. See `source-hierarchy.md` for consensus thresholds and `decisions.md` 2026-04-26 entry for the rationale.

### 1. Confidence pick: <bait specification — family-level by default, brand-level only when earned>
- **Color:** <pattern name and conditions it suits>
- **Size:** <inches or oz>
- **Rigging orientation:** <how it goes on the hook>
- **Evidence:** <tournament result or pro endorsement, cited inline>
- **Sponsor flag:** [SPONSOR-FLAG: <pro> sponsored by <brand>] — applicable | none found

### 2. Situational: <bait specification>
- **Best for:** <specific conditions>
- (same fields as above)

### 3. Situational: <bait specification>
- **Best for:** <specific conditions>
- (same fields as above)

## When it excels

- **Season:** <pre-spawn | spawn | post-spawn | summer | fall | winter | year-round> — <what's happening biologically>
- **Water temp range:** <X–Y °F>
- **Depth range:** <X–Y ft>
- **Cover/structure:** <grass, rock, brush, points, ledges, docks, etc.>
- **Water clarity:** <stained | clear | muddy — and what changes>
- **Weather:** <post-front, pre-front, stable, wind direction, cloud cover>
- **Time of day:** <if it matters>

## Tennessee-specific notes

- **Reservoirs where it shines:** <named reservoirs with one-line reason for each>
- **Reservoirs where it underperforms:** <if any pattern exists>
- **TVA current/generation effects:** <how generation schedule affects this rig — applicable to TVA-managed lakes>
- **Smallmouth vs. largemouth on TN waters:** <where the species difference changes the playbook — especially on Dale Hollow, Center Hill, Norris, Tims Ford>
- **Local pro patterns:** <what TN-based pros do specifically with this rig — DeFoe, Strader, Walker, Coulter, Morgan>

## Working technique

- **Rod:** <length, action, power — with brand/model if there's strong consensus>
- **Reel:** <type, gear ratio, with brand/model if relevant>
- **Line interaction:** <how the line type affects feel, hookset, sensitivity>
- **Cadence/retrieve:** <step-by-step description of how to work it>
- **Hookset:** <sweep, snap, reel-set — with reasoning>
- **Boat positioning:** <if it matters — long cast, vertical, dragging, etc.>

## @bassniper empirical findings

Required section. Document where his underwater testing and scientific-method approach intersects with this rig. Confirmations are as valuable as contradictions — if pro wisdom and underwater video agree, that's high-confidence signal worth featuring.

If no coverage exists, document the search:

```
No @bassniper coverage found as of YYYY-MM-DD.
Searched: <list search terms used>
```

Otherwise, format each relevant finding as:

- **What he tested:** <variable, condition, comparison>
- **Finding:** <what the underwater video or controlled test showed>
- **Pro consensus says:** <what conventional wisdom holds>
- **Verdict:** confirms | contradicts | partial agreement | nuanced
- **Why it matters for our kids:** <one-line takeaway>
- **Source:** [video title](url)

## Failure modes

- **When not to throw it:** <conditions where another rig is clearly better>
- **Common rigging mistakes:** <what kids will get wrong, and what the consequence is>
- **When a similar rig outperforms:** <e.g., "in heavy slop, the Punch Rig outperforms — see punch-rig/dossier.md">
- **Reading the rig is wrong:** <signs from feel/bites that you've sized wrong, knotted wrong, etc.>

## Sources

Consolidated source list. Inline citations throughout the dossier are the primary mechanism — this section is the audit trail.

1. [Source name, YYYY](url) — <one-line note on what this source contributed>
2. [Source name, YYYY](url) — ...
3. ...

````

## Special patterns

### Full flag inventory

The complete set of inline flags used in dossiers. Their evidentiary meanings and tier interactions live in `source-hierarchy.md`; the table below covers what each one looks like in a dossier and what it tells the reader.

- **`[CONTESTED]`** — Multiple credible sources disagree. Requires a follow-up line explaining the disagreement and the conditions driving it.
- **`[THIN]`** — Single source, no corroboration found. Acceptable when tagged honestly; the flag carries the confidence level.
- **`[STALE]`** — Pre-2024 source with no recent corroboration. The claim may still be valid but reflects older practice.
- **`[TN-LOCAL]`** — Reservoir-specific or TN-specific claim that should not be presented as universal. Often the right framing for highland-reservoir smallmouth patterns.
- **`[community-consensus]`** — Pattern observed across three or more independent forum or community voices on different threads or platforms. Lower individual evidence per source, but the pattern itself is the signal.
- **`[SPONSOR-FLAG]`** — Pro endorsement aligns with a known sponsor relationship. Per `decisions.md` 2026-04-26, this is a confidence-calibration signal, not a corruption flag — independent corroboration raises confidence rather than the flag automatically discrediting the claim.

### Smallmouth variants

When the spec genuinely changes, call it out as a sub-bullet under the relevant component (lighter line, smaller hook, lighter weight, color shift). When the spec is the same but the *application* differs (same rig, different retrieve cadence on smallmouth), document it under "Tennessee-specific notes" instead. Don't duplicate.

### Tournament-proven vs. conventional wisdom split

When recent tournament winners are doing something different from longstanding conventional wisdom, that's a feature moment. Surface it explicitly — don't average them or pick one. Format:

```
**Conventional wisdom:** <what was standard 5+ years ago>
**Recent tournament evidence:** <what 2024–2026 winners are actually doing> [cited]
**Why it changed:** <if known>
```

### Contested claims

Tag inline with `[CONTESTED]` and explain in a footnote-style line directly under the claim:

```
Best hook for this rig is a 4/0 Owner Jungle Flippin' [Pro A, 2025](url) [CONTESTED]
**[CONTESTED]:** Pro B argues a 3/0 EWG is better in <conditions> [Pro B, 2025](url). Disagreement appears driven by <variable>.
```

### Thin claims

Tag with `[THIN]` when only one source exists and you couldn't find corroboration:

```
The 2.8 Keitech in Sexy Shad is the dominant choice on Center Hill in fall [Pro C, 2024](url) [THIN]
**[THIN]:** Single-source claim, no community corroboration found. Worth verifying in next research pass.
```

## Validation checklist

Before declaring a dossier complete, confirm yes to all:

- [ ] Every H2 section from the template is present (no missing headings, even if marked "Not applicable")
- [ ] Every component has a brand and a specific model — no generic placeholders
- [ ] Every factual claim has an inline citation
- [ ] At least one TN-specific reservoir is named with a reason
- [ ] Smallmouth variant addressed in every component section (either with spec or "same as largemouth")
- [ ] @bassniper section is present (with findings or with documented absence)
- [ ] All flagged claims (`[CONTESTED]`, `[THIN]`, `[STALE]`, `[TN-LOCAL]`, `[community-consensus]`, `[SPONSOR-FLAG]`) include the appropriate explanation or context line
- [ ] Sources section consolidates everything cited inline
- [ ] Failure modes section names a specific competing rig where one exists
- [ ] Working technique includes rod, reel, retrieve cadence, and hookset

If any answer is no, the dossier is in working state, not complete state. Keep iterating in `working-notes.md` and update the dossier when the gap is filled.
