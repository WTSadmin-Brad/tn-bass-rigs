# source-hierarchy.md

This file ranks sources by evidentiary weight and tells you when one source is enough versus when consensus across multiple is required. It pairs with `pro-roster.md` — that file covers *who* to listen to, this one covers *what format* their input has to be in for it to count as evidence.

The goal is volume plus consensus: lots of sources to support the kind of callout-rich, expert-tip-dense infographics Brad wants, but cross-referenced enough to filter out marketing fluff and copy-paste consensus that no one actually tested.

## The tier system

### Tier A — Primary evidence

These sources can stand alone for a claim if no contradicting evidence exists, though corroboration always strengthens the dossier.

**Tournament results and post-tournament breakdowns.** What actually won. Includes BASS Elite Series and Opens, MLF Bass Pro Tour and Toyota Series, National Professional Fishing League (NPFL), Bassmaster B.A.S.S. Nation, and regional TN circuits — BFL Wild Card events at TN venues, Joe Wheeler / TN-AL border tournaments, college series at TN reservoirs, TWRA-sanctioned events. The angler's own post-tournament breakdown of what they threw and why is the gold standard. Tournament organization recap articles count when they include specific gear details.

**Empirical content with controlled methodology.** @bassniper is the canonical example — see the dedicated section below. Any source that uses underwater video, side-by-side comparisons, repeated trials, or systematic data collection rather than demonstration. The threshold is "designed to find out if X is true" rather than "designed to show how to do X."

**Manufacturer technical specifications.** For component data only — line diameters, hook gauges and wire sizes, weight materials, knot strength tests published by line manufacturers. Use for objective specs, never for performance claims. A Sunline test of fluorocarbon abrasion resistance is Tier A for the resistance number; a Sunline blog post saying their line is best is Tier D.

### Tier B — Strong secondary

Credible, citable, but ideally paired with another source from Tier A or another Tier B.

**Named-pro YouTube channels with consistent technique content.** The pro is identified, has a tournament record or established reputation (see `pro-roster.md`), and the content goes beyond a sponsor showcase. Jacob Wheeler's channel breaking down a finesse technique counts; an unbranded "Top 5 Bass Rigs" compilation does not.

**Credentialed editorial publications with named authors.** Wired2Fish, In-Fisherman, Bassmaster Magazine, MLF feature articles, Major League Fishing editorial. The author has a byline, a track record, and ideally direct angler interviews quoted in the piece. Publication date matters — a 2018 Wired2Fish article on drop-shotting is informative but flag with `[STALE]` if no 2024+ corroboration exists.

**Pro interviews and podcasts on official outlets.** The Bass Cast, Fishing the Midwest, Bassmaster's official podcast, MLF Now. Direct angler statements with a date and a verifiable platform. Transcripts go in `sources/transcripts/` with the URL preserved.

### Tier C — Corroboration only

Don't anchor a claim on these alone. They strengthen claims that already have Tier A or B support, and they help identify community-level patterns worth investigating.

**Forum and community discussion.** BBC (Bass Fishing Forum), regional TN Facebook groups (e.g., Tennessee Bass Fishing, Center Hill Bass Anglers, Dale Hollow groups), r/bassfishing, Wired2Fish forum sections. Useful for: spotting consensus across many anonymous voices, finding obscure local patterns that don't show up in tournament coverage, surfacing complaints or contradictions about widely-promoted gear.

When a forum thread shows three or more independent voices saying the same thing across different threads or platforms, that's worth treating as `[community-consensus]` and tagging accordingly. Single forum posts get tagged `[THIN]` if used at all.

### Tier D — Excluded

These sources do not appear in the dossier as evidence, period. If something useful turns up in one of these formats, find the same information in a higher tier or leave it out.

**AI-generated content masquerading as editorial.** Generic structure (intro, history, components, how-to, top baits, conclusion), no specific tournament references, no named pros with direct quotes, vague brand references that drift between paragraphs, stock photos rather than real angler shots, generic or absent author bios, heavy affiliate-link density. By 2026 this is an industrial-scale problem in fishing content. Spotting it is part of the research workflow.

**SEO blog farms and affiliate listicles.** "Top 10 Drop Shot Hooks of 2026" with five paragraphs of filler before each Amazon link. Even when the underlying recommendations happen to be correct, the source's incentive structure and lack of attribution disqualify it.

**Brand-owned content without clear editorial separation.** Strike King's blog post about why their hooks are best is marketing, not evidence. Same for Yamamoto, Berkley, Z-Man, etc. Brand technical specs (Tier A above) are different — those are factual claims about their own products.

**Anonymous YouTube channels.** No named host, no tournament record, no body of work — even if a specific video looks credible, the lack of an identifiable producer means there's no track record to weigh the claim against. The host's identity is what makes Tier B work.

## @bassniper weighting

The empirical methodology is what earns @bassniper the elevated weight, not the brand of the channel. Per Brad's framing: he applies the scientific method, uses underwater video, and runs systematic experiments rather than repeating conventional wisdom. When he has tested a rig or technique under controlled conditions, that data outranks pro endorsements that may be sponsorship-influenced or based on anecdotal water time alone.

The rule: when @bassniper's findings contradict pro consensus, surface the contradiction in the dedicated dossier section. When his findings confirm pro consensus, that's high-confidence signal worth featuring — both pro experience *and* underwater video pointing the same direction is the strongest evidence this project will produce.

This same weighting logic extends to other empirically-grounded creators. The threshold isn't the channel name — it's the methodology. If TacticalBassin runs a controlled comparison of fluorocarbon brands with measured break points, that piece earns Tier A treatment. If they make a "best baits" list without testing methodology, it's Tier B.

## How to identify low-quality sources in real time

When evaluating an unfamiliar URL, watch for these tells:

- **Generic structural pattern.** If the article's outline matches every other fishing article on the same topic almost exactly, especially with H2 headings phrased as questions ("What is a Drop Shot Rig?", "How do you tie it?", "What baits work best?"), it's likely AI-generated SEO filler.
- **No tournament dates, no pro names with direct quotes.** Real expert content cites specific events, specific anglers, specific outcomes. Generic content doesn't.
- **Affiliate-link density.** Count the Amazon/Tackle Warehouse/specific retailer links in the first three paragraphs. More than two in that span and the article exists primarily to sell, not to inform.
- **Author missing or vague.** "By the [Site Name] Team" or no byline at all. Compare to credentialed editorial where the author has their own page, history, and ideally fishing credentials.
- **Stock imagery.** Generic catalog shots of products instead of on-the-water photos. Real expert content shows real fish, real boats, real water.
- **Drift between specifics.** A paragraph recommends a Gamakatsu hook, the next mentions an Owner hook in the same context without explanation. Real authors stay coherent across the article; AI content forgets what it said two paragraphs back.
- **Claims with no causal explanation.** "Use 15-pound fluorocarbon for this rig" with no reasoning is a downgrade. "Use 15-pound fluorocarbon because this rig drags through rock and abrasion resistance matters more than line diameter" is real expertise.

When in doubt, look for the same claim in a Tier A or Tier B source. If it doesn't exist outside the suspect content, treat it as untrustworthy.

## When consensus is required

Different claim types have different evidence thresholds.

**Component-level brand specificity** (e.g., "use a 4/0 Owner Jungle Flippin' for this rig") requires either Tier A evidence or consensus across at least three Tier B sources from pros with different sponsorships. Without that, drop to family-level specificity ("use a 4/0 heavy-wire flipping hook") and tag the brand suggestion separately as `[CONTESTED]` or omit it.

**Bait family or material claims** (e.g., "5-inch stickbait, salt-impregnated, in green pumpkin") only need Tier A or two corroborating Tier B sources. This level of specificity is where most consensus actually lives in bass fishing — leverage that, don't over-specify.

**Technique and condition claims** (e.g., "this rig excels in 8–15 feet over sparse vegetation in summer") need Tier A or two Tier B sources with broad agreement. These are easier to corroborate because they describe physics and biology rather than gear preferences.

**TN-specific patterns** (e.g., "smallmouth on Dale Hollow respond to this rig in late fall around 30 feet") often won't have national-tier coverage. Accept Tier B + Tier C corroboration here, or single Tier B with a `[TN-LOCAL]` tag indicating the claim is reservoir-specific and may not generalize.

**Empirical underwater observations** (e.g., "the bait falls horizontally rather than head-down on this rig") get strong weight from a single @bassniper-tier source because the methodology produces the evidence directly rather than relying on testimony.

## When thin evidence is acceptable

Sometimes there genuinely won't be five sources. A Center Hill smallmouth wintertime pattern might have one good local source and nothing else nationally. The dossier still needs to say something useful — pretending we have no information serves no one.

The rule: thin evidence is acceptable when tagged honestly. Use `[THIN]` inline with the claim and add a one-line note explaining the evidence base. The kids see the same callout, but the dossier's audit trail shows the confidence level. Future research passes can fill the gap or remove the claim.

What's not acceptable: thin evidence presented with confident framing as if it were consensus. The flag is what makes thin evidence honest.

## Connection to the dossier

The flags `[CONTESTED]`, `[THIN]`, `[STALE]`, `[community-consensus]`, `[SPONSOR-FLAG]`, and `[TN-LOCAL]` are the mechanism by which source quality shows up in the dossier itself. See `schema.md` for the full flag inventory and formatting. The tiers in this file determine which flag (if any) applies to a given citation; the schema file determines how the flag appears in the rendered dossier.

When a flag is needed, it goes inline with the claim, not in a footnote section at the bottom. The claim and its confidence level live together so the agent reading the dossier later doesn't have to cross-reference.

## What's not in this file

The list of pros and their content channels lives in `pro-roster.md`. The citation format lives in `CLAUDE.md`. The dossier flag inventory and rendering lives in `schema.md`. This file's job is the ranking and the methodological reasoning behind it.
