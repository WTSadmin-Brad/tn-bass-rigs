# Research protocol

The protocol that governs per-rig research sessions for this project. Locks the workflow that prevents the context-bloat / blocked-domain / parallel-fetch failures observed in session 1 (2026-04-27 — see `decisions.md` 2026-04-27 entry "Research protocol locked").

This is the human-readable canonical spec. Once the protocol has been exercised end-to-end on the first rig (drop-shot, session 3) and confirmed working, it gets packaged as the `/per-rig-research` skill (see § Carved-out phases) and the skill becomes the standard entry point for every subsequent rig.

## 1. Per-rig research workflow — Subagent fork/merge

Every rig is researched by **three subagents running in parallel from the main session.** Each scopes to one research domain, pulls its own sources, files them to disk, and returns a ≤500-word structured report. The report is what lands in main context — **never** the underlying fetched pages.

### Subagents

**Subagent A — Component specs.**
- Domain: brand-and-model-level component data (hooks, weights, line, leader, rod, terminal hardware).
- Source tier: A and B per `source-hierarchy.md`.
- Output sections: maps to the schema's component sections in `schema.md`.
- Brand specificity bar: per the 2026-04-26 "Bait specificity defaults to family/material level" decision, default to family/material level; brand-level claims need either Tier A evidence or convergent Tier B from pros with different sponsorships.

**Subagent B — TN-local + tournament evidence.**
- Domain: TN reservoir-specific patterns, tournament results (BASS, MLF, NPFL, regional TN circuits), smallmouth variants on highland reservoirs (Dale Hollow, Center Hill, Norris, Tims Ford).
- Inline-tag with `[TN-LOCAL]` per `schema.md`.
- Output prioritizes the rig's Tennessee-specific notes section per the schema.

**Subagent C — @bassniper empirical.**
- Domain: empirical underwater-video evidence, controlled comparisons.
- **Required dossier section** per `CLAUDE.md` and the 2026-04-26 @bassniper-weighting decision.
- Methodology-elevation: Tier A treatment for any controlled empirical content from any creator, not just @bassniper.
- Reads `sources/transcripts/` first; only fetches new transcripts after the pre-seeded set is exhausted.

### Subagent invocation

Each subagent gets:
- `tools` allowlist: `WebFetch`, `WebSearch`, `Read`, `Write`, `Grep`.
- Context references: `schema.md`, `source-hierarchy.md`, the rig's `working-notes.md`, the `sources/articles/` and `sources/transcripts/` directories, and `sources/articles/blocked.md` (the rate-limit-aware domain list).
- Hard instructions: file every fetched excerpt to `sources/articles/<descriptive-name>.md` (or `sources/transcripts/`) **before** drafting the report; cite by file path in the report; never inline raw page content in the report body.

### Structured report schema

Workflow-agnostic — applies regardless of orchestration choice. The report is the artifact that lands in main context.

```
## Research report — <Rig> — <Domain> — <YYYY-MM-DD>

**Sources consulted** (filed to `sources/articles/` or `sources/transcripts/`):
- `<file-name>.md` — <one-line takeaway>

**Findings** (≤500 words, bullet form, every claim cites a source file):
- ...

**Contradictions / open questions:**
- ...

**Confidence flags applied:** [CONTESTED] [THIN] [STALE] [TN-LOCAL] [community-consensus] [SPONSOR-FLAG]
```

### Why subagents (not single session, agent teams, or `/batch`)

- **Single session** — what session 1 used. Re-creates the context-bloat failure.
- **Agent Teams** — peer mesh, experimental, higher cost (N independent contexts). The three research domains don't need to argue with each other; no peer-debate value to justify the cost.
- **`/batch`** — for mechanically similar changes across many files, not citation-heavy research.
- **Subagent fork/merge** — heavy isolated work where only the conclusion matters. The canonical "Repetitive structured research" pattern.

## 2. Web-fetch tool stack

Anthropic's WebFetch returns 503 from many fishing sites and cannot reach YouTube. The protocol uses a free local stack:

- **Playwright MCP** — local FOSS browser-based fetch. Handles JS-heavy and bot-blocked domains. Completely free.
- **A free YouTube transcript MCP** — specific tool finalized during the carved-out fetch-tool installation phase.

**Rejected** (fail "completely free" hard constraint): Firecrawl (metered free tier exhausts at normal volume), Browserbase (paid), Apify (pay-per-use beyond limited free actors).

Installation, configuration, and validation against ≥3 previously-blocked URLs are carved out into Phase A — see § Carved-out phases.

## 3. Source-caching rule

**Every fetched excerpt is saved to disk before being cited.** Re-fetch is never required across sessions or follow-up subagents — the cache is the source of truth.

- **Articles, tournament reports, brand pages** → `sources/articles/<descriptive-name>.md`.
- **Video transcripts** → `sources/transcripts/<descriptive-name>.md`.

File header format:

```markdown
# <Source title>

**URL:** <url>
**Author / channel:** <name>
**Date:** <YYYY-MM-DD>
**Tier:** A/B/C per `source-hierarchy.md`
**Flags:** [STALE] [TN-LOCAL] etc.

## Extracted findings
- ...

## Notes
- ...
```

## 4. Rate-limit-aware fetch discipline

Empirical from session 1: parallel fetch batches of 6 hit 503 immediately; sequential calls survived.

- **Sequential, not parallel.** Subagents run in parallel with each other, but each subagent fetches its own sources sequentially.
- **Exponential backoff** on transient failure: 1s → 2s → 4s → 8s → 16s → 32s, then abort that URL.
- **Three-strikes abort.** After 3 retry failures on a domain, drop to WebSearch snippet capture as a **lead only** — explicitly NOT citable per the verification rule in `CLAUDE.md`. Add the URL to `sources/articles/blocked.md` with the snippet hint marked `DO NOT CITE — leads only`.
- **Domain triage at session start.** Subagents read `sources/articles/blocked.md` first and skip URLs on the blocked list.

## 5. Pre-seeding workflow for YouTube

When Brad has specific YouTube videos in mind for a session:

1. **Before the session starts**, Brad drops the transcript into `sources/transcripts/`, named `<channel>-<topic>-<YYYY-MM>.md`.
2. The file header includes URL, channel, video title, publish date, and the transcript paste.
3. Subagent C reads `sources/transcripts/` first and only invokes the YouTube transcript MCP after the pre-seeded set is exhausted.

Once the YouTube transcript MCP is installed and validated, pre-seeding becomes optional — but still preferred for transcripts Brad already has in hand, to skip the MCP call entirely.

## 6. Token discipline

**Framing:** input tokens dominate in long Claude Code research sessions because every turn re-sends the full context. Output-side compression (Caveman-style) has limited ROI for citation-heavy work.

| Technique | Where it lives | Rationale |
|-----------|----------------|-----------|
| Source-excerpts-stay-out-of-main-context | This file § 1 + § 3 | The single biggest input-token win for this project. Raw pages live in subagent contexts or on disk; main thread sees only ≤500-word reports. Session 1 died from raw pages in main context. |
| Subagent fork/merge for per-rig research | This file § 1 | Implementation of the rule above. |
| `/compact` and `/clear` discipline | Per-session command | Compact between rigs (every per-rig workflow ends with one). Clear when starting an unrelated session. Preserve: dossier and decisions changes. Drop: raw fetches and exploration chatter. |
| CLAUDE.md hygiene — under 200 lines | `CLAUDE.md` (already enforced) | Long CLAUDE.md files reduce adherence to their own rules. Bulk lives in pointer files. |
| `/per-rig-research` skill | `.claude/skills/per-rig-research/SKILL.md` (Phase B) | Body loads only on invocation. Description (≤250 chars) is the only always-loaded tax. Standard entry point for every rig in every new session once packaged. |

## Carved-out phases

Two phases run in their own dedicated chats, in this order:

### Phase A — Fetch-tool installation and validation

Runs **before session 3** so drop-shot synthesis isn't blocked on tooling problems.

- Install Playwright MCP and a free YouTube transcript MCP.
- Validate against ≥3 previously-blocked URLs from session 1's blocked-domain list (see `next-session-brief.md` § "Domains confirmed blocked at WebFetch in session 1").
- Append a test report to the bottom of this file (`research-protocol.md`).
- Add a `decisions.md` entry capturing the validation outcome.
- Delete `next-session-brief.md` once the test report is appended.

### Phase B — Skill packaging

Runs **immediately after** the protocol has been exercised end-to-end on the drop-shot rig in session 3 and confirmed working.

- Package the per-rig research procedure as `.claude/skills/per-rig-research/SKILL.md`.
- Skill body is a thin wrapper that loads this file and dispatches the three subagents.
- Skill description (≤250 chars) names the trigger and the report contract.
- This file (`research-protocol.md`) remains at repo root as the human-readable canonical spec.
- Update `CLAUDE.md` Per-rig workflow to invoke `/per-rig-research <rig-name>` as the standard entry point.
- Add a `decisions.md` entry covering what got packaged and why.

The skill is **committed, not optional.** "Test first, package immediately after" sequencing exists so the skill body reflects what actually worked, not what was planned.
