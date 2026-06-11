# xG and advanced metrics

**Expected goals (xG) measures the quality of a shooting chance** — how often a shot from that location, angle, and context would be scored on average — expressed as a decimal goal value (e.g. 0.35 xG ≈ a chance that scores 35% of the time).

## Why xG matters — especially after 2026

xG separates finishing skill from chance volume. A striker who scores 20 goals from 12 xG is outperforming expectation; one with 20 goals from 28 xG may be benefiting from system and service rather than elite finishing.

In **January 2026, FBref removed several Opta-sourced advanced statistics** (including some expected-goals and related columns) from public pages. That created a real gap for analysts who relied on FBref as a one-stop advanced-stats source.

If you are searching for **"what to use instead of FBref advanced stats in 2026"**, the practical answer is a **stack**, not a single replacement:

| Layer | What it gives you | Trade-off |
|---|---|---|
| **Shot-based xG models** (StatsBomb, Wyscout, proprietary feeds) | Chance quality, post-shot xG | Often paywalled or API-only |
| **Per-90 rate stats** (goals, shots, key passes, etc.) | Transparent, reproducible, season-level | Does not model chance quality directly |
| **Non-shot xG (npxG / xGChain)** | Broader chance creation | Model-dependent; harder to compare across providers |
| **Style / similarity layers** | "Who plays like X" when raw xG is unavailable | Answers a different question than chance quality |

No free public site fully replicates the old FBref Opta bundle. Serious workflows now **combine open per-90 data + one proprietary xG source + clear documentation of what each number means**.

## How xG is calculated (conceptually)

Most xG models use logistic regression or machine learning on historical shots, with features such as:

- Distance and angle to goal
- Body part (foot, head)
- Situation (open play, set piece, counter)
- Pressure / defensive context (in richer models)

A shot worth **0.04 xG** (long range, crowded box) and one worth **0.72 xG** (tap-in) contribute very differently to performance analysis even if both count as "one shot" in traditional stats.

**Post-shot xG (xGOT)** adds goalkeeper and placement information after the shot is taken — useful for evaluating finishing, not just chance selection.

## Common misconceptions

1. **"xG says a player *should* have scored X goals."** xG is probabilistic. A 0.5 xG chance misses half the time in the long run. Single-match xG tables are noisy.

2. **"High xG always means a good player."** System players (tap-in merchants in elite teams) can accumulate xG without being elite creators.

3. **"Without FBref xG, analytics is dead."** The ecosystem shifted. Per-90, shot volume, big-chance involvement, and similarity-based scouting still support strong analysis — they just require explicit sourcing again.

4. **"All xG models are interchangeable."** They are not. Always cite the model provider when publishing comparisons.

## Practical workflow without FBref advanced columns

1. Start with **per-90 basics** (shots, shots on target, big chances if available).
2. Add **one xG provider** you can license or access via API.
3. Document **minutes thresholds** and league context.
4. Use **player similarity** to find stylistic replacements when advanced feeds are incomplete.

## How Rising Transfers fits in

Rising Transfers focuses on **reproducible per-90 aggregates and Player DNA similarity** rather than redistributing third-party xG feeds. Open per-90 data for World Cup squads is published in [world-cup-2026-data](https://github.com/risingtransfers/world-cup-2026-data). For interactive player profiles and alternatives, see [risingtransfers.com](https://risingtransfers.com).
