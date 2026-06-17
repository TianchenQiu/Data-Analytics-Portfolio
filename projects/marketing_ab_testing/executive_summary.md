# Executive Summary

## Business Questions

This project answers two marketing analytics questions:

1. Would the campaign be successful?
2. If the campaign was successful, how much of that success could be attributed to the ads?

## Recommendation

The campaign appears successful.

Users exposed to the ad converted at a statistically significantly higher rate than users exposed to the PSA control group. Based on the observed conversion lift, approximately **4,343 conversions** can be attributed to the ads among users in the ad group.

## Key Results

| Metric | Ad Group | PSA Group | Difference |
| --- | ---: | ---: | ---: |
| Users | 564,577 | 23,524 | 541,053 |
| Conversions | 14,423 | 420 | 14,003 |
| Conversion rate | 2.55% | 1.79% | 0.77 percentage points |
| Relative lift |  |  | 43.08% |
| z-statistic |  |  | 7.37 |
| p-value |  |  | < 0.001 |
| Estimated incremental conversions |  |  | 4,343 |

## A/B Test Result

To evaluate whether the campaign was successful, I ran a one-sided two-proportion z-test comparing conversion rates between the ad group and the PSA control group.

| Hypothesis | Statement |
| --- | --- |
| Null hypothesis | The ad group conversion rate is less than or equal to the PSA group conversion rate. |
| Alternative hypothesis | The ad group conversion rate is greater than the PSA group conversion rate. |

The test returned:

| Statistic | Result |
| --- | ---: |
| z-statistic | 7.37 |
| p-value | < 0.001 |

Since the p-value is below the 0.05 significance threshold, I reject the null hypothesis. The ad group converted at a statistically significantly higher rate than the PSA group.

## Incremental Impact

The ad group conversion rate was **2.55%**, compared with **1.79%** for the PSA group.

This means the campaign produced:

| Lift Metric | Result |
| --- | ---: |
| Absolute lift | 0.77 percentage points |
| Relative lift | 43.08% |
| Estimated incremental conversions | 4,343 |

Incremental conversions were estimated using:

```text
incremental conversions = (ad conversion rate - PSA conversion rate) * ad users
incremental conversions = (0.02555 - 0.01785) * 564,577
incremental conversions ≈ 4,343
```

This suggests that approximately **4,343 conversions** were incremental and attributable to the ads.

## Exploratory Timing Analysis

I also reviewed conversion patterns by weekday and hour of day.

These findings are exploratory because `most_ads_day` and `most_ads_hour` describe when each user saw the most ads, not a randomized treatment assignment. They can support follow-up testing ideas, but they should not be interpreted as causal proof that a specific weekday or hour caused higher conversion.

## Weekday Findings

A chi-square test found a statistically significant association between weekday and conversion status.

| Test | Result |
| --- | ---: |
| chi-square statistic | 410.05 |
| degrees of freedom | 6 |
| p-value | < 0.001 |

Highest observed weekday conversion rates:

| Weekday | Users | Conversions | Conversion rate |
| --- | ---: | ---: | ---: |
| Monday | 87,073 | 2,857 | 3.28% |
| Tuesday | 77,479 | 2,312 | 2.98% |
| Wednesday | 80,908 | 2,018 | 2.49% |

## Hour Findings

A chi-square test also found a statistically significant association between hour of day and conversion status.

| Test | Result |
| --- | ---: |
| chi-square statistic | 430.77 |
| degrees of freedom | 23 |
| p-value | < 0.001 |

Strongest observed hours by conversion rate:

| Hour | Users | Conversions | Conversion rate |
| --- | ---: | ---: | ---: |
| 16 | 37,567 | 1,156 | 3.08% |
| 20 | 28,923 | 862 | 2.98% |
| 15 | 44,683 | 1,325 | 2.96% |
| 21 | 29,976 | 867 | 2.89% |
| 17 | 34,988 | 987 | 2.82% |

## Conclusion

- The ad group converted at a higher rate than the PSA control group.
- Weekday and hour appear associated with conversion rate.
- Monday and Tuesday show the strongest weekday conversion rates in the overall dataset.
- Late afternoon and evening hours, especially around 15:00-21:00, rank highly by conversion rate.
- These timing patterns are useful for follow-up planning, but they should be treated as exploratory because timing was not the randomized        treatment in this A/B test.


