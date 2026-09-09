# USACE CWMS — Center Hill Dam pool elevation, mid-September 2020–2025 vs. 2026

**URL:** https://cwms-data.usace.army.mil/cwms-data/timeseries?office=LRN&name=Center%20Hill%20Dam.Elev.Inst.~1Day.0.celrn-cwms-forecast&unit=ft
**Author / channel:** USACE Nashville District (LRN) CWMS public data API
**Date (published):** live data system, queried 2026-09-09
**Date (fishing/event):** N/A — hydrologic record 2020-09-01 through 2026-09-09
**Lake / region:** Center Hill Reservoir
**Tier:** A (primary USACE instrumentation/forecast series)
**Density:** high
**Flags:** [TN-LOCAL]

## Extracted findings

Series name: `Center Hill Dam.Elev.Inst.~1Day.0.celrn-cwms-forecast` (daily instantaneous elevation, ft, office LRN). Note the series includes both measured and forecast/computed values (`celrn-cwms-forecast` version); treat as best-available daily pool elevation, not a raw single-gauge reading.

### Sep 12 elevation by year (ft MSL)

| Year | Sep 12 elev (ft) | Sep 1 elev (ft) | Sep 1→12 change | Notes |
|---|---|---|---|---|
| 2020 | 636.7 | 637.3 | -0.6 | steady gradual drawdown |
| 2021 | 636.0 | 637.7 | -1.7 | faster drawdown |
| 2022 | 637.1 | 636.9 | +0.2 (net); spiked to 638.6 on 9/6 | rain event mid-week then resumed fall |
| 2023 | 637.4 | 640.0 | -2.6 | started well above other years, steepest drawdown |
| 2024 | 634.3 | 636.1 | -1.8 | **lowest Sep 12 in the 2020–25 set, closest analog to 2026** |
| 2025 | 636.5 | 637.7 | -1.2 | typical mid-range year |
| **2026** | **633.6** (per shared context / TVA forecast) | 635.1 (measured) | ~-1.5 (measured through 9/9) | **lowest of all seven years by ~0.7 ft vs. next-lowest (2024)** |

Six-year (2020–2025) mean Sep 12 elevation ≈ 636.3 ft. 2026's projected 633.6 ft sits roughly **2.7 ft below the six-year mid-September average** and about 0.7 ft below the next-lowest analog year, 2024 (634.3 ft on 9/12/2024). Summer full pool for Center Hill is nominally 648 ft — every one of these seven Septembers is already well into fall drawdown by the 9/12 mark, ranging 634–640 ft on Sep 1 and 633.6–637.4 ft on Sep 12. 2026 is the low outlier of the set, not merely "typical fall drawdown."

### 2026 season shape, Jun 1 – Sep 9 (measured/forecast daily elevation, ft)

Selected points from the full daily series (102 points total):
- Jun 1: 639.4 — Jun 9: 641.2 (**seasonal peak for the pulled window**) — Jun 30: 640.8
- Jul 1: 640.5 — Jul 17: 638.9 — Jul 31: 637.8
- Aug 1: 637.8 — Aug 15: 637.5 — Aug 25: 636.3 — Aug 31: 635.3
- Sep 1: 635.1 — Sep 5: 634.57 — Sep 9: 633.9 (matches shared-context live-conditions figure)

**Key finding: Center Hill 2026 never reached the nominal 648 ft summer full pool in this window.** The highest value in the Jun 1–Sep 9 pull is 641.2 ft (Jun 9–10), roughly 7 ft under typical full summer pool. The lake has declined almost monotonically since mid-June — a ~7.3 ft drop over ~13 weeks, averaging roughly 0.08 ft/day, accelerating slightly in the Sep 1–9 stretch (~0.15 ft/day, consistent with the shared-context 0.1–0.2 ft/day figure). This is consistent with the TVA notice that the Center Hill orifice gate has been open since 2026-06-01 — the pool was drawn down from an already-below-normal June peak rather than from a full 648 ft pool, and continuous orifice release (on top of normal fall drawdown) is the more likely explanation for the low Sep 9 reading and the fact that 2026 undercuts even 2024, the driest analog year in this set. See dam-safety/orifice-gate item in the report for sourcing on why the gate is open (could not find a dated USACE statement confirming a specific dam-safety cause — see Fetch-failure log / open questions).

## Notes

Raw JSON cached alongside this note is not committed to the vault (per protocol, only the digest goes to sources/articles); recompute via the API call above if needed. All values from a single API pull 2026-09-09, `celrn-cwms-forecast` version of the daily elevation series, unit=ft, timezone=US/Central.
