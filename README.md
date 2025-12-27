# 🏏 ICC Men's Cricket World Cup 2023 – Advanced Data Analysis

## 📌 Section Overview

This section of the project focuses on **advanced data integration, feature engineering, and in-depth analytical insights** derived from the ICC Men’s Cricket World Cup 2023 dataset. After initial data loading and cleaning, this phase enriches datasets, applies domain-driven assumptions, and uncovers **team strategies, player performance under pressure, venue impact, and match outcome patterns**.

This README explains **what was done, why it was done, and what insights were generated**, following GitHub best practices.

---

## 🔗 Data Integration & Enrichment

### Batting Data + Player Information

* Batting statistics were merged with player metadata using player names
* Added contextual attributes:

  * Player country
  * Playing role (Batsman, All-rounder, Bowler, Wicketkeeper)
* A **left join** strategy was used to ensure no batting records were lost

**Why this matters:**
Raw performance data becomes more meaningful when enriched with player roles and teams, enabling **role-based and team-wise comparisons**.

---

### Bowling Data + Player Information

* Bowling statistics were similarly enriched with player country and role
* Enables:

  * Team bowling strength analysis
  * Role-based bowling effectiveness

---

### Data Validation

* Post-merge null checks were performed to ensure all players were mapped correctly
* Any mismatches were flagged for inspection

**Best Practice:**
This validation step ensures **data integrity before analytical computations**.

---

## 🔢 Data Type Conversion & Standardization

### Numeric Column Conversion

* Batting and bowling metrics such as runs, balls, wickets, strike rate, economy, etc., were converted to numeric types
* Invalid values were safely handled using coercion

**Why:**
Ensures accurate aggregations, calculations, and visualizations without runtime errors.

---

### Column Name Normalization

* Renamed columns like `4s` → `fours`, `6s` → `sixes`
* Standardized column naming across datasets

**Why:**
Improves readability, avoids syntax issues, and maintains consistency during analysis.

---

## 📅 Match Context & Feature Engineering

### Date Formatting

* Match dates were converted to proper datetime format
* Enables future time-based or trend analysis

---

### Innings Assignment Logic

**Assumption Used:**

* Team 1 bats first → Innings 1
* Team 2 bats second → Innings 2

**Why:**
Innings context is critical for:

* Chasing vs defending analysis
* Pressure performance evaluation

*Note: Assumptions are explicitly documented for transparency.*

---

## 📊 Team Performance Analysis

### Win Percentage Calculation

* Calculated matches played and matches won per team
* Win percentage used instead of raw wins for fair comparison

**Insight Generated:**
Identifies the most consistent teams throughout the tournament.

---

### Batting Depth Analysis

Batting orders were grouped into:

* Top Order (1–3)
* Middle Order (4–7)
* Lower Order (8+)

**Metric Used:** Runs per wicket

**Why:**
Provides a deeper understanding of batting stability and dependency on specific orders.

---

### 300+ Score Analysis

* Evaluated frequency and distribution of 300+ team scores
* Identified teams with high scoring dominance

---

### Centuries & Half-Centuries

* Counted 100s and 50s per team
* Visualized using stacked bar charts

**Insight:**
Highlights teams with consistent big-match batting contributions.

---

## 🎯 Bowling Performance Analysis

### Total Wickets by Team

* Aggregated wickets taken by each team
* Measures bowling penetration

---

### Bowling Out Opponents (10 Wickets)

* Counted instances where teams bowled out the opposition

**Advanced Insight:**
Shows teams that finish matches decisively rather than relying only on run containment.

---

### Bowling Metrics Evaluation

Metrics analyzed:

* Economy Rate
* Bowling Average
* Strike Rate

**Filtering Applied:**

* Minimum wicket threshold to ensure fairness

---

## 🔥 Pressure Situation Analysis

### Successful Chases (300+ Targets)

* Evaluated teams’ success rate while chasing high targets

**Insight:**
Reveals mental toughness and chasing capability under pressure.

---

### Defending Low Totals (<250)

* Analyzed teams’ ability to defend low scores

**Insight:**
Highlights disciplined and effective bowling attacks.

---

### Toss Impact Analysis

* Compared match outcomes based on batting first vs chasing

**Purpose:**
Quantifies any overall toss bias in match results.

---

### Target Range Analysis

Targets grouped into:

* Under 200
* 200–249
* 250–299
* 300+

**Why:**
Shows how chase success probability changes with target size.

---

## 🧠 Player Performance Under Pressure

### 50+ Scores in Winning Chases

* Identified players scoring 50+ runs in successful chases only

**Why this matters:**
Filters out low-impact stats and highlights true **match-winning performances**.

---

## 🏟 Venue Impact Analysis

### Batting First vs Chasing by Venue

* Compared success rates by venue

**Insight:**
Reveals pitch behavior and helps with toss strategy decisions.

---

### Average First Innings Scores

* Calculated average first innings score per venue

**Outcome:**
Identifies high-scoring vs bowling-friendly venues.

---

## ⭐ Top Player Analysis

### Top Batsmen Evaluation

Metrics included:

* Total runs
* Batting average
* Strike rate
* 50s and 100s
* Boundary count

Rankings generated using **minimum qualification criteria** to ensure fairness.

---

### Top Bowlers Evaluation

Metrics included:

* Wickets taken
* Economy rate
* Bowling average
* Strike rate
* Best bowling figures

Provides a balanced and professional evaluation similar to real-world cricket analytics.

---

## 🏁 Key Takeaways

* Strong data enrichment and feature engineering improved insight quality
* Identified dominant teams, clutch players, and venue patterns
* Demonstrated advanced EDA, grouping logic, and cricket-domain understanding

---

## 🛠 Tools & Technologies

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Google Colab

---



---

⭐ *If you find this project insightful, feel free to star the repository!*
