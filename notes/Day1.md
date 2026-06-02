# Day 1 - Dataset Understanding

## Dataset Information

* Source: Our World in Data COVID Dataset
* Rows: 589,779
* Columns: 61
* Memory Usage: ~382 MB

## Time Coverage

* Start Date: 2020-01-01
* End Date: 2026-05-10
* Total Days Covered: 2322

## Country Analysis

* Total Unique Countries/Entities analyzed.
* 181 countries have complete coverage for all 2322 days.

## Missing Value Investigation

* Investigated missing values in `total_cases`.
* Hong Kong contains the highest number of missing values in `total_cases`.

## Learnings

* One row represents one country/entity on one date.
* `groupby()` is useful for country-wise aggregation.
* Missing values should be investigated before drawing conclusions.

## Questions for Day 2

1. Which columns have the highest percentage of missing values?
2. Which countries have the highest cumulative cases?
3. Which countries have the highest deaths?
4. Which columns are reliable enough for deeper analysis?
