---
title: Creating the Causal Structure (Causal Discovery )
deprecated: false
hidden: false
metadata:
  robots: index
---
### Marketing Mix Modeling (MMM) Methodology

<br />

### : Creation of a Causal Structure

The first phase of the **MMM (Marketing Mix Modeling) methodology** is the **Creation of a Causal Structure**. This is a **discovery step** that aims to understand the underlying data structure by generating a **causal graph** from two years of historical data. The primary goal is to move beyond simple correlations and identify true **causal relationships** between marketing variables, external factors, and key business metrics. The process also validates these relationships with evidence from the data, which helps to avoid common modelling pitfalls.

***

### The Causal Graph

The **causal graph** is a visual representation of how different variables influence each other. Key features of this graph include:

* **Mapping Causal Relationships**: It shows how marketing variables (like TV spend or social media ads) and external factors (like seasonality or competitor activity) impact your business metrics.
* **Validating Assumptions**: The model automatically verifies the causal assumptions based on the data, ensuring the relationships are supported by evidence and are not just coincidental correlations.

***

### The Three-Perspective Approach

In practice, the hypothesis building and analysis are an iterative process that involves going back and forth between three perspectives to determine the appropriate model structure.

1. **Domain Knowledge**: Hypotheses are first formed based on a deep understanding of how consumers purchase the products or services being modeled. This requires specific domain knowledge in marketing and media to understand temporal relationships, as causality is always a **before/after relationship** in time. Analysts should consult with marketers and media representatives to understand the specific methodologies used for data collection.
2. **Data Representativeness**: The model's representativeness is evaluated based on the possibility of collecting and measuring the necessary data.
3. **Model Structure Rules**: The model structure must adhere to specific rules to accurately reflect marketing and media causality:
   * **Temporal Causality**: The model structure must reflect the **before/after** nature of cause-and-effect relationships.
   * **Hierarchical Arrangement**: Variables that are in an inclusion relationship should not be placed in the same hierarchy within the model structure.
   * **Objective Variable Separation**: The model structure for the objective variable should be kept separate.
   * **Data-Driven Estimation**: Causal graphs are estimated directly from the data, assuming a distribution of functions.

Our  MMM methodology is a three-step process that overcomes the limitations of traditional models by combining the best of causal AI and regression analysis.

#### **Step 1: Creation of  Causal Structure**

This initial phase is a **discovery step** focused on understanding the underlying structure of your data. Using two years of historical data, our platform automatically generates a **causal graph**.  This graph is a powerful representation that:

* **Identifies Causal Relationships**: It visually maps out how different marketing variables (e.g., TV spend, social media ads) and external factors (e.g., seasonality, competitor activity) influence each other and your key business metrics.
* **Validates Causal Assumptions**: By analyzing the data, the model verifies the validity of these relationships, ensuring we aren't making assumptions that aren't supported by evidence. This prevents common modeling pitfalls where correlation is mistaken for causation.

#### **Step 2: Regression with Causal Priors**

Once the causal graph is established, we run a sophisticated regression model. The key difference here is that the regression is **informed by the causal structure** identified in Step 1.

* **Causally Informed Modeling**: For example, if the causal graph indicates that top-of-funnel brand spend influences Google branded searches, our model will first account for the effect of that brand spend before isolating the unique, incremental impact of branded search itself. This ensures we are measuring true incrementality, not simply re-attributing effects.
* **Flexible and Data-Driven**: Our approach prefers to learn the **true incrementality directly from the data** without imposing strong, rigid assumptions (e.g., fixed adstock or saturation curves). This makes our models more adaptive and accurate. However, the platform is flexible enough to incorporate specific marketer priors or assumptions if desired.
* **Robustness through Bootstrapping**: To provide confidence in our findings, we employ a **bootstrapping method**. This resampling technique generates thousands of model variations to determine the most probable range for each variable's coefficient, providing a **95% confidence interval**. This statistical rigor ensures the coefficients are stable and reliable.

#### **Step 3: Incrementality-Adjusted Ensemble Forecasting** 🔮

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