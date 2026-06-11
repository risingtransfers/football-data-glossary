# Best XI methodology

**A data-driven Best XI is an optimal 11-player lineup selected under explicit constraints** — formation, budget, league, age, nationality, or tactical "vibe" — using performance signals rather than reputation alone.

## Why structured XI building matters

Fans and analysts build XIs every day, but informal picks bias toward fame, recent headlines, and national-team prestige. A **methodology-backed XI**:

- Enforces **formation validity** (one GK, balanced back line, legal positions)
- Applies **filters** (U23 only, World Cup squad only, budget cap)
- Ranks candidates with **repeatable scoring**, not memory

This is how you turn "my dream team" into something you can defend with data — and share as a poster, thread, or scouting brief.

## Core building blocks

Most serious XI builders combine four layers:

### 1. Candidate pool

Define who is eligible:

- **League / club scope** (e.g. Premier League only, Big-5 squads)
- **Tournament roster** (e.g. World Cup 2026 squad pool)
- **Minutes threshold** (exclude players with too few league minutes)

### 2. Position assignment

Map each player to formation slots (GK, LB, CB, DM, AM, ST, etc.). Coarse labels ("Midfielder") are not enough — good systems infer **detailed roles** from DNA tags and per-90 shape.

### 3. Scoring / ranking

Rank eligible players per slot using signals such as:

- **Season per-90 percentiles** within league + position
- **Recent form** (last N matches vs. season baseline)
- **Role-specific metrics** (tackles for DM, key passes for #10, saves for GK)

Example simplified slot score:

```
slot_score = 0.6 × season_percentile + 0.4 × form_percentile
```

Weights vary by vibe ("High Press" vs. "Italian Wall").

### 4. Constraints & balance

Apply hard rules:

- One goalkeeper
- Max players per club (optional)
- Budget cap (sum of valuations ≤ limit)
- Average age band (e.g. U23 XI)

Then check **team balance**: not 11 attackers, not 0 creative hubs.

## "Vibe" presets

Advanced builders expose **presets** — curated tactical identities such as:

- **High press** → prioritizes ball recovery, press intensity, work rate
- **Pace & transition** → wide speed, dribbles, counter profile
- **Galácticos** → star-weighted ranking within budget
- **World Cup nation** → roster membership filter + form

Each preset changes **which metrics matter**, not just the skin on the UI.

## Common misconceptions

1. **"Best XI = best 11 players in the world."** Context matters. A WC-only XI, a €200M budget XI, and a U23 XI are different optimization problems.

2. **"One rating number is enough."** Composite ratings hide role fit. A elite CB looks mediocre on attacking per-90 — slot-aware scoring fixes this.

3. **"Formation is cosmetic."** Invalid structures (three GKs, no CB) break realism. Formation is a hard constraint.

4. **"Algorithms remove debate."** They **focus** debate — from "who is best?" to "are these weights right for this vibe?"

## How Rising Transfers builds Best XI

Rising Transfers runs an interactive [Best XI builder](https://risingtransfers.com/en/best-xi) over 56,000+ players with:

- Formation-aware slot assignment
- Vibe presets (press, counter, galácticos, U23, World Cup squads, etc.)
- DNA-informed candidate ranking and stylistic tags
- Shareable lineup posters

World Cup squad membership for 2026 integrates with the open [world-cup-2026-data](https://github.com/risingtransfers/world-cup-2026-data) index. For stylistic alternatives to any selected player, use [player similarity profiles](https://risingtransfers.com/en/players/rodri/alternatives) or the [open similarity dataset](https://github.com/risingtransfers/football-player-similarity).
