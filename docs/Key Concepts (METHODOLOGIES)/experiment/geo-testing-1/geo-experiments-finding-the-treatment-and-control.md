---
title: >-
  Geo-Experiments: Assigning Treatment and Control, and Establishing
  Counterfactuals
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
Geo-experiments offer a unique approach for evaluating the impact of marketing efforts on a regional scale. Unlike traditional, user-based experiments, geo-experiments assign treatment and control across entire regions, allowing for broader observations. 

### 1. Overview: Geo vs. User-Level Experiments 

Geo-experiments differ fundamentally from user-level experiments in terms of assignment, measurement, and application. The following table summarises the distinctions between the two types:

|                            | **User-Based Experiments**                                      | **Region-Based (Geo) Experiments**                                                               |
| -------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **Assignment Method**      | Randomly assigns individuals to treatment/control groups        | Assigns entire regions (e.g., cities, DMAs) to treatment/control groups                          |
| **Ideal Context**          | Digital environments where individual-level control is feasible | Offline or media contexts where individual assignment is impractical                             |
| **Level of Measurement**   | Individual outcomes (clicks, conversions, etc.)                 | Aggregate outcomes (regional sales, foot traffic)                                                |
| **Randomization Benefits** | Minimizes bias, ensures precise exposure control                | Reduces spillover effects by grouping regions, enabling market-level targeting                   |
| **Advantages**             | High control over exposure, detailed user insights              | Allows analysis of regional effects, suitable for interventions targeting broad geographic areas |
| **Challenges**             | Spillover and network effects can be challenging                | Regional differences can complicate matching; may need larger samples for statistical power      |

**Why Use Geo-Experiments?**  
Geo-experiments are particularly useful in scenarios where **spillover effects** or **regional targeting** complicate user-level randomization. By focusing on regions, we can observe aggregate shifts in response to interventions like regional ad campaigns or in-store promotions.

***

### 2. Methodology: Quasi-Causal Approaches in Geo-Experiments

When designing geo-experiments, we often face logistical and contextual constraints that make pure randomization challenging. In such cases, quasi-causal methods provide a structured approach for estimating the impact of interventions by constructing counterfactual scenarios.

#### 2.1 Causal Methods (Ideal but Limited Feasibility)

Causal methods directly assign regions to treatment and control groups through randomization, ensuring high internal validity.

- **Random Assignment**: Each region has an equal probability of receiving treatment, helping balance both observable and unobservable factors.
- **Challenges**: In geographic settings, constraints like the limited number of regions, dependencies between regions, and operational limitations often restrict the feasibility of pure randomization.

#### 2.2 Quasi-Causal Methods

When pure randomization is unfeasible, quasi-causal methods help simulate a **counterfactual**, or what would have occurred without the intervention. These methods are essential for maintaining validity in geo-experiments.

**Common Quasi-Causal Methods in Geo-Experiments:**

- **Synthetic Control Method (SCM)**: Constructs a synthetic version of the treatment region by weighting data from multiple control regions. This synthetic region approximates pre-treatment characteristics, providing a reliable comparison.

  **Example**:

  ```plaintext
  Treatment Region: New York City
  Synthetic Control Pool: Chicago (weight: 0.4), Boston (weight: 0.3), Philadelphia (weight: 0.3)
  Synthetic NYC = 0.4×Chicago + 0.3×Boston + 0.3×Philadelphia
  ```

<br />

# Lifesight's Approach: Augmented Synthetic Control Method (ASCM)

The **Augmented Synthetic Control Method (ASCM)** is an enhancement over the original Synthetic Control Method (SCM) that addresses limitations when achieving a strong pre-treatment fit is challenging. SCM assumes a perfect pre-treatment fit, and if this is not attainable, SCM guidelines recommend avoiding its use. ASCM, however, provides a solution by explicitly estimating and correcting bias introduced by imperfect pre-treatment fits.

Here's how ASCM tackles this problem:

- **Recognizing the Bias:** ASCM acknowledges that imperfect pre-treatment fit introduces bias into the estimate. It uses an outcome model to explicitly estimate the extent of this bias.
- **De-biasing the Estimate:** ASCM employs a bias-correction technique, similar to methods used in inexact matching. This involves adjusting the initial SCM estimate by subtracting the estimated bias derived from the outcome model.
- **Ridge Regression for Balance:**   Ridge ASCM, as this method is called, retains the weighted average structure of SCM but permits negative weights on some control units, enabling better pre-treatment fit even when the treated unit lies outside the convex hull of control units.

**Regularization as a Key Feature:** Ridge ASCM incorporates a regularization parameter (λridge) that directly governs the degree of extrapolation allowed. Higher values of  λridge result in weights closer to the original SCM weights, minimizing extrapolation. Lower values permit greater extrapolation to enhance pre-treatment fit.

**Benefits under Different Data Generating Processes:**

| **Model Type**          | **Description**                                                                                                                                                                    | **How ASCM is Useful**                                                                                                                                        |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Linear Model**        | A regression model that assumes a linear relationship between outcome and predictor variables. The effect of predictors is assumed proportional to changes in the outcome.         | ASCM improves the model by reducing bias in cases where the pre-treatment fit is not perfect, enhancing accuracy in the impact estimate.                      |
| **Linear Factor Model** | An extension of linear models that incorporates unobserved, latent factors affecting the outcome. Useful for time-series or panel data with shared influences across observations. | ASCM corrects bias from imperfect fits while balancing against overfitting risks, especially with complex datasets. Regularization helps optimize model fit./ |

> 📘 Note: We have captured the comparison of methodologies for other geo experiments here: Comparison Methodology.