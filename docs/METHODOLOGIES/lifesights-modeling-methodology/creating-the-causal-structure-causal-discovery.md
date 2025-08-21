---
title: Creating the Causal Structure (Causal Discovery )
deprecated: false
hidden: true
metadata:
  robots: index
---
### Lifesight: A Unified Approach to Marketing Measurement

Lifesight is a unified marketing measurement platform that integrates three core functions : Causal Modelling, Experimentation, and Causal Attribution, into a single solution. Unlike traditional fragmented tools, it provides a holistic and accurate view of marketing performance by focusing on causal relationships rather than mere correlations. The platform is designed to empower businesses to make strategic, tactical, and operational decisions at scale, ensuring every action is grounded in reliable, cause-and-effect insights.

<br />

### Lifesight's Causal Modelling Approach :

Lifesight's Causal Modeling approach is a three-step process that moves beyond traditional statistical methods to provide a more accurate and reliable understanding of marketing's (and other factors) true impact.

***

#### Step 1 : Causal Structure in Marketing Mix Modeling (MMM)

The first and most critical phase of **Marketing Mix Modeling (MMM)** is the **creation of a causal structure**. This initial step is a **causal discovery process** that moves beyond simple correlation to identify the true cause-and-effect relationships within your data. The goal is to generate a **causal graph** that visually represents how marketing variables, external factors, and business outcomes are causally linked.

This process is essential for two reasons:

* **Mapping Causal Relationships**: The causal graph clearly illustrates how marketing spend (e.g., TV, social media), external influences (e.g., seasonality, competitor actions), and business metrics (e.g., sales) impact one another.
* **Validating Assumptions**: By automatically verifying these relationships against historical data, the model ensures that the identified connections are not merely coincidental correlations but are supported by strong evidence. This validation prevents common modeling errors and builds a more reliable foundation for your analysis.

#### The Iterative Process of Model Building

Developing this causal structure is an **iterative process** that requires integrating three key perspectives:

1. **Domain Knowledge**: The foundation of any good causal model is a deep understanding of the business and its consumers. Hypotheses about how variables influence one another are first formed based on insights from marketing and media experts. Since causality is inherently a **temporal relationship**, understanding the 'before/after' sequence of events is paramount.

2. **Data-Driven Insights**: This step involves analyzing historical data to validate or refine the initial hypotheses. The model automatically tests the proposed causal links, identifying which relationships are statistically significant and supported by the evidence. This helps uncover hidden dependencies that might not have been obvious from domain knowledge alone.

3. **Cross-Functional Collaboration**: The final model structure is a product of ongoing collaboration. Analysts work closely with marketers, media planners, and data owners to ensure the model accurately reflects real-world operations and data collection methodologies. This collaborative feedback loop is crucial for building a robust and trustworthy model.

<br />

#### \*\*Step 2: ML Based Inference \*\*

Once the causal graph is established, we run a sophisticated regression model. The key difference here is that the regression is **informed by the causal structure** identified in Step 1.

* **Causally Informed Modeling**: For example, if the causal graph indicates that top-of-funnel brand spend influences Google branded searches, our model will first account for the effect of that brand spend before isolating the unique, incremental impact of branded search itself. This ensures we are measuring true incrementality, not simply re-attributing effects.
* **Flexible and Data-Driven**: Our approach prefers to learn the **true incrementality directly from the data** without imposing strong, rigid assumptions (e.g., fixed adstock or saturation curves). This makes our models more adaptive and accurate. However, the platform is flexible enough to incorporate specific marketer priors or assumptions if desired.
* **Robustness through Bootstrapping**: To provide confidence in our findings, we employ a **bootstrapping method**. This resampling technique generates thousands of model variations to determine the most probable range for each variable's coefficient, providing a **95% confidence interval**. This statistical rigor ensures the coefficients are stable and reliable.

#### **Step 3: Incrementality-Adjusted Ensemble Forecasting**

This final step bridges the gap between historical inference and future prediction, a common trade-off in many data science projects.

* **Combining Inference and Prediction**: We run multiple forecasting algorithms (an **ensemble**) on the historical data. However, the crucial part is that these forecasts are then **adjusted based on the incrementality** inferred from Steps 1 and 2.
* **Accurate and Causal Predictions**: This ensures that our future predictions not only project trends but also correctly reflect the **true causal impact** of each marketing channel. The forecasts are not just accurate—they are causally sound, giving you a powerful tool for future budget allocation and planning.

***

### Key Advantages of Our Method

This unique three-step approach delivers a range of significant benefits that set our platform apart:

* **Combines Best-in-Class Methodologies**: We seamlessly blend the proven power of **traditional regression** with the accuracy of **causal AI**, creating a more comprehensive and robust model.
* **Stable and Reliable Coefficients**: Our causal-first approach helps us recover more stable and reliable coefficients, giving marketers higher confidence in the true incremental impact of their spend.
* **Full Transparency and Scrutiny**: Because the entire modeling process is housed within the Lifesight platform, every assumption, every relationship, and every result can be reviewed, challenged, and modified, providing unparalleled transparency.
* **Inference Meets Prediction**: We resolve the classic data science dilemma by creating a model that excels at both understanding the past and accurately predicting the future.
* **Continuous Monitoring and Adaptation**: Our system is designed for continuous learning. We offer regular model refreshes and monitoring to detect **concept drift**, ensuring the model remains accurate and relevant even as market dynamics change.
* **Integrates Diverse Schools of Thought**: Our methodology effectively combines elements from both **Bayesian and Frequentist** statistical schools, leveraging the strengths of each.
* **Advanced Planning Capabilities**: Our planning tool goes beyond a simple sum of incremental effects. It accounts for **synergy** (where channels amplify each other's effects) and **cannibalization** (where channels compete), providing a far more nuanced and effective planning solution.