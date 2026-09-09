# Center Hill Lake water temperature — aggregator readings, early Sept 2026 (Tier C, estimates only)

**URL:** https://www.omniafishing.com/w/center-hill-lake-fishing-reports/current-conditions ; https://lakemonster.com/lake/TN/Center-Hill-Lake-956
**Author / channel:** Omnia Fishing (current-conditions aggregator); LakeMonster (satellite/algorithmic aggregator)
**Date (published):** pulled 2026-09-09
**Date (fishing/event):** Omnia page's own "recorded_at" / meta date = 2026-09-03. LakeMonster page states "updated Sep 9, 2026" in one place but the page's own meta/og tags say 77°F while body text says 72°F — **internal contradiction, both dated to the pull day**.
**Lake / region:** Center Hill Reservoir
**Tier:** C (both are aggregator/estimate services, not direct field measurements) — **label every number here as an estimate**
**Density:** low
**Flags:** [THIN], [CONTESTED] (LakeMonster's own page disagrees with itself)

## Extracted findings

- **Omnia Fishing:** page meta date and embedded JSON both show `water_temperature: 79`, `water_temperature_recorded_at: "2026-09-03"` for Center Hill Lake (waterbody id c98a6ebc-...). This is the most specific dated aggregator figure found: **79°F as of 2026-09-03** (6 days before the tournament-prep pull date, 2 days before this research run).
- **LakeMonster:** page title / meta / og-description all say "Current water temperature: 77°F" (undated beyond "today"); but the visible body copy says "the latest LakeMonster reading for Center Hill Lake, updated Sep 9, 2026, shows 72°F surface water temperature, mostly clear, 3 mph wind." Two different numbers (77°F vs 72°F) attributed to "current" on the same page — treat both as unreliable/estimate-grade and flag the internal contradiction. An embedded historical JSON blob on the same page lists a much older reading of 84.0°F for a different KY lake (Dale Hollow-area comparison site), not Center Hill — do not conflate.
- Net read: **aggregator estimates cluster in the low-to-high 70s°F for Center Hill in the first ten days of September 2026** (72–79°F range across the two sources/three numbers), consistent with the still-summer air temps (88–93°F highs) noted in shared context, but none of this is a verified field/buoy/dated-observer measurement.
- **No USGS temperature gauge exists for Center Hill.** USGS site 03424000 "CENTER HILL LAKE NEAR SMITHVILLE, TN" (36.0967, -85.8272) is on file (`waterservices.usgs.gov` site service), but its only cataloged data series is an inactive/historical "ad" (annual) record spanning 2006–2007 with only 2 data points and no parameter code populated — **no active or current water-temperature time series at this station.** Confirmed via `https://waterservices.usgs.gov/nwis/site/?sites=03424000&format=rdb&seriesCatalogOutput=true`.
- **No dated guide report, tournament recap, or TWRA creel-clerk report for Center Hill reservoir itself carrying a September 2026 (or any 2026) surface-temperature reading was found in this pass.** The only dated, named-source Center Hill reservoir temperature readings located were TWRA/creel-clerk weekly reports from spring 2024 (see `tnfishingreport-center-hill-creel-clerk-reports-2024.md` if cross-referenced — [STALE], different year, useful only as a seasonal-pattern analog, not a 2026 value).
- **No Center-Hill-specific fall-turnover timing or thermocline-depth statement (dated or named-source) was found.** General bass-fishing thermocline/turnover explainers (Wired2Fish, MidWest Outdoors, Bassmaster/Iaconelli) surfaced in search but contain no Center Hill-specific data and were not fetched/cached — they would only restate the generic mechanism already known and are LEAD-only per the no-padding instruction.

## Notes

Given the near-record-low pool (633.6 ft forecast for tournament day, ~14 ft under nominal full pool) and the extended, drought-driven low-water operating posture documented in the USACE April 2026 release, Brad should treat any generic "highland reservoir thermocline at X feet" claim as unverified for this specific lake/year — no dated 2026 measurement of thermocline depth exists in the fetched record.
