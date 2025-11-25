---
title: Model Tuning
excerpt: How Lifesight Uses Evolutionary AI to Build Your Ideal Model
deprecated: false
hidden: false
metadata:
  robots: index
---
### Under the hood

Building a Marketing Mix Model (MMM) used to be a manual process of trial and error. An analyst would tweak variables, run a regression, check the error, and repeat—often introducing human bias along the way. t Lifesight, we take a different approach. We treat model selection not as a math problem to be solved once, but as an evolutionary process. Our engine generates thousands of potential models, tests them against reality, and uses Evolutionary Algorithms to "breed" the most accurate and logical outcomes.

***

Here is how our engine finds the right hyper-parameters for your specific data.

1. **Defining the "DNA" of Your Marketing**

Every business is unique. To capture this, our model optimizes a specific set of Hyperparameters—think of these as the DNA of the model. We don't just look at spend; we look at the behavior of that spend:

Ad Memory (Adstock): How long does an ad stay in a consumer's mind? Does a brand impression decay in two days or two weeks?

Diminishing Returns (Saturation): At what point does spending more money stop yielding proportional results? We look for the "tipping point" for every channel.

Noise Filtering (Regularization): How do we ensure the model reacts to true signal (marketing impact) rather than random noise in the data?

2. **Survival of the Fittest: The Evolutionary Algorithm**

Instead of trying to guess these parameters, the Lifesight engine uses Evolutionary Algorithms. The process mimics natural selection:

Initialization: The engine creates a massive population of random models, each with different "DNA" (combinations of adstock, saturation, and coefficients).

The Stress Test: Each model is evaluated to see how well it performs.

Selection & Mutation: The "weak" models (those that don't fit the data or don't make sense) are discarded. The "strong" models are kept and "mutated"—slightly tweaked to explore if small changes improve performance.

Generational Growth: This cycle repeats for thousands of iterations. Over time, the models evolve, becoming progressively smarter and more accurate.

3. **The "Two-Brain" Approach: Multi-Objective Optimization**

Most traditional modeling tools optimize for a single metric: Accuracy (low prediction error).

The problem? A model can be mathematically accurate but strategically impossible. For example, a model might predict sales perfectly but claim that TV contributes $0 revenue despite $1M in spend. This is "overfitting."

Lifesight uses Multi-Objective Optimization to solve for two conflicting goals simultaneously:

Objective A: Statistical Fit (The Math Brain): We minimize the prediction error (NRMSE). The model must accurately predict historical sales trends.

Objective B: Business Logic (The Strategy Brain): We minimize "Decomposition Distance" (DECOMP.RSSD). This metric ensures that the relationship between Share of Spend and Share of Effect is realistic. It penalizes models that suggest a channel with high spend has near-zero impact (or vice versa) without strong evidence.

**_[Note - Additional objectives are added when it comes to model calibration]_**

4. The Result: The Pareto Front

Because we optimize for two conflicting objectives (Math vs. Logic), there is rarely a single "perfect" model. Instead, our engine delivers a Pareto Front.

The Pareto Front is a collection of the optimal models where you cannot improve accuracy without sacrificing some business logic, and vice versa.

The Benefit: This gives you transparency and control. Rather than forcing a single "black box" number on you, Lifesight presents the best possible options—calibrated to your specific business context—allowing us to select the model that balances statistical power with strategic reality.

<br />
