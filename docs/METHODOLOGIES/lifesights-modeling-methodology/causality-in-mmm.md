---
title: Causality in MMM
excerpt: How Lifesight makes MMM causally informed
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Traditional ML approaches can primarily only detect trends and patterns. It is not inherently suitable to infer causality for a variety of reasons, such as :

1. For robust causal inference we need to bring data together with certain assumptions about causal directions among the variables in the Data
2. Data in itself does not help in causal inference (though it can be used for pattern recognition)

Associations (in Data) can be thought of as a function of Causation and Bias. Causal Inference techniques provides us with certain tools and approaches to handle the Bias part, so that Associations can be used to infer Causation.

<Image align="center" src="https://files.readme.io/4cadd1816a961fc41de87e669e12f4d7990fa0db1f30fd468224611ba71e638a-Screenshot_2025-01-22_at_12.29.42_PM.png" />

\_[Causal Inference could be thought of as the process to address the Bias algorithmically ]\_

Causal Inference happens in two steps : 

1. Causal Discovery 
2. Causal Estimation

In this **Causal Discovery** is primarily Human Guided. Given certain assumptions (stated using a DAG and informed by strong business domain knowledge) of cause and effect between the variables, data is used to discover the strength of these relationships. 

**Causal Estimation** , once the DAG is agreed upon, we can apply multiple techniques to infer the average treatment effects and marginal effects of the relationships. Some of the popular Causal Estimation Techniques are Regression, Double Machine Learning, Structural Causal Models and Meta-Learners.

\_[Lifesight currently uses Regression and is Actively researching Double Machine Learning and Structural Causal Models for Causal Estimation]\_

**Why do we need Causal AI for MMM**

1. Some of the assumptions of traditional regression models are not grounded in reality - example independence of input variables [ Top of the funnel spend and Bottom of the funnel spend are not truly independent of one another ]
2. Need for complex modelling (interaction effects, nested models, feature selection etc... ) can be easily rationalised using causal discovery (instead of using traditional approaches such as PCA or Factor Analysis)
3. Causal Inference based estimation techniques are more robust and resistant to change in environment (Models drift less frequently as compared to traditional regression based models)
4. Outcome of MMM models are used to for "what if" analyses, predictive forecasting and counterfactual reasoning - causal AI based techniques are more suitable for this  

Note : The limitations in entrusting statistical modeling or machine learning techniques alone for causal inference could be well understood from certain statistical paradoxes, such as

1. [Simpson's Paradox](https://en.wikipedia.org/wiki/Simpson%27s_paradox)
2. [Lord's Paradox ](https://causality.cs.ucla.edu/blog/index.php/2019/08/13/lords-paradox-the-power-of-causal-thinking/)
3. [Berkson's Paradox](https://en.wikipedia.org/wiki/Berkson%27s_paradox)

In Lifesight, our focus is to build a Causal MMM model that can perform quasi-causal inferences on observational data - Essentially, this approach could be thought of as running a large number of retrospective incrementality experiments on top of observed historical data. 

This is how we go about introducing causality into our process

1. We start by first understanding the relationships in the data in the forms of DAGs : Chains (mediators) , Forks (confounders) & Colliders are identified
2. We understand the nature of relationships : Direct, Indirect (Halo), Interaction (Synergy/Antagonism)
3. We use a combination of Ridge Regression, Nested Models & Hierarchical models to quasi-causally understand the marginal, incremental and average effects of all the interactions
4. We also incorporate experiment result through a [calibration](https://docs.lifesight.io/docs/calibration) process to incorporate causal inputs to the model

<Image align="center" src="https://files.readme.io/80ddbc93d67b5819125d4b614bdd1dabc097838d5d1b20eb99e0e7793c1f08f4-DAGg.jpg" />

<br />

Need for [Advanced Modelling Approaches](https://docs.lifesight.io/docs/causality-in-mmm) is informed by the causal structure discovered from the DAG and its weights.