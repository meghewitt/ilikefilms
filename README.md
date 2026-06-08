# Horror Film Analysis
*How has horror cinema evolved from 1970 to 2020?*

## Research questions
1. Has horror's popularity (as a share of all notable films) changed over time — and is any trend unique to horror or a general market shift?
2. Have horror's ratings changed over time — and do critics and audiences tell different stories?
3. What factors explain the changes in horror's ratings?

## Key findings
- Horror peaked in the **1980s slasher era** (19% of notable films), collapsed in the **1990s** (8.9%), and has been recovering since — a pattern unique to horror, not seen in peer genres
- **Critics and audiences diverged sharply in the 2010s** — prestige horror (A24 era: Get Out, Hereditary, Midsommar) elevated critical scores while audience scores hit their lowest point
- **Volume does not independently cause lower ratings** — the apparent correlation is confounded by time; within individual decades, higher output years do not reliably produce lower scores
- **Content rating predicts critic scores in isolation** (PG-13 rated 25 points below NR) but becomes non-significant once director is controlled for — critics penalise PG-13 horror because of who directs it, not the rating itself
- **Director is by far the strongest predictor of critic scores** (R²=0.594 with director fixed effects vs 0.052 without) — dwarfing production tier, content rating, and genre combo combined
- **The production landscape fundamentally shifted**: major studio horror collapsed from 85% in the 1970s to 21% in the 2020s, prestige indie grew from 2% to 33% in the 2010s, and DTV/schlock exploded to 47% in the 2020s — this structural split explains both the critical recovery and the persistent audience score depression

## Methodology notes
- **Dataset:** Rotten Tomatoes Movies Dataset (Stefano Leone, Kaggle) — 17,712 films scraped October 2020
- **Year filter:** 1970+ — validated by plotting film count by year; pre-1970 coverage is too sparse for reliable decade-level analysis
- **Coverage limitation:** RT skews toward theatrical releases, English-language films, and post-2000s content. Volume trends reflect horror's presence in notable cinema, not total production output. A more complete analysis would supplement with IMDB for volume
- **Genre tagging:** RT uses multi-genre tags — a film tagged "Horror, Comedy" counts in both genre share calculations. This means share figures represent films with a horror element, not exclusively horror films
- **NR caveat:** Pre-1968 films are labelled NR by default (MPAA rating system didn't exist), creating two distinct NR populations that shouldn't be directly compared
- **Regression models:** Progressive OLS models tested content rating, production tier, decade, genre combo, and director as predictors of critic score. Director fixed effects restricted to directors with 3+ horror films (n=236 films)

## Tools
Python, Pandas, Scipy, Statsmodels, Sklearn, Matplotlib, Seaborn

## Dataset
Rotten Tomatoes Movies Dataset — Stefano Leone (Kaggle, CC0 Public Domain)