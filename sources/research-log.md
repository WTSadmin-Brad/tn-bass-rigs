# Research log

Chronological dig log per CLAUDE.md folder map. Each entry is a session or
carved-out phase, dated, with what was done, what got cached, and what's
still owed. Append-only.

---

## 2026-04-27 — Session 1: Drop-shot research kickoff

- Phase 0 lock: Drop Shot first, palette locked, no watermark, spotted/Kentucky
  bass grouped under "other allowable TN species" (commit `f1445a4`).
- Pulled 12 source excerpts to `sources/articles/` (commit `40deda5`). All 12
  carry URL, author, date, tier, extracted findings, and notes per the protocol
  § 3 file header. List in the original `next-session-brief.md` (now deleted —
  see commit `40deda5` for the file inventory).
- Hit context-bloat from raw web pages staying in main thread, plus 503 and 403
  responses from many target domains under WebFetch. Session ended in repeated
  API errors before per-rig synthesis began.
- Working-notes synthesis from the 12 cached excerpts deferred to session 3.
- `sources/articles/blocked.md` not yet created.

## 2026-04-27 — Session 2: Research protocol designed and locked

- Locked `research-protocol.md` at repo root (commit `adeb0bc`) covering: subagent
  fork/merge per-rig workflow, Playwright + free YouTube transcript MCP fetch
  stack, source-caching rule, sequential rate-limit discipline with three-strikes
  abort, YouTube pre-seeding workflow, and token discipline.
- Carved Phase A (fetch-tool install + validation) and Phase B (skill packaging)
  into dedicated chats.
- Distilled and deleted `the-loadout.md` (the temporary candidate-tools doc).
- `decisions.md` "Research protocol locked" entry added.

## 2026-04-27 — Phase A: Fetch-tool installation and validation

- Installed `@playwright/mcp@latest` (v0.0.70) and
  `@kimtaeyoon83/mcp-server-youtube-transcript` (v0.1.1) at user scope. Both
  `✓ Connected` per `claude mcp list`. (commit `35d14a8`)
- Validated Playwright against three previously-blocked domains: wired2fish.com,
  majorleaguefishing.com, bassresource.com — all returned 200 with real content.
- Pulled @bassniper "Drop Shot Length, Weight, and Bait Testing" (2020-03-04)
  end-to-end — 549 segments / 20,752 chars. Pre-seeded to
  `sources/transcripts/bassniper-drop-shot-length-weight-bait-2020-03.md`.
- Caveat logged: westernbass.com and onthewater.com return Cloudflare bot
  challenges under headless Chromium. Workaround menu in research-protocol.md
  Phase A test report.
- Test report appended to `research-protocol.md`. `next-session-brief.md` deleted.

## 2026-04-27 — Session 3: Drop-shot synthesis (protocol exercised end-to-end)

- First end-to-end exercise of `research-protocol.md`. Three subagents dispatched
  in parallel (single message) per § 1: Subagent A — Component specs, Subagent B —
  TN-local + tournament, Subagent C — @bassniper empirical. All three returned
  ≤500-word structured reports per the protocol contract. Raw page bodies stayed
  in subagent contexts; main thread saw only the reports.
- Sources newly cached: 12 articles + 5 transcripts. Total cache after session 3:
  24 articles + 6 transcripts. Every excerpt carries the protocol § 3 file header.
- Articles filed (this session): `mikeiaconelli-blog-mastering-dropshot-2024.md`,
  `mlf-strader-watts-bar-profile.md`, `mlf-martens-drop-shot-101-2019.md`,
  `mlf-wheeler-table-rock-stage-seven-2019.md`,
  `wired2fish-dale-hollow-truth-2025.md`,
  `wired2fish-meyer-bubba-shot-2021.md`,
  `wired2fish-defoe-southern-drop-shot-2024.md`,
  `wired2fish-palaniuk-a-list-2022.md`,
  `wired2fish-meyer-wacky-drop-shot-2019.md`,
  `bassresource-palaniuk-rojas-cruising-2016.md`,
  `basscast-clevenger-cherokee-bfl-2024.md`,
  `aa-fishing-tims-ford-bass-report.md`.
- Transcripts filed (this session):
  `bassfishinglife-drop-shot-leader-length-2025-05.md`,
  `bassfishinglife-drop-shot-retrieve-2025-08.md`,
  `bassfishinglife-drop-shot-rage-swimmer-2025-10.md`,
  `tacticalbassin-drop-shot-clearwater-smallmouth-2018-02.md`,
  `derekkira-drop-shot-schooling-coldfront-2020-03.md`.
- Synthesis: `rigs/drop-shot/working-notes.md` updated with cross-source bullets
  organized by dossier topic, and `rigs/drop-shot/dossier.md` created
  schema-strict per `schema.md`. All inline citations carry source name and URL.
  Stop gate held — no `image-prompts.md` drafted; awaiting Brad's dossier review
  per the 2026-04-26 calibration-pause decision.
- Major cross-source finding: **the TN drop-shot game is bifurcated** into
  highland-reservoir smallmouth finesse and TVA-largemouth power-finesse; two
  sub-rigs share a name but very little gear. Surfaced in the dossier's
  Tennessee-specific notes section using the conventional-wisdom-vs-recent-tournament
  split format from the 2026-04-26 decisions entry.
- Methodology-not-channel rule (`decisions.md` 2026-04-26) actively applied:
  three Bass Fishing Life controlled-comparison transcripts elevated to Tier A
  and embedded in the @bassniper section alongside the pre-seeded @bassniper
  source. Schema-question on whether to rename that section "Underwater empirical
  findings" raised in `working-notes.md` for Brad's review.
- Operational findings: rate-limit discipline held — no 503 cascades observed;
  cache-first reading kept Subagent A and B's fetch volumes manageable.
  Cloudflare-protected domains avoided per the Phase A caveat. The
  `mcp__youtube-transcript__get_transcript` tool returned `[object Object]` to
  the agent harness for all calls; Subagent C worked around by direct
  `youtube-transcript@1.3.1` npm-library invocation. New `decisions.md` entry
  appended to capture this for future sessions.
- Channel-attribution discovery: four of five "priority @bassniper videos"
  listed in the session-3 brief were actually from other channels (The Bass
  Fishing Life × 3, TacticalBassin × 1, Derek Kira × 1). Only the pre-seeded
  2020-03 transcript is genuinely @bassniper. Findings still stand under the
  methodology-elevation rule. Carried forward as an open question in
  `working-notes.md`.
- Open follow-ups: BassResource Cherokee daily reports (Loftus 2nd-place specs);
  Center Hill drop-shot specifics; Strader / Walker / Morgan TVA-current
  drop-shot specifics; full @bassniper channel scan for additional drop-shot
  content beyond the 2020-03 video.
- Phase B (skill packaging) is unblocked. The protocol exercised cleanly end-to-end
  with one operational caveat (MCP serialization, worked around). Skill body can
  reflect what actually worked.

## 2026-09-09 — Center Hill September tournament research (cross-repo run; deliverable in bass-fishing-vault)

- Purpose: scouting brief for Brad's Center Hill tournament Sat 2026-09-12 (Hurricane Bridge). Deliverable, runbook, and
  research postmortem live in `bass-fishing-vault/field-notes/`. This repo holds the cached sources per `research-protocol.md` § 3.
- Four Sonnet subagents (recent intel / historical September corpus / conditions baseline / pro September content) plus
  main-session live-data pulls (USACE CWMS, LRN preschedule, NWS, USNO) and two main-session salvage passes.
- Cached this run — articles: `omnia-center-hill-september-user-reports-2020-2024.md`,
  `3bmedianews-center-hill-dale-hollow-sept-2020-series.md`, `omniafishing-center-hill-lake-reports-multi-year-sept.md`,
  `twra-creel-clerk-center-hill-weekly-report-2024-10-30.md`, `twra-center-hill-reservoir-page-2026.md`,
  `usace-cwms-center-hill-elevation-september-history.md`, `center-hill-water-temperature-aggregators-2026-09.md`,
  `dvids-usace-nashville-drought-low-lakes-2026-04.md`, `dvids-center-hill-spillway-gate-replacement-2026-05.md`,
  `dvids-center-hill-orifice-gate-reinstallation-2024-06.md`, `twra-weekly-report-caney-fork-tailwater-2026-07-16.md`,
  `twra-weekly-report-center-hill-tailwater-2026-07.md`, `wired2fish-september-2026-lures-roundup.md`,
  `youtube-rss-roster-scan-2026-09-09.md`.
- Cached — transcripts: `ottdefoe-technique-of-month-september-scoping-suspenders-2026-09.md`,
  `wheelerfishing-best-september-bait-2026-09.md`, `wheelerfishing-late-summer-raw-breakdown-2026-08.md`,
  `tacticalbassin-free-rig-fall-bass-2026-09.md`, `bassfishinghq-late-summer-technique-2026-09.md`.
- Cached — tournament-reports: `mlf-bfl-dalehollow-2024-09.md` (Pearman, jighead minnow + FFS, largemouth),
  `mlf-bfl-music-city-dale-hollow-2024-09-preview.md`, `twra-creel-clerk-center-hill-reservoir-reports-2024.md`,
  `bfl-music-city-center-hill-2026-schedule.md`, `volunteer-bass-trail-2026-schedule.md`.
- Findings relevant to rig dossiers: DeFoe's September jighead-minnow spec (VMC Redline tungsten / Minnow Shaker 2/0,
  1/8–3/8 oz, 3–5" Rock and Shad, reel-set) is a Damiki/minnow-rig data point for the deferred Hover/Damiki decision;
  TacticalBassin's free-rig rock checklist plus the unpulled Steve Rogers "worm weight vs free rig weight in rock" test
  (IJlNZOCrLwc) feed the Free Rig dossier. Center Hill drop-shot specifics (loose-ends S3.9) still `[THIN]`: one 2020
  mention only.
- Tooling: YouTube channel RSS + Node `youtube-transcript@1.3.1` work from the cloud container (rate wall after ~6 pulls);
  Playwright dead there; MLF via Wayback `id_` snapshots or thebasscast.com mirror; Omnia report data is in static HTML.
  Details in `NickajackLake/Docs/Tooling/cloud-container-fetch-paths-2026-09-09.md`.
