---
title: 'Geo Experiments: Comparison Methodology'
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
| **METHODOLOGY**                | **ASSUMPTIONS**                                                                       | **DRAWBACKS**                                                                                                 | **OTHER IMPORTANT POINTS**                                                                  |
| ------------------------------ | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Matched Market Tests (MMT)** | Test and control markets are close twins in historical conversions                    | Perfect matches are rare, hidden differences can bias results; low power with only one or two control markets | Simple and cost-effective for a few geos; historical precursor to synthetic-control methods |
| **Synthetic Control Method**   | Weighted blend of multiple control geos recreates the test geo’s pre-test conversions | More complex to implement and explain; needs robust historical data                                           | Delivers tighter confidence intervals and higher sensitivity than single-market tests       |

<br />

Lifesight uses GeoLift, a package developed by GeoLift for market selection and measurement of lift.

GeoLift combines two advanced **Synthetic Control Methods (SCM)** techniques: **Augmented Synthetic Control Methods (ASCM)** and **Generalized Synthetic Controls (GSC)**.

GeoLift uses **ASCM** to estimate and correct for bias in the synthetic control. It then applies **GSC**, which is robust to small sample sizes and differences across units, to deliver reliable inference.

This two-step approach helps manage issues caused by the curse of dimensionality, where increasing the number of units or historical data makes exact matching harder and increases bias. **GSC** also uses parametric bootstrapping to provide solid estimates of uncertainty and inference.

By integrating **ASCM** and **GSC**, GeoLift offers a robust solution to bias in synthetic control estimation. This does require more processing power but delivers more reliable and accurate measurement for your marketing experiments.