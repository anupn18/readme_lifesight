---
title: Lifesight's approach to Causal Inference
excerpt: Understand how Lifesight approaches Causal Inference in the platform.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Lifesight’s approach to understanding and leveraging causal relationships in data is centered around a three-step process

## Step 1: Laying the Foundation

Our journey begins with the critical inputs of Data and Business Knowledge. This foundational step ensures that our analysis is grounded in the real-world context of your business, setting the stage for meaningful insights. 

## Step 2: Causal Inference

At Lifesight, we utilize the DECI (Deep End to End of Causal Inference) framework to underpin our approach to causal inference. This framework integrates both causal discovery and estimation processes into a cohesive end-to-end flow. 

1. #### Causal Discovery: 
   Causal discovery is a critical process aimed at identifying causal relationships between variables within observational data. The main objective is to uncover a network of causal relationships that aligns with both the collected data and predefined causal assumptions.
2. #### Directed Acyclic Graph (DAG): 
   The causal relationships are depicted in a Directed Acyclic Graph (DAG), where nodes represent variables and edges signify causal connections.
3. #### Bayesian Approach: 
   The DECI framework adopts a Bayesian methodology for causal discovery, incorporating prior knowledge and constraints to refine the search for causal relationships.

We employ a hybrid approach, combining Score and Constraint-based algorithms, to construct causal graphs. This method leverages causal assumptions to establish a preliminary graph, which is then refined using data-driven techniques.

**Score-Based Algorithm** searches for a causal graph that both aligns with the observational data and adheres to the specified constraints. To further refine the causal graph, we utilize Non-Linear Additive Noise Models, allowing for the correction of the graph to reveal true causal relationships, even from purely observational data.

## Causal Estimation 

Following the Causal Discovery, the DECI framework proceeds to Causal Estimation. This stage focuses on quantifying the Average Treatment Effects (ATE) using the established DAG.

Through calculus and the generative model learned by DECI, we simulate samples from intervened distributions to estimate treatment effects accurately.DECI provides an approximation of the posterior distribution over graphs, considering the observational data. This approximation is instrumental in understanding the treatment effects and the causal structure.

## DECI Assumptions

The DECI framework operates under several foundational assumptions, which include:

1. **Causal Markov Condition:** This assumes that all observed variables are independent of their non-effects, given their direct causes.
2. **Causal Faithfulness Condition:** It posits that all observed independencies in the data are attributable to the underlying causal structure.
3. **Non-Gaussianity:** The distribution of additive noise within the causal model is assumed to be non-Gaussian, aiding in the identification of causal relationships.
4. **Causal Sufficiency:** The framework assumes the absence of unobserved confounders, ensuring that all relevant variables are considered in the analysis.

## Step 3: Reporting and Insight Generation

The culmination of the above intricate process involves the presentation of **Average Treatment Effects (ATE)**, delivering profound insights into the ramifications of various interventions. 

The comprehension of ATE is essential for businesses, as it provides an overarching view of the average impact of interventions, thereby facilitating informed strategic decision-making.