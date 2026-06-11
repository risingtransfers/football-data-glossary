# Per-90 statistics

**Per-90 statistics normalize a player's counting stats to a full 90-minute game**, so you can compare a winger with 1,800 league minutes against a substitute with 600 minutes on equal footing.

## Why per-90 matters

Raw season totals reward playing time, not efficiency. A striker with 15 goals in 3,400 minutes looks similar on a leaderboard to one with 12 goals in 1,900 minutes — but the second player is scoring at a much higher rate.

Per-90 fixes that by scaling every metric to "what would this player produce in one full match?" Analysts, scouts, and fantasy managers use per-90 to answer: *Who is actually productive when on the pitch?*

After FBref removed several Opta-derived advanced columns in early 2026, **per-90 rates built from transparent seasonal aggregates became even more important** as a baseline layer anyone can reproduce and cite.

## How to calculate and read per-90

The formula is straightforward:

```
stat_per90 = (total_stat / minutes_played) × 90
```

Examples:

| Player | Goals | Minutes | Goals per 90 |
|---|---:|---:|---:|
| A | 12 | 1,900 | 0.57 |
| B | 15 | 3,400 | 0.40 |

Player A scores more often per minute played, even though Player B has more total goals.

Common per-90 metrics include:

- **Attacking:** goals, assists, shots, key passes, big chances
- **Possession / creation:** passes, pass accuracy, progressive carries
- **Defending:** tackles, interceptions, clearances, aerial duels won
- **Goalkeeping:** saves, goals conceded

Always check **minutes played** alongside the rate. A player with 200 minutes and 1.0 goals/90 is not comparable to someone with 2,500 minutes — small samples inflate or deflate rates.

## Common misconceptions

1. **"Per-90 replaces context."** It does not. Role, league strength, and team style still matter. A defensive midfielder's 0.05 goals/90 can be excellent; a striker's 0.05 is not.

2. **"More per-90 is always better."** For some metrics (goals conceded, fouls, dispossessed), lower is better.

3. **"Totals are useless."** Totals still matter for availability and durability. Per-90 and totals answer different questions.

4. **"One season is enough."** Single-season per-90 is a snapshot. Multi-season trends reduce noise from injury, rotation, or tactical change.

## Minimum minutes threshold

Most serious workflows apply a **minutes floor** (often 450–900 league minutes, roughly 5–10 full games) before trusting per-90 ranks. Rising Transfers applies a 450-minute filter in its [World Cup 2026 open dataset](https://github.com/risingtransfers/world-cup-2026-data) for the same reason: reduce small-sample noise in public exports.

## How Rising Transfers uses per-90

Rising Transfers computes per-90 from seasonal aggregates across 56,000+ player profiles. These rates feed Player DNA embeddings, scouting comparisons, and the [Best XI builder](https://risingtransfers.com/en/best-xi). Interactive per-90 profiles and alternatives are available at [risingtransfers.com](https://risingtransfers.com).
