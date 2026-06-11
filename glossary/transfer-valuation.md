# Transfer valuation

**Transfer valuation is an estimate of what a football player would cost in the transfer market** — expressed in currency (typically euros) — based on performance, age, contract context, league level, and stylistic profile.

## Why AI valuation matters

Published "market values" from third-party aggregators are useful benchmarks, but they:

- Update on someone else's schedule
- Cannot be redistributed in open datasets (licensing constraints)
- Treat all players with the same opaque methodology

**Model-based valuations** let platforms generate their own estimates from signals they control — form trends, league tier, minutes, and style — while staying legally clean for public release.

Analysts use valuations to:

- Compare **value vs. performance** (bargain hunting)
- Frame **transfer alternatives** ("similar style, lower price")
- Stress-test **squad-building budgets** in tools like Best XI builders

## How models typically estimate value

There is no single industry formula. Common inputs include:

| Signal | Why it matters |
|---|---|
| **Age** | Peak years (roughly 24–28 for outfield players) command premiums |
| **League tier** | Top-five-league players trade at higher multiples |
| **Recent form (per-90 trends)** | Hot streaks move short-term price |
| **Minutes / availability** | Durable starters are worth more than fragile rotation options |
| **Position scarcity** | Elite GKs, #10s, and wide creators often carry premiums |
| **Style / role fit** | System-dependent; harder to price, but DNA helps compare peers |

A simplified mental model:

```
estimated_value ≈ base_league_tier × form_multiplier × age_curve × availability_factor
```

Real production systems add non-linear terms, peer comparisons, and confidence bands. **Always treat a single number as a point estimate, not ground truth.**

## Common misconceptions

1. **"Valuation = what the player will actually sell for."** Real fees include desperation, sell-on clauses, contract length, and seller leverage. Models estimate *fair-ish range*, not negotiated price.

2. **"Higher market value from Site X is always correct."** Different providers disagree by 30–50% on the same player. Cite your source.

3. **"AI valuation is just market value with a new label."** Good internal models can incorporate **form signals and league context** that lagging market tables miss — but they need transparent methodology for trust.

4. **"Open datasets should include market values."** Many commercial feeds forbid redistribution. Open projects often publish **model-derived estimates** under a distinct field name (e.g. `rt_value_estimate_eur`) instead.

## Open-data practice

When publishing valuations in open repositories:

- Label them clearly as **model estimates**, not official market prices
- Document inputs (form, league tier, age) at a high level
- Do **not** republish third-party market-value fields

Rising Transfers publishes AI estimates in [world-cup-2026-data](https://github.com/risingtransfers/world-cup-2026-data) under `rt_value_estimate_eur` for this reason.

## How Rising Transfers uses valuation

Rising Transfers combines DNA form signals, league tier, and age heuristics for valuation displays in scouting and squad tools. Interactive transfer-value context is available on player profiles at [risingtransfers.com](https://risingtransfers.com).
