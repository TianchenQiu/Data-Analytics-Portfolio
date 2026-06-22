# Executive Summary

## Project Objective

This project analyzes an A/B test from the mobile game Cookie Cats. The business goal is to determine whether the first progression gate should remain at level 30 or be moved to level 40.

In the game, a gate is a point where players must pause before continuing. The experiment compares two versions:

- `gate_30`: players encounter the first gate at level 30
- `gate_40`: players encounter the first gate at level 40

The main question is whether moving the gate later improves player retention or engagement.

## Dataset Overview

The dataset contains user-level experiment data. Each row represents one player and includes the following fields:

- `userid`: unique player identifier
- `version`: assigned experiment group, either `gate_30` or `gate_40`
- `sum_gamerounds`: total number of game rounds played during the observed period
- `retention_1`: whether the player returned 1 day after install
- `retention_7`: whether the player returned 7 days after install

The primary metrics for this analysis were day-1 retention and day-7 retention. Total game rounds were used as a supporting engagement metric.

## Data Cleaning and Validation

The dataset was first checked for quality and consistency before analysis. The validation process included checking dataset shape, column names, data types, missing values, duplicate user IDs, experiment group values, retention values, and impossible values in total game rounds.

No major data quality issues were found. The dataset had no missing values and no duplicate user IDs. The experiment group column contained only the expected values: `gate_30` and `gate_40`. The retention columns were converted from boolean values to integers, where `1` represents retained and `0` represents not retained. This made retention rates easier to calculate and supported later statistical testing.

The two experiment groups were also reasonably balanced, which supports a fair comparison between the gate versions.

## Exploratory Data Analysis

Exploratory analysis began with a group-level summary comparing total users, retained users, retention rates, and average game rounds by gate version.

Retention was evaluated visually using bar charts for retained user counts and retention rates. These charts showed that day-1 retention was very similar between `gate_30` and `gate_40`, while day-7 retention appeared higher for `gate_30`.

Total game rounds were analyzed as an engagement metric. The distribution was highly right-skewed, meaning most players played a relatively small number of rounds while a small number of players played many rounds. One extreme outlier was found in the `gate_30` group, with 49,854 total game rounds. This value was much higher than the next largest observations, which were around 2,000 to 3,000 rounds.

Because of this outlier, average game rounds were compared both with and without the extreme value. After removing the single extreme outlier for sensitivity analysis, the average game rounds between the two groups became much closer. This suggested that the original average difference was largely influenced by one unusually active player rather than a broad engagement difference between groups.

The outlier was not removed from the main dataset during cleaning because it may represent a real user. Instead, it was handled through sensitivity analysis to understand its impact.

## Statistical Testing

Two-proportion z-tests were used to compare retention rates because retention is a binary outcome. Separate tests were conducted for day-1 retention and day-7 retention.

For day-1 retention, the test failed to reject the null hypothesis. This means there was not enough evidence to conclude that day-1 retention differed significantly between `gate_30` and `gate_40`.

For day-7 retention, the test rejected the null hypothesis. The result showed a statistically significant difference between the two groups. Based on the group summary, `gate_30` had the higher day-7 retention rate.

Total game rounds were tested using the Mann-Whitney U test because the metric was highly skewed and contained an extreme outlier. This test was used to compare whether one group generally had higher game-round values than the other without assuming a normal distribution.

The Mann-Whitney U test found no statistically significant difference in total game rounds between `gate_30` and `gate_40`. The same conclusion held after excluding the single extreme outlier as a sensitivity check.

## Key Findings

- The dataset was clean and suitable for A/B testing.
- The experiment groups were reasonably balanced.
- Day-1 retention did not differ significantly between `gate_30` and `gate_40`.
- Day-7 retention differed significantly between the two groups.
- `gate_30` had the higher day-7 retention rate.
- Total game rounds were highly right-skewed.
- One extreme game-round outlier strongly affected the average for `gate_30`.
- After excluding the extreme outlier for sensitivity analysis, average game rounds became much closer between groups.
- Game rounds did not differ significantly between the two groups based on the Mann-Whitney U test.

## Recommendation

Based on the results, moving the first gate from level 30 to level 40 does not appear to improve player retention or engagement. The `gate_40` version did not produce a statistically significant improvement in day-1 retention, day-7 retention, or total game rounds.

The strongest finding is that `gate_30` had significantly higher day-7 retention. Since longer-term retention is an important metric for mobile game performance, the recommendation is to keep the first gate at level 30.

This recommendation is further supported by the engagement analysis, which found no evidence that `gate_40` increased total game rounds.
