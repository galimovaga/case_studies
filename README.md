# Tennis Analytics Case Studies

**Galiya Galimova** · Tennis Analyst

---

Four case studies built on public ATP and WTA data. Each notebook starts with a question, follows an analysis in Python and ends with key findings. The projects cover exploratory analysis, explanatory modelling, clustering and custom performance metrics.

| # | Case study | Objective | Method | Data |
|---|---|---|---|---|
| 1 | [Jannik Sinner's Performance](Analysis%20of%20Jannik%20Sinner%27s%20Performance.ipynb) | To analyze Jannik Sinner's key performance indicators across surfaces (hard, clay, grass) and match outcome (win/loss). | Exploratory data analysis | ATP Tour data, 2018–2025 |
| 2 | [Serve Direction](Analysis%20of%20Serve%20Direction.ipynb) | To classify tennis players based on their serve direction preferences on different sides of the court (deuce vs ad) and to identify distinct serve tactics and playing styles. | K-Means clustering | Match Charting Project, 2010–2025 |
| 3 | [Shot Types for WTA Top 20 players](Analysis%20of%20Shot%20Types.ipynb) | To analyze and compare the aggressiveness, shot-making efficiency, and shot-type dominance among WTA Top 20 players using key performance metrics. | Exploratory data analysis | Match Charting Project, 1979-2025 |
| 4 | [Jack Draper's Performance Metrics](Regression%20Analysis%20of%20Jack%20Draper%27s%20performance%20metrics.ipynb) | To identify which serve and return performance metrics are statistically associated with winning a match. | Logistic regression (explanatory) | ATP Tour data, 2018–2025 |

---

## 1. Analysis of Jannik Sinner's Performance

**Objective:** To analyze Jannik Sinner's key performance indicators across surfaces (hard, clay, grass) and match outcome (win/loss).

**Data:** 21,800+ rows, 45 columns (2018–2025), filtered to Sinner's matches.

**Key findings:**
- From April 2019 to January 2020 Jannik Sinner moved up 235 positions. In November 2021 he broke into the TOP 10 of the ATP ranking.
- Won 11 ATP 250 titles, 2 ATP 500 titles, 5 Masters titles, and 4 Grand Slam titles. His win percentage on hard court is 79.5%, 74.4% on grass and 71.4% on clay.
- Serve performance is highest on grass followed by hard court and lowest on clay. On grass first serve points won is 79%, second serve points won is 59% and total serve points won is 71%. On hard court serve performance metrics are 77%, 56% and 69% respectively. On clay these metrics are 72%, 55% and 65% respectively.
- Jannik Sinner has the lowest return points won percentage (38%). On clay he has the highest return points won (43%). On hard surface this metric is 41%.
- Jannik Sinner faces the most break points on clay (7.69%) but saves the lowest percentage (61.17%). On grass he faces the fewest break points (4.97%) and saves the most (69.07%). Hard court performance is in between. He faces 6.38% of break points and saves 67.22% of break points.

## 2. Analysis of Serve Direction (ATP 2010 - 2025)

**Objective:** To classify tennis players based on their serve direction preferences on different sides of the court (deuce vs ad) and to identify distinct serve tactics and playing styles.

**Data:** 10,660 charted matches, aggregated to 690 players.

**Key findings:**
- **Cluster — asymmetric "T / wide" pattern.** T serves dominate on the deuce side (46%), wide serves on the ad side (55%).
- **Cluster — balanced, adaptive pattern.** A moderate preference for wide serves on both sides (41% and 40%), with no strong extremes.
- The notebook includes a function that returns any player's serve-direction profile, which can be used for opponent scouting.

## 3. Analysis of Shot Types for WTA Top 20 Players

**Objective:** To compare aggressiveness, shot-making efficiency and shot-type strengths among the WTA Top 20 players (ranking of 27 May 2026).

**Data:** Match Charting Project shot-type statistics, aggregated to a player-level dataset by shot category (groundstrokes, slices, drop shots, lobs, volleys, overheads and others; forehand vs backhand side).

**Key findings:**
- The most aggressive are Amanda Anisimova, Aryna Sabalenka and Madison Keys. The most controlled are Elina Svitolina, Mirra Andreeva and Coco Gauff.
- Sabalenka combines aggression with control: a 12% winner rate against an 11% unforced error rate (ratio 1.05). Anisimova makes more errors than winners (ratio 0.79).
- Coco Gauff is the only Top 20 player whose backhand winner rate (6.3%) is slightly higher than her forehand winner rate (6.2%).

## 4. Regression Analysis of Jack Draper's Performance Metrics

**Objective:** Identify which serve and return performance metrics are statistically associated with winning a match. The model is an explanatory, not predictive.

**Data:** 21,800+ rows, filtered to Jack Draper's 161 ATP Tour matches (2018–2025).

**Key findings:**
- First-serve points won, second-serve points won and return points won are all significant (p < 0.001). Aces (p = 0.088) and double faults (p = 0.221) are not significant once these percentages are in the model.
- Adding return performance raises pseudo-R² from 0.35 to 0.64. Draper's return game explains match outcomes more than his serve alone.
- A 1-percentage-point increase is associated with a higher win probability of about 2.72 pp for return points won, 1.17 pp for first-serve points won and 0.75 pp for second-serve points won.
- Against TOP 10 opponents Draper's drop-off is concentrated in point conversion, not first serve accuracy. First-serve points won falls from 79% (wins) to 65% (losses) while first serve in percentage barely changes (59% vs 57%).

---

## Tools

- **Python:** pandas, NumPy, Matplotlib, Seaborn
- **Modelling:** scikit-learn (K-Means, StandardScaler, logistic regression, silhouette score), statsmodels (logit, VIF)
- **Environment:** Jupyter Notebook

## Data sources

[Match Charting Project](https://github.com/JeffSackmann/tennis_MatchChartingProject) — shot-by-shot charted ATP and WTA matches
