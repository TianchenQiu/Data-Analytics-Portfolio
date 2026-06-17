Executive Summary
Business Question
This analysis answers two questions:

Would the campaign be successful?
If the campaign was successful, how much of that success could be attributed to the ads?
Recommendation
The campaign appears successful. Users exposed to the ad converted at a statistically significantly higher rate than users exposed to the PSA control group.

Based on the observed lift, approximately 4,343 conversions can be attributed to the ads among users in the ad group.

Key Results
Metric	Ad Group	PSA Group	Difference
Users	564,577	23,524	541,053
Conversions	14,423	420	14,003
Conversion rate	2.55%	1.79%	0.77 percentage points
Relative lift			43.08%
z-statistic			7.37
p-value			< 0.001
Estimated incremental conversions			4,343
Interpretation
To evaluate whether the campaign was successful, I ran a one-sided two-proportion z-test comparing the conversion rate of the ad group against the PSA control group.

Null hypothesis: the ad group conversion rate is less than or equal to the PSA group conversion rate.
Alternative hypothesis: the ad group conversion rate is greater than the PSA group conversion rate.
The test returned a z-statistic of 7.37 and a p-value below 0.001. Since the p-value is below the 0.05 significance threshold, I reject the null hypothesis and conclude that the ad group converted at a statistically significantly higher rate than the PSA group.

The ad group conversion rate was 2.55%, compared with 1.79% for the PSA group. This means the ad campaign produced an absolute lift of about 0.77 percentage points and a relative lift of about 43.08%.

To estimate how much success can be attributed to the ads, I applied the conversion-rate lift to the number of users in the ad group:

incremental conversions = (ad conversion rate - PSA conversion rate) * ad users
incremental conversions = (0.02555 - 0.01785) * 564,577
incremental conversions ≈ 4,343
This suggests that approximately 4,343 conversions were incremental and attributable to the ads.

Exploratory Timing Findings
I also reviewed conversion patterns by weekday and hour of day. These analyses are exploratory because most_ads_day and most_ads_hour describe when each user saw the most ads, not a randomized treatment assignment.

A chi-square test found a statistically significant association between weekday and conversion status:

chi-square(6) = 410.05, p < 0.001
The highest overall conversion rates appeared on:

Weekday	Users	Conversions	Conversion rate
Monday	87,073	2,857	3.28%
Tuesday	77,479	2,312	2.98%
Wednesday	80,908	2,018	2.49%
A chi-square test also found a statistically significant association between hour of day and conversion status:

chi-square(23) = 430.77, p < 0.001
The strongest hours by overall conversion rate appeared around late afternoon and evening:

Hour	Users	Conversions	Conversion rate
16	37,567	1,156	3.08%
20	28,923	862	2.98%
15	44,683	1,325	2.96%
21	29,976	867	2.89%
17	34,988	987	2.82%
These timing patterns can help generate follow-up ideas, such as testing budget concentration on stronger weekdays or hours. However, they should not be described as causal proof that those times caused higher conversion without a dedicated timing experiment.

Caveats
Treatment and control group sizes are imbalanced.
Segment cuts by day and hour should be treated as exploratory unless pre-planned.
total_ads may reflect delivered exposure after assignment, so it should not be used as a simple pre-treatment control.
This analysis estimates conversion impact, not profit impact. Campaign cost and conversion value would be needed to judge ROI.
Next Steps
Add a confidence interval for the absolute conversion-rate lift.
Create a simple conversion-rate chart for the final portfolio version.
Run chi-square tests for weekday and hour association in the EDA notebook.
Translate incremental conversions into revenue or profit impact if conversion value and campaign cost are available.
