---
title: 'Geo Experiments : Power Analysis'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Statistical power is a crucial element in hypothesis testing, as it measures the ability to detect a real difference between test and control groups. A higher power means a lower likelihood of false negatives, where a true effect goes undetected. Typically, researchers aim for a power level above 80%, which ensures a reasonable chance of identifying an effect when it exists.

The power of an A/B test is influenced by four main factors:

1. **Statistical significance threshold** – This criterion controls the false positive rate. For instance, a significance level of 0.1 ensures that the false positive rate stays under 10%.
2. **Effect size** – The magnitude of the expected effect is often determined based on practical needs or prior knowledge. An effect smaller than 0.5% is often considered trivial due to noise and may not justify the effort of conducting the test.
3. **Sample size** – The number of observations plays a significant role in the ability to detect effects. Larger sample sizes generally improve the power of the test.
4. **Noise level** – Variability in the data can obscure true effects, making it harder to detect smaller changes.

In online A/B testing, power analysis is commonly performed to determine the minimum sample size required to detect an effect of a given size, under a specific significance level. The goal is to achieve a high statistical power, allowing detection of smaller effects efficiently.

Geo Experiment, takes this concept further by simulating experiments on historical data. It estimates the minimum detectable effect (MDE) with high power for each treatment group. For example, if you plan to run a one-month study and aim to detect a 5% lift, **Geo Experiment** will simulate this by removing the most recent month's data, using the remainder to build a synthetic control. A 5% lift is then applied to the test markets during the removed month, and GeoLift evaluates whether this effect can be reliably detected using the synthetic control.

This method allows experimenters to understand how large an effect needs to be to ensure high power in real-world conditions, improving the design and outcomes of geo-based tests.

<br />

At Lifesight, we use **prospective powcher analysis** on the data uploaded by users to help plan and run effective tests. In general, through the power analysis we can find: :

| Different Aspects of Test Planning | Decription                                                                                                                                                                      |
| :--------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| The Right Test and Control Markets | Power analysis helps find the best markets to test and compare. This makes sure the test results are balanced and reliable.                                                     |
| Test Budget                        | We calculate a good estimate of how much budget is needed to run the test. This helps avoid overspending while making sure the test is effective.                               |
| The Right Number of Test Locations | Power analysis helps figure out how many locations are needed to detect meaningful results. This ensures we have enough locations to get accurate data without going overboard. |
| the Best Test Duration             | We estimate how long the test should run to get clear results. The test needs to be long enough to capture effects but not too long to waste resources.                         |
| Minimum Detectable Effect (MDE)    | The MDE is the smallest change we can confidently measure in the test. Power analysis helps set this threshold so we know if the test can catch small but important changes.    |
