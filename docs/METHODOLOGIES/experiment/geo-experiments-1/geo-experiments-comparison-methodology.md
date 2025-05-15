---
title: 'Geo Experiments: Comparison Methodology'
excerpt: ''
deprecated: false
hidden: true
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