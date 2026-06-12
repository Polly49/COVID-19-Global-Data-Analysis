# Day 4 — COVID-19 Vaccination EDA & Analytical Thinking

Today was less about writing code and more about learning how to think like a data analyst.

## What I Worked On

### 1. Vaccination Data Analysis
- Analyzed vaccination-related features such as:
  - `total_vaccinations`
  - `people_vaccinated`
  - `people_fully_vaccinated`
  - `total_boosters`
  - Vaccination metrics per hundred population
- Checked missing values and found that vaccination-related columns contain a large amount of missing data because many countries did not report vaccination statistics consistently.

---

### 2. Country-Level Vaccination Summary
Created a country-wise aggregated dataset containing:
- Total vaccinations
- Fully vaccinated population (%)
- Total boosters
- Booster coverage (%)

This helped identify:
- Countries with the highest vaccination coverage.
- Countries with the highest booster administration.
- Global leaders in vaccine rollout.

---

### 3. Peak Vaccination Analysis
Identified:
- Countries with the highest number of vaccinations administered in a single day.
- Dates on which countries achieved their peak vaccination rates.

### Key Findings
- China recorded the highest number of vaccine doses administered globally.
- India ranked among the top countries in total vaccinations.
- China's peak daily vaccination count was significantly higher than most countries.
- India reached its peak vaccination rate later than China.

---

### 4. Vaccination Rollout Timeline
Analyzed when countries started their vaccination campaigns.

### Key Findings
- Vaccination campaigns began in late 2020.
- Countries such as the United States, Canada, Israel, and several European nations started early.
- India reported its first vaccination doses on **16 January 2021**.

---

### 5. India Case Study
Explored the relationship between:
- Vaccination coverage
- COVID-19 death rates

Learned how to create **dual-axis plots** using Matplotlib:

```python
ax1 = plt.subplots(...)
ax2 = ax1.twinx()
```

This allowed me to visualize two variables with completely different scales on the same timeline.

### Observation
- Vaccination coverage increased rapidly during 2021–2022.
- Death rates declined after major vaccination campaigns.
- However, visual trends alone are not enough to prove causation.

---

### 6. Global Vaccination vs Death Rate Analysis

#### First Attempt
Compared:

- Maximum vaccination coverage
- Total deaths per million

using a scatter plot.

### Result
The relationship was weak and did not show the expected negative trend.

---

#### Second Attempt
Refined the analysis by comparing:

- Maximum vaccination coverage
- Average `new_deaths_smoothed_per_million` after January 2021

This metric was more meaningful because it focused on the vaccination era rather than the entire pandemic history.

### Result
The correlation remained weak:

```text
Correlation ≈ 0.18
```

---

## Biggest Learning of the Day

Initially, I assumed:

```text
More Vaccination → Fewer Deaths
```

However, after multiple experiments, I learned an important lesson:

> Good analysis is not about proving a belief. It is about testing a hypothesis and accepting what the data shows.

The weak correlation suggested that vaccination coverage alone cannot fully explain differences in COVID-19 death rates across countries. Other factors such as healthcare systems, demographics, government policies, reporting quality, virus variants, and population characteristics also influence mortality outcomes.

---

## Technical Concepts Learned

- Missing value analysis
- GroupBy aggregations
- Country-level feature engineering
- Time-series analysis
- Dual-axis visualization (`twinx`)
- Scatter plot interpretation
- Correlation analysis
- Hypothesis testing through EDA
- Distinguishing correlation from causation

---

## Personal Reflection

Today was one of the first days where I spent more time thinking than coding.

I learned that creating plots is easy; interpreting them is difficult.

The most valuable lesson was understanding that when a visualization does not support my hypothesis, the goal is not to manipulate the analysis until it does. Instead, the goal is to question the metric, refine the approach, and honestly report the findings.

That shift—from writing code to asking better questions—felt like a real step toward becoming a data analyst.
