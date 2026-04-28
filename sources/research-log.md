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
