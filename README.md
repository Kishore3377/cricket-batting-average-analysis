# 🏏 The Batting Average Trap — IPL 2024 Cricket Analytics

## 📌 Project Overview

Can batting average alone determine whether a cricket player should bat higher?

This project investigates the statement:

> "Player A has a better batting average than Player B, so Player A should bat higher."

The objective is to determine whether batting average alone provides enough information to make a batting-order decision.

Instead of relying on a single KPI, the analysis compares multiple dimensions of batting performance using real IPL 2024 ball-by-ball data.

---

## 🎯 Business / Cricket Question

A cricket analyst recommends promoting a player because the player has a higher batting average.

The question is:

**Does a higher batting average necessarily mean the player provides greater value when batting higher in the order?**

To investigate this, the project compares:

* Batting Average
* Strike Rate
* Total Runs
* Mean Runs per Match
* Median Runs per Match
* Standard Deviation
* Fours
* Sixes
* Boundary Runs
* Boundary Contribution

---

## 📊 Dataset

**Source:** Cricsheet

Cricsheet provides open cricket ball-by-ball data in JSON format.

The IPL dataset contains individual JSON files where each file represents a match.

The JSON structure used in this project follows:

```text
Match
│
├── info
│
└── innings
    │
    ├── team
    │
    └── overs
        │
        └── deliveries
            ├── batter
            ├── bowler
            ├── runs
            └── wickets
```

The analysis focuses specifically on **IPL 2024**.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* JSON
* pathlib
* Jupyter Notebook

---

## 🔄 Project Workflow

```text
Raw IPL JSON Files
        ↓
Inspect JSON Structure
        ↓
Extract Delivery-Level Data
        ↓
Create Pandas DataFrame
        ↓
Filter IPL 2024
        ↓
Aggregate Player Statistics
        ↓
Calculate Batting Average
        ↓
Calculate Strike Rate
        ↓
Calculate Match-Level Statistics
        ↓
Analyze Mean / Median / Standard Deviation
        ↓
Analyze Boundary Contribution
        ↓
Visualize Player Performance
        ↓
Business / Cricket Recommendation
```

---

## 🧹 Data Processing

The raw Cricsheet data is nested JSON rather than a traditional CSV table.

The project extracts relevant information from:

* Match
* Innings
* Overs
* Deliveries

For each delivery, the analysis captures information such as:

* Match ID
* Season
* Innings
* Batting Team
* Batter
* Batter Runs
* Balls Faced
* Dismissed Player
* Dismissal Type

This converts the nested JSON structure into an analysis-ready Pandas DataFrame.

---

## 📐 Key Metrics

### Batting Average

Batting average is calculated as:

```text
Runs Scored / Times Dismissed
```

### Strike Rate

```text
Runs Scored / Balls Faced × 100
```

### Mean

Measures the average runs scored per match appearance in the constructed match-level dataset.

### Median

Used to understand the typical match-level scoring performance and reduce the influence of extreme innings.

### Standard Deviation

Used as a measure of match-to-match variation.

A higher value indicates greater variability in scores, while a lower value indicates more stable scoring.

### Boundary Contribution

Boundary runs are calculated using:

```text
(Fours × 4) + (Sixes × 6)
```

Boundary contribution is then compared with total runs.

---

## 📈 Visualizations

### 1. Batting Average vs Strike Rate

This visualization examines whether players with higher batting averages also provide higher scoring rates.

Bubble size represents total runs scored.

### 2. Consistency vs Typical Performance

This visualization compares:

* Median runs per match
* Standard deviation of runs

The objective is to understand both typical performance and variability.

---

## 🔍 Key Analytical Insight

The analysis demonstrates why a single KPI should not automatically be converted into a decision rule.

Batting average provides useful information about a player's run production relative to dismissals, but it does not capture every dimension of T20 batting value.

Strike rate, scoring distribution, consistency and boundary contribution can provide additional context.

Therefore:

> **Batting average should be treated as one input into a batting-order decision rather than the sole decision criterion.**

The appropriate choice ultimately depends on the team's role requirements and match strategy.

---

## 💡 Data Analyst Takeaway

This project was not only about calculating cricket statistics.

The main objective was to practice a data analyst workflow:

**Question → Data → Cleaning → Transformation → KPI Calculation → Statistical Analysis → Visualization → Decision**

The key lesson:

> **Don't just report the metric. Understand what decision the metric is being used to support.**

---

## 📁 Project Structure

```text
Day_2_Cricket_Analytics/
│
├── data/
│   └── ipl_json/
│
├── notebooks/
│   └── Day_2_Batting_Average.ipynb
│
├── output/
│   ├── batting_average_vs_strike_rate.png
│   └── consistency_comparison.png
│
└── README.md
```

---

## 🚀 Future Improvements

Possible extensions to this project include:

* Compare specific player pairs
* Analyze batting position
* Analyze powerplay vs middle-over vs death-over performance
* Compare performance against different bowling types
* Analyze opposition strength
* Add match situation/context
* Develop a role-based batting score
* Build an interactive Power BI dashboard

---

## 📚 Data Source

Cricsheet — open cricket data

https://cricsheet.org/

## 👤 Project

**Day 2 — Daily Data Analyst Challenge**

Focus: Cricket Analytics + Data Analysis + Statistical Reasoning

