# Day 2 Notes – COVID EDA & Pandas

## 1. EDA Notebook Structure

A professional EDA notebook should follow:

```text
Project Introduction

Dataset Information

Basic EDA

Country & Date Analysis

Case Analysis

Death Analysis

Vaccination Analysis

Testing Analysis

Key Insights
```

Each section should contain:

```text
Objective
Code
Observations
```

---

# 2. Important Pandas Functions Learned

## Data Inspection

```python
df.head()
df.tail()
df.info()
df.describe()
df.shape
df.columns
```

Purpose:

* Understand dataset structure.
* Check data types.
* View sample records.

---

## GroupBy

Used to perform analysis on groups.

```python
df.groupby("country")["total_cases"].max()
```

Meaning:

For every country, find maximum total cases.

---

## Aggregation (agg)

Used to perform multiple aggregations.

```python
df.groupby("country").agg(
    Total_Cases=("total_cases","max"),
    Max_New_Cases=("new_cases","max")
)
```

Output:

| country | Total_Cases | Max_New_Cases |

---

## reset_index()

Converts grouped index back into a normal column.

```python
grouped_df.reset_index()
```

Remember:

```python
.reset_index()
```

NOT

```python
.reset_index
```

---

## Sorting

```python
df.sort_values(
    by="Total_Cases",
    ascending=False
)
```

Used for ranking countries.

---

## Filtering

Single country:

```python
df[df["country"]=="India"]
```

Multiple countries:

```python
df[df["country"].isin(
    ["India","China"]
)]
```

---

# 3. String Operations

## str.contains()

Checks whether text contains a pattern.

Example:

```python
df["country"].str.contains("India")
```

Returns:

```text
True
False
False
```

---

Multiple words:

```python
df["country"].str.contains(
    "India|China"
)
```

Meaning:

Contains India OR China.

---

NOT condition:

```python
~df["country"].str.contains(
    "World|Asia"
)
```

Used to exclude rows.

---

Difference:

```python
isin()
```

→ Exact match

```python
str.contains()
```

→ Pattern search

---

# 4. idxmax()

Definition:

Returns the index where maximum value occurs.

Example:

```python
df["new_cases"].idxmax()
```

Returns:

```text
1254
```

Meaning:

Maximum new_cases is present at row 1254.

---

To get complete row:

```python
df.loc[
    df["new_cases"].idxmax()
]
```

---

Grouped version:

```python
df.loc[
    df.groupby("country")
      ["new_cases"]
      .idxmax()
]
```

Returns:

Row corresponding to maximum new_cases for every country.

---

# 5. COVID Dataset Concepts

## Total Cases

Cumulative confirmed cases.

```text
Never decreases
Usually increases with time
```

---

## New Cases

Cases reported on a specific day.

```text
Today's Cases - Yesterday's Cases
```

---

## New Cases Smoothed

7-day moving average of new cases.

Purpose:

* Reduce daily fluctuations.
* Remove weekend reporting effects.
* Show actual trend.

---

# 6. Case Analysis Performed

Created:

```python
Cases_per_country
```

Containing:

```text
Country
Total Cases
Maximum New Cases
Peak Date
```

---

Key Findings:

* China recorded the highest single-day spike among individual countries.
* India recorded approximately 414k daily cases during its second wave.
* Dataset contains aggregated entities such as:

  * World
  * Asia
  * Europe
  * High-income countries

These should be excluded when comparing individual countries.

---

# 7. Important Lesson

Do NOT try to memorize every Pandas function.

Focus on understanding:

```text
What problem am I trying to solve?
```

Then learn the function that solves it.

Core functions to master first:

* groupby()
* agg()
* sort_values()
* isin()
* str.contains()
* isnull()
* merge()
* reset_index()

These cover most EDA tasks.

---

# Next Session

Start:

## Death Analysis

Questions:

1. Which country has highest total deaths?
2. Which country recorded highest deaths in a day?
3. On what date did it occur?
4. India vs China comparison.
5. Missing value analysis for death-related columns.

```
```
