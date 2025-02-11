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
<Table>
  <thead>
    <tr>
      <th>
        METHODOLOGY
      </th>

      <th>
        ASSUMPTIONS
      </th>

      <th>
        DRAWBACKS
      </th>

      <th>
        OTHER IMPORTANT POINTS
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        GEO-BASED
      </td>

      <td>
        • The treatment effect is homogeneous across different geographic regions\
        • The relationship between the outcome variable and other factors remains consistent across regions\
        • Random assignment successfully balances out any pre-existing differences between treatment and control groups
      </td>

      <td>
        • Spillover effects: Treatment applied in one region might influence the outcome in neighboring control regions\
        • Limited generalizability: The findings from one geographic area may not generalize to other areas with different characteristics\
        • Data availability: Obtaining data at the geo-level for all relevant metrics can be challenging\
        • Statistical power: The precision of the estimate depends on the number of geos
      </td>

      <td>
        • Best suited when many geos are available and spillover effects are minimal\
        • Privacy-friendly due to aggregated data at regional level\
        • Limited by geographic constraints
      </td>
    </tr>

    <tr>
      <td>
        TIME-BASED
      </td>

      <td>
        • The outcome variable exhibits a stable trend in the absence of intervention\
        • The treatment effect is consistent over time\
        • The model accurately captures the underlying data-generating process of the time series
      </td>

      <td>
        • Susceptibility to time-varying confounders: Uncontrolled external factors that change over time can bias the estimated impact\
        • Limited ability to isolate the treatment effect when multiple events occur
      </td>

      <td>
        • Suitable for gradual interventions over time\
        • Can estimate cumulative causal effect\
        • Limited by time series complexity
      </td>
    </tr>

    <tr>
      <td>
        MATCHED MARKET
      </td>

      <td>
        • The matched markets are similar in all relevant aspects except for the treatment\
        • The matching procedure effectively controls for confounding factors
      </td>

      <td>
        • Difficulty in finding perfectly matched markets\
        • Potential for hidden biases from unobserved differences between markets
      </td>

      <td>
        • Cost-effective for small number of geos\
        • Used for measuring offline impact of online advertising\
        • Limited by matching quality
      </td>
    </tr>

    <tr>
      <td>
        SYNTHETIC CONTROL METHOD
      </td>

      <td>
        The control time series used to construct the synthetic control are unaffected by the treatment\
        • The relationship between the control series and the treatment series that existed before the intervention continues afterward\
        • The model structure remains stable over time
      </td>

      <td>
        Dependence on good control time series\
        • Sensitivity to model misspecification
      </td>

      <td>
        Superior Approach for Causal Inference:  

        1. Enhanced Counterfactual Construction:\
           • Creates more accurate "synthetic" control groups using multiple control time series\
           • Minimizes impact of individual unit idiosyncrasies
        2. Flexibility in Control Selection:\
           • Enables data-driven selection of predictors• Allows flexible combination without restrictive constraints\
           • Leads to more adaptive and accurate counterfactuals
        3. Comprehensive Uncertainty Handling:\
           • Provides realistic and nuanced causal impact estimations
        4. Versatility:• Ideal for case studies with limited treated units\
           • Incorporates trends, seasonality, and time-varying covariates\
           • Adapts to both small and large-scale studies
        5. Robustness:\
           • Leverages multiple control series• Reduces reliance on single matched market\
           • Enhances overall analysis reliabilityWhile other methods have their place depending on context and data availability, SCM addresses many of their limitations, making it a powerful tool for understanding marketing intervention impacts in complex, real-world scenarios. 
      </td>
    </tr>
  </tbody>
</Table>
