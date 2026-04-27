# decisions.md

Append-only log of methodological decisions, scope locks, rejected approaches, and deferred items. The point of this file is to prevent re-litigating settled questions and to preserve reasoning that would otherwise get lost between sessions.

## Format rules

- Append new entries at the bottom. Do not edit past entries — if a decision changes, write a new entry that supersedes the old one and reference the original by date and title.
- Date format: `YYYY-MM-DD`. Use the date the decision was actually made, not the date the entry was written if there's a gap.
- Each entry follows this structure:

```
## YYYY-MM-DD — <short title>
**Context:** <one or two sentences>
**Decision:** <what we decided>
**Rationale:** <why>
**Affects:** <which rigs, files, or processes>
```

- Deferred decisions (questions raised but not yet answered) live in a dedicated section at the bottom of this file, separate from the chronological log.

---

## 2026-04-26 — Project scope and species priority locked

**Context:** Project setup conversation between Brad and Claude. Project goal is a series of industrial-design-sketch-style infographics teaching tournament-winning bass rigs to two school-age fishing-team kids. Most TN tournaments are mixed-bag (largemouth, smallmouth, and other allowable species per TWRA rules), which drove a question about how to structure the dossiers around species.

**Decision:** Largemouth bass is the primary species. Smallmouth and other allowable TN species are treated as variants *within* the same rig dossier rather than as separate dossiers. The schema requires a smallmouth variant note for every component section, even if it's "same as largemouth." On clear-water highland reservoirs (Dale Hollow, Center Hill, Norris, Tims Ford), smallmouth-specific adjustments get foregrounded in the Tennessee-specific notes section.

**Rationale:** A separate dossier per species would multiply the work without producing meaningfully different rigs in most cases. The variant-within-dossier pattern matches the actual decision a kid faces on the water — same rig, slightly different setup based on what they're targeting that day.

**Affects:** `schema.md`, every rig dossier.

## 2026-04-26 — Phase 1 rig list

**Context:** Decision on which rigs to include in the first production cycle.

**Decision:** Phase 1 covers ten weighted rigs: Free Rig, Carolina Rig, Texas Rig, Drop Shot, Tokyo Rig, Ned Rig, Jika Rig, Punch Rig, Shaky Head, Football Jig. Hover Rig and Damiki/minnow rig are proposed additions if recent TN tournament evidence supports them, particularly for smallmouth-dominant patterns. Final inclusion gets confirmed in Phase 0 of the actual research session.

**Rationale:** All ten core rigs have established tournament use, distinct rigging requirements, and enough technique nuance to justify their own dossier. Hover and Damiki are deferred because their recent-tournament case is strong but not yet verified for the TN-specific context.

**Affects:** Project scope, production sequencing.

## 2026-04-26 — Wiki structure: Karpathy classic with per-deliverable folders

**Context:** Choice between several wiki-pattern variants — Karpathy classic (three layers + AGENTS.md), per-deliverable folders, Obsidian-vault-as-wiki, research-log pattern.

**Decision:** Karpathy classic combined with per-deliverable rig folders. Each rig is a self-contained deliverable flowing from sources → working notes → dossier → image prompt → final asset. Obsidian deferred. No separate `/creative` or `/meta` folders.

**Rationale:** The per-rig folder structure means saying "work on the drop shot" gives the agent a complete workspace without re-orienting. Obsidian adds friction up front for a project that lives mostly in Claude Code; can be layered on later if browsability becomes useful. The single root-level `style-guide.md` holds palette, callouts, and visual codification together because they're always referenced together.

**Affects:** Repository structure, `CLAUDE.md` folder map.

## 2026-04-26 — CLAUDE.md as router, not encyclopedia

**Context:** Question of whether to put project conventions, schema, style guide, and source rules into CLAUDE.md or split into pointer files.

**Decision:** CLAUDE.md stays short and routes to specifics that live elsewhere. New conventions go in the appropriate pointer file (`schema.md`, `style-guide.md`, `pro-roster.md`, `source-hierarchy.md`), not in CLAUDE.md.

**Rationale:** Karpathy's pattern works because the entry-point file stays small enough that an agent reads it carefully every session. Bloating CLAUDE.md defeats the entire pattern. Pointer files load on demand, which preserves context budget for synthesis work.

**Affects:** `CLAUDE.md`, all pointer files, governance for future additions.

## 2026-04-26 — Phase 0 confirmation gate per session

**Context:** Risk that an agent could begin researching or drafting a dossier without scope confirmation, producing work that has to be redone when scope assumptions turn out to be wrong.

**Decision:** Every session that involves dossier work begins with restating scope and getting explicit Brad confirmation before pulling sources. This is a hard rule in `CLAUDE.md`.

**Rationale:** Bass fishing has enough adjacent rigs and technique variations that ambiguous scope ("work on the Texas rig today") can lead to wildly different outputs depending on whether Brad meant the basic rig, the punch-rig variant, the Tokyo-rig adjacent setup, etc. Cheap up-front exchange beats expensive rework.

**Affects:** `CLAUDE.md`, session workflow.

## 2026-04-26 — Calibration pause after first dossier

**Context:** Risk that structural flaws in the first dossier would propagate across all subsequent dossiers if production proceeds without a review gate.

**Decision:** After the first rig dossier is complete, work pauses for Brad's review before drafting image prompts and before starting the second dossier. The schema and visual approach get refined based on what the first dossier reveals.

**Rationale:** A schema that looks complete in the abstract often shows gaps once it's filled out with real content. Catching those gaps after one dossier is much cheaper than catching them after five.

**Affects:** Per-rig workflow in `CLAUDE.md`, production sequencing.

## 2026-04-26 — Bait specificity defaults to family/material level

**Context:** The schema's "Top 3 baits" section initially implied brand-level specificity. Brad clarified that most consensus in bass fishing actually lives at the bait family or material level — "any 5-inch salt-impregnated stickbait in green pumpkin" rather than "Yamamoto Senko 5-inch #297." Specific brands earn specificity when their action or material is genuinely distinct.

**Decision:** Bait recommendations default to family/material specificity. Brand-level recommendations require either Tier A evidence or consensus across at least three Tier B sources from pros with different sponsorships (see `source-hierarchy.md`). The Keitech 2.8 swimbait is a canonical example of where brand-level specificity is earned — its action genuinely differs from competitors. Most baits are not in that category.

**Rationale:** Over-specifying to brands when the underlying consensus is at family level produces dossiers that look authoritative but actually impose arbitrary choices. Family-level specificity is honest about where the actual agreement lives, and it leaves the kids with usable knowledge ("any premium 5-inch stickbait") rather than brand dependency.

**Affects:** `schema.md` Top 3 baits section, `source-hierarchy.md` consensus rules, every rig dossier.

## 2026-04-26 — Sponsorship as confidence calibration, not corruption flag

**Context:** Initial framing treated sponsor relationships with some suspicion — sponsored endorsements as inherently questionable. Brad reframed: sponsorship is contextual information that affects when corroboration is needed, not a disqualifying signal.

**Decision:** Pro endorsements are weighted on consensus and methodology, not sponsorship status. The `[SPONSOR-FLAG]` inline tag remains in the schema, but its function is to signal "look for independent corroboration" rather than "discount this claim." Where consensus exists across pros with different sponsorships, confidence rises sharply.

**Rationale:** Pros endorse what wins them money — that includes their sponsors' products, but tournament results force them to use what actually catches fish. Treating sponsorship as automatic discrediting throws away signal. The right calibration is: solo claim from a sponsored pro = lower confidence; same claim corroborated across multiple pros with different sponsorships = high confidence.

**Affects:** `pro-roster.md` framing, `source-hierarchy.md` consensus rules, dossier flag interpretation.

## 2026-04-26 — @bassniper weighting and the methodology-not-channel rule

**Context:** @bassniper's empirical methodology — underwater video, controlled comparisons, scientific-method approach — produces a different category of evidence than typical pro YouTube content. Question of how to weight that.

**Decision:** Empirical content with controlled methodology earns Tier A treatment regardless of channel. @bassniper is the canonical example. The same elevation extends to other creators when they apply the same methodology — TacticalBassin running a controlled fluorocarbon comparison earns Tier A for that piece, even though their general "best baits" content is Tier B. The threshold is the methodology, not the channel name.

The @bassniper section in every dossier is required. Confirmations of pro consensus are as valuable as contradictions — both pro experience and underwater video pointing the same direction is the strongest evidence this project will produce.

**Rationale:** Empirical testing produces evidence directly rather than relying on testimony. Brad has identified @bassniper as a unique resource and wants the eventual full corpus extraction. Building the elevated weighting into the source hierarchy from the start ensures his findings get featured rather than buried in a sea of pro endorsements.

**Affects:** `source-hierarchy.md`, `schema.md` required @bassniper section, every dossier.

## 2026-04-26 — Conventional wisdom vs. recent tournament evidence handled as a split, not an average

**Context:** Bass fishing has decades of accumulated dogma, some of which is genuinely outdated. Recent tournament winners are sometimes doing things that contradict longstanding "rules." The dossier could either pick one, average them, or surface the split explicitly.

**Decision:** When recent tournament winners contradict conventional wisdom, the dossier surfaces both as a feature moment with this format:

```
**Conventional wisdom:** <what was standard 5+ years ago>
**Recent tournament evidence:** <what 2024–2026 winners are actually doing> [cited]
**Why it changed:** <if known>
```

**Rationale:** Picking one or averaging hides information that's actually useful for the kids. Showing both teaches them how the sport evolves and why specific choices win — that's a more durable lesson than memorizing the current correct answer.

**Affects:** `schema.md` special patterns section, every dossier where the split exists.

## 2026-04-26 — White halo confirmed as load-bearing visual element

**Context:** Visual style derived from reference images (carabiner, glue gun, fire extinguisher) showing a thick white outline tracing each object's silhouette, separating it from background marker swatches.

**Decision:** The white halo is non-negotiable for every infographic. Every image prompt explicitly reinforces it. Image-gen output that loses the halo is treated as a calibration failure requiring prompt iteration.

**Rationale:** Without the halo, the marker swatches behind the object visually merge with the object itself and the entire compositional structure of the style collapses. It's also the detail image-gen models most reliably skip, which makes explicit reinforcement necessary.

**Affects:** `style-guide.md`, every image prompt in every `image-prompts.md`.

## 2026-04-26 — Per-rig accent color palette proposed, pending Phase 0 confirmation

**Context:** Need to assign each rig a dominant chromatic accent that supports memorization (the kids should associate "the red one" with Texas Rig before reading the title) without color collisions on comparison sheets.

**Decision:** Initial proposed palette documented in `style-guide.md`: Texas (crimson red), Carolina (forest green), Free Rig (burnt orange), Drop Shot (cobalt blue), Ned (teal), Shaky Head (warm gray + olive), Football Jig (chocolate brown), Tokyo (deep purple), Jika (mustard yellow), Punch (magenta). Final palette confirmed during Phase 0 of the first research session.

**Rationale:** Each color is distinctive enough to read at a glance, distinct from the others to avoid confusion on comparison sheets, and resonant with the rig's identity where possible (brown matches the football jig's actual skirt color, magenta keeps the punch rig aggressive).

**Affects:** `style-guide.md`, all visual outputs. Subject to Phase 0 override.

## 2026-04-26 — Image gen fallback to human illustrator brief

**Context:** Spencer Nugent–style marker rendering is one of the harder aesthetics for image generation to nail — deeply hand-made, with specific imperfections (overshoot, streak, halo) that don't show up in training data nearly as densely as photorealistic or vector outputs. ChatGPT Image 2.0 may have closed that gap, but the project shouldn't depend on it.

**Decision:** If image generation hits a quality ceiling that meaningful prompt iteration can't break through, the same project documentation (`style-guide.md` + per-rig dossier + reference images) becomes a clean brief for a human illustrator. No work is lost in that transition.

**Rationale:** Building the documentation thoroughly enough to guide either path means we aren't gambling the project's quality on the assumption that current image-gen tools can match a hand-drawn aesthetic. If they can, faster and cheaper. If they can't, we have a clean fallback.

**Affects:** `style-guide.md` fallback section, production sequencing.

## 2026-04-26 — Flag inventory expanded with [STALE] and [TN-LOCAL]

**Context:** While drafting `source-hierarchy.md`, identified two evidentiary states the existing flags didn't cover cleanly: pre-2024 sources without recent corroboration, and reservoir-specific claims that shouldn't be presented as universal. Both situations were arising naturally in the source ranking work.

**Decision:** Added `[STALE]` and `[TN-LOCAL]` to the dossier flag inventory. `[STALE]` marks pre-2024 sources without recent corroboration — the claim may still be valid but reflects older practice. `[TN-LOCAL]` marks reservoir-specific or TN-specific claims that should not be generalized, often the right framing for highland-reservoir smallmouth patterns.

**Rationale:** Honest tagging beats implicit handling. Both situations were going to come up repeatedly; making them visible in the dossier gives readers (and future research passes) the confidence-calibration signal they need.

**Affects:** `schema.md` flag inventory, `source-hierarchy.md`, every dossier going forward, dossier validation checklist.

## 2026-04-26 — Callout density target raised

**Context:** Initial `style-guide.md` set the per-sheet callout target at 3–7. Brad's stated preference is "the more info we can add while still feeling like art pieces, the better" — meaning the original target was too restrictive against actual project goals.

**Decision:** Density target raised to 5–10 primary callouts plus secondary annotations (knot insets, pro-tip boxes, conditions reference). The constraint is the wall-hangable test rather than a fixed count: if a sheet stops looking like an art piece and starts looking like a reference card, density has crossed the threshold. When in doubt, push density up rather than down.

**Rationale:** Memorization aids work harder when they carry more information per glance, and Brad has explicitly prioritized density over restraint within the art-piece quality bar. The wall-hangable test is the right governing constraint because it's binary (does this still look like art? yes/no) rather than arbitrary.

**Affects:** `style-guide.md`, every infographic.

## 2026-04-27 — Phase 0 lock for first production session

**Context:** First research session opened. Phase 0 confirmation gate per `CLAUDE.md` and the 2026-04-26 confirmation-gate entry. Brad confirmed scope, first rig, palette approach, watermark policy, and species-grouping treatment.

**Decision:**
- **First rig is Drop Shot.** Selected because it exercises every section of the schema (leader, terminal hardware, smallmouth variant on highland reservoirs) and produces the cleanest calibration signal for both schema and visual style.
- **Hover Rig and Damiki/minnow rig are out of Phase 1.** Supersedes the 2026-04-26 "Phase 1 rig list" deferral on these two. Reconsider in a later phase if recent TN tournament evidence surfaces a strong case.
- **No logo, watermark, or signature is rendered on the infographics.** Brad will apply his own mark to finished sheets after the fact. Supersedes the 2026-04-26 deferred "Signature/watermark" item. `style-guide.md` updated to reflect.
- **Spotted/Kentucky bass remain grouped under "other allowable TN species."** No dedicated variant note added to the schema. Reservoir-specific spotted-bass patterns surface in the Tennessee-specific notes section with `[TN-LOCAL]` tagging if they appear. Resolves the 2026-04-26 deferred item.
- **Per-rig accent palette as proposed in `style-guide.md` is locked as the working palette.** Best-judgment overrides allowed mid-stream when an actual collision shows up in rendering or comparison-sheet layout — log the swap here when it happens. Resolves the 2026-04-26 deferred "Final accent color palette" item.

**Rationale:** Drop Shot first preserves calibration value. Hover/Damiki lack the verified TN tournament base to justify Phase 1 inclusion. Brad applying his own mark removes a moving target from every image prompt. Spotted/Kentucky bass patterns haven't surfaced as deep enough to justify their own variant treatment; keeping the schema tight is worth more than pre-emptive structural complexity. Locking the palette without re-litigating each color frees the session for content; the visual style guide is robust enough to absorb a swap if one is needed.

**Affects:** `style-guide.md` (single-rig sheet composition + palette section header), `rigs/drop-shot/` (next workspace), Phase 1 scope (10 rigs not 12), schema unchanged.

## 2026-04-27 — Sponsorship is non-blocking when actual usage is documented

**Context:** Brad's framing during Phase 0 lock: "I couldn't care less who pays them, but I definitely want to know what they catch them on." This sharpens the 2026-04-26 "confidence calibration, not corruption flag" stance.

**Decision:** Sponsorship is not a blocker on a claim. The relevant question is whether the pro is actually fishing the bait/component they credit with the win. The `[SPONSOR-FLAG]` inline tag in the schema remains — it's still useful audit metadata — but its presence does not require a non-sponsored corroborating source before a claim can stand. Tournament-documented usage by a sponsored pro is evidence in its own right. The "consensus across pros with different sponsorships" threshold in `source-hierarchy.md` for component-level brand specificity is treated as a heuristic, not a hard gate: when sponsored pros across multiple brands all converge on the same usage, that's the same signal under a different label, and the brand-specific claim earns its place.

**Rationale:** Tournament results force pros to throw what catches fish. Treating sponsorship as a blocker introduces a bias against actual usage data, which is the highest-signal evidence available. The existing methodology was already in this direction; this entry tightens it so dossier work doesn't over-cautiously downgrade tournament-cited brand-specific claims.

**Affects:** `source-hierarchy.md` interpretation (no rewrite — heuristic framing), `pro-roster.md` framing (no structural change), `[SPONSOR-FLAG]` usage in every dossier.

## 2026-04-27 — Research protocol locked

**Context:** Session 1 (2026-04-27) collapsed before per-rig dossier work began. Three failure patterns: raw web pages bloated main context every turn; parallel fetches hit 503 from rate-limited fishing sites; many target domains hard-block Anthropic's WebFetch entirely. YouTube content (mandatory @bassniper coverage per `CLAUDE.md`) is also unreachable via WebFetch. Session 2 designed the protocol to prevent recurrence, working from `the-loadout.md` (now distilled and deleted) as the candidate-tools framework.

**Decision:** Locked `research-protocol.md` at repo root with six sections:

1. **Per-rig workflow — Subagent fork/merge.** Three parallel subagents per rig (component specs / TN-local + tournament / @bassniper empirical), each producing a ≤500-word structured report. Reports are what land in main context; raw fetched pages do not.
2. **Web-fetch stack.** Playwright MCP + a free YouTube transcript MCP. Hard constraint: completely free. Firecrawl, Browserbase, and Apify rejected on cost.
3. **Source-caching rule.** Every fetched excerpt is saved to `sources/articles/` or `sources/transcripts/` before being cited. Codifies existing practice.
4. **Rate-limit-aware fetch discipline.** Sequential not parallel; exponential backoff (1s → 32s); three-strikes abort with WebSearch snippet fallback as lead-only (not citable). Blocked URLs go to `sources/articles/blocked.md`.
5. **Pre-seeding workflow for YouTube.** Brad drops transcripts into `sources/transcripts/` before the session starts; Subagent C reads pre-seeded transcripts first.
6. **Token discipline.** Source-excerpts-stay-out-of-main-context is the load-bearing rule. Subagent fork/merge implements it. `/compact` between rigs, `/clear` between sessions. CLAUDE.md stays under 200 lines.

Two phases carved out into their own chats, in order:
- **Phase A — Fetch-tool installation and validation.** Runs before session 3. Install both MCPs, validate against ≥3 blocked URLs, append a test report to `research-protocol.md`, delete `next-session-brief.md`.
- **Phase B — Skill packaging.** Runs immediately after the protocol is exercised end-to-end on drop-shot in session 3. Package as `.claude/skills/per-rig-research/SKILL.md` so `/per-rig-research <rig-name>` becomes the standard entry point for every rig in every new session. Skill is committed, not optional.

`the-loadout.md` is deleted as part of this entry — its content is distilled into `research-protocol.md` and was always temporary per the brief.

**Rationale:** Subagent fork/merge keeps raw pages out of main context, which is the single biggest input-token win available to this project — input tokens dominate long research sessions because every turn re-sends the full context. Subagents beat agent teams on cost (no peer-debate value across the three independent research domains) and beat single-session on context discipline. Playwright MCP is the only browser-automation stack that meets the completely-free constraint. The "test first, package immediately after" sequencing for the skill exists so the skill body reflects what actually worked, not what was planned. Carving out installation/validation and skill packaging into separate chats prevents the protocol-design session from over-extending the same way session 1 did.

**Affects:** `research-protocol.md` (new), `CLAUDE.md` (folder map + per-rig workflow cross-references + load-on-demand entry), `the-loadout.md` (deleted), every per-rig research session going forward, the skill packaging in Phase B, the fetch-tool install in Phase A.

---

## Deferred decisions

Items raised but not yet settled. Resolve and convert to a dated entry above when decided.

**Highland reservoir / smallmouth-specific dossiers.** Whether smallmouth-dominant reservoirs (Dale Hollow, Center Hill, Norris, Tims Ford) eventually warrant their own dossier set distinct from the largemouth-primary core. Currently handled as variants within each rig dossier, but if the smallmouth-specific patterns turn out to be deep enough, they could justify a parallel series. Revisit after the first three dossiers reveal how much smallmouth content the variant approach actually carries.

**Comparison sheet content rules.** Single-rig sheets are well-specified. Comparison sheets ("Texas vs. Carolina vs. Free") need explicit rules for which components get shared callouts vs. duplicate ones, and whether the comparison is structured as parallel diagrams or a unified split-rig diagram.

**Family poster scope.** Family posters (e.g., "Weighted Soft-Plastic Rigs") are mentioned in `style-guide.md` but not specified as a Phase 1 deliverable. Decide after the per-rig sheets reveal which families have enough cohesion to justify a poster.
