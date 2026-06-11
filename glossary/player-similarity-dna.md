# Player similarity (DNA)

**Player similarity (often called "Player DNA" in Rising Transfers) identifies footballers who play in a similar style** — not just players who share a position or goal tally, but those whose overall per-90 profile and tactical role resemble each other in multi-dimensional space.

## Why similarity matters

Traditional stats answer *what happened*. Similarity answers *who else plays like this*:

- A sporting director needs **alternatives** when a transfer target is unavailable.
- A scout wants **younger or cheaper stylistic matches**, not just the same position on paper.
- A fantasy manager needs a **like-for-like replacement** during injury or rotation.

Most public datasets list goals, assists, and market values. Very few publish **open stylistic similarity scores** — that gap is why dedicated similarity datasets matter for scouting and analytics workflows.

## How Player DNA similarity works

Rising Transfers builds a **semantic embedding** for each player from per-90 performance signals across attacking, passing, defending, and (for goalkeepers) shot-stopping metrics. Each embedding is a high-dimensional vector (768 dimensions in the current model).

**Similarity score** between two players is computed as **cosine similarity** between their vectors:

```
similarity = cos(θ) = (A · B) / (||A|| × ||B||)
```

Scores range from **0 to 1**:

| Score | Typical interpretation |
|---|---|
| 0.85+ | Very similar stylistic profile |
| 0.75–0.85 | Strong overlap |
| 0.65–0.75 | Partial overlap |
| < 0.65 | Different profiles |

Example: searching "players like Rodri" should surface defensive midfielders with comparable ball-winning and distribution patterns — not merely any midfielder with similar minutes.

## What gets published vs. protected

Open datasets should publish **model outputs only**:

- ✅ Top-N similar players per target
- ✅ Similarity scores
- ✅ Style tags (human-readable labels)

They should **not** publish:

- ❌ Raw embedding vectors (enables reverse-engineering of the full similarity matrix)
- ❌ Complete pairwise matrices for entire leagues

The [football-player-similarity](https://github.com/risingtransfers/football-player-similarity) repository follows this pattern: **450 players, top-10 matches each, no raw vectors**.

## Common misconceptions

1. **"Similarity equals quality."** Two players can be highly similar while one is world-class and the other is a lower-league prospect. Similarity is about *style*, not *level*.

2. **"Same position = similar player."** Position labels are coarse. Two "central midfielders" can have opposite roles (destroyer vs. playmaker).

3. **"High similarity means identical stats."** Embeddings capture multivariate patterns. Two players may differ in one stat but align across ten others.

4. **"More neighbors = better dataset."** Publishing every pairwise score increases re-identification risk without adding proportional scouting value. Top-10 per player is the practical sweet spot.

## How Rising Transfers uses DNA similarity

Interactive "who plays like X" profiles live at:

```
https://risingtransfers.com/en/players/{slug}/alternatives
```

The open dataset mirrors this capability for 450 curated players. Full coverage across 56,000+ profiles remains on [risingtransfers.com](https://risingtransfers.com).
