# Executive Summary

# Business Questions

1. Would the campaign be successful?
2. If the campaign was successful, how much of that success could be attributed to the ads?

# Recommendation

The campaign appears successful. Users exposed to the ads converted at a statistically significantly higher rate than users exposed to the PSA control group.

Based on the observed conversion lift, approximately 4,343 conversions can be attributed to the ads.

# Key Results

| Metric | Ad Group | PSA Group | Difference |
| --- | ---: | ---: | ---: |
| Users | 564,577 | 23,524 | 541,053 |
| Conversions | 14,423 | 420 | 14,003 |
| Conversion rate | 2.55% | 1.79% | 0.77 percentage points |
| Relative lift |  |  | 43.08% |
| z-statistic |  |  | 7.37 |
| p-value |  |  | < 0.001 |
| Estimated incremental conversions |  |  | 4,343 |

## Interpretation

To evaluate whether the campaign was successful, I ran a one-sided two-proportion z-test comparing conversion rates between users exposed to the ad and users exposed to the PSA control.

The test found a statistically significant increase in conversion rate for the ad group. The ad group converted at 2.55%, compared with 1.79% for the PSA group.

This is an absolute lift of 0.77 percentage points and a relative lift of 43.08%.

To estimate how much success could be attributed to the ads, I calculated incremental conversions:

```text
incremental conversions = (ad conversion rate - PSA conversion rate) * ad users
incremental conversions = (0.02555 - 0.01785) * 564,577
incremental conversions ≈ 4,343
