---
title: Understanding Causal DAGs
deprecated: false
hidden: false
metadata:
  robots: index
---
## Introduction

The marketing landscape has evolved dramatically, with businesses managing increasingly complex relationships between channels, tactics, and performance metrics. Traditional approaches to relationship management in regression based Modeling systems often fall short when dealing with the intricate web of modern marketing ecosystems. Causal DAG represents a fundamental paradigm shift that addresses these challenges head-on, providing a structured, hierarchical approach to relationship management that enhances both clarity and control.

## Our DAG Philosophy

At the core of our approach lies a transformative philosophy rooted in causal thinking: **reality is not tabular, it's graphical**. While traditional data analysis approaches treat variables as independent columns in a table, we recognize that marketing variables exist in a complex web of interdependencies that can only be properly understood through graphical representation.

Our philosophy addresses four fundamental challenges in marketing measurement:

**Data Requires Human Intelligence**: Raw data is inherently "dumb" – it lacks the contextual understanding that only human expertise can provide. While data might suggest that the number of characters in a person's first name correlates with their weight, human intelligence recognizes this as spurious correlation. Similarly, marketing data requires human judgment to distinguish between meaningful causal relationships and statistical artifacts.

**Avoiding Statistical Paradoxes**: The same dataset can yield contradictory conclusions depending on how questions are framed – a phenomenon exemplified by Simpson's Paradox. Marketing decision makers, not just data scientists, must take control of defining the right questions and causal assumptions to avoid misleading insights.

**Making Assumptions Explicit**: All statistical models make implicit assumptions about independence and identical distribution that rarely hold true in marketing. Top-of-funnel spending influences bottom-of-funnel performance, seasonality affects both revenue and media investment decisions, and intervention scenarios change the very distributions that models were trained on. Causal DAG makes these assumptions explicit and testable.

**Graphical Reality Representation**: Marketing relationships exist as networks of cause and effect, not isolated correlations. Seasonality doesn't just drive revenue – it influences investment decisions that create brand equity, which in turn affects demand capture efficiency. Only through graphical representation can we identify mediators, confounders, and colliders that traditional tabular approaches miss.

Our foundational principle: **Correlation equals Causation plus Bias**. By explicitly modeling causal structure through DAGs, we can identify and remove bias, transforming correlation into meaningful causal insights that drive better decision-making.

## Types of DAG

Causal DAG uses a two-tier architecture that separates business-level relationship logic from model-specific implementations.

![](https://files.readme.io/f8231cc780dcdec9211c386cabfeadd638839a0ec19f290a1bd577abe9957cb8-image.png)

### Business Graph (Workspace DAG)

The Workspace DAG serves as the foundational layer that captures your organization's understanding of how marketing variables interact to drive business outcomes. Think of it as your Business Model.

**Key Characteristics:**

* Represents causal relationships at the business logic level
* Serves as a template for all new model DAGs
* Can change as your business model evolves
* Managed collaboratively across teams

**Use Cases:**

* Define standard causal pathways between media channels and KPIs
* Establish assumptions about external factors and confounders
* Create reusable templates for consistent modeling approaches
* Document business logic supporting causal relationships

### Model Graph (Model DAG)

Model DAGs represent the implementation of business relationships within specific modeling contexts. Each model inherits its initial structure from the Workspace DAG.

**Key Characteristics:**

* Inherits structure from Workspace DAG at creation
* Read-only after model creation to ensure integrity
* Model-specific implementation of business relationships
* Individual identity for comparison and analysis

**Use Cases:**

* Tactic-specific modeling with inherited business logic
* Temporal modeling with consistent foundational assumptions
* Individual model analysis and comparison

## Critical Importance in the Unified Marketing Measurement (UMM) Space

UMM requires moving beyond simple correlation analysis to understand the true causal mechanisms driving marketing performance. Causal DAG addresses three key challenges:

**Cross-Channel Attribution**: Understanding how channels create, amplify, and depend on each other requires graphical thinking. Brand building creates conditions that make performance marketing more effective, while demand capture depends on upstream awareness generation.

**Intervention Modeling**: UMM must answer "what if" questions about scaling, reducing, or eliminating channels. These interventions change data distributions, requiring causal understanding rather than correlation-based prediction.

**Stakeholder Alignment**: UMM success depends on alignment around causal understanding. Causal DAG enables business leaders to take control of causal assumptions and ensures statistical findings pass the test of business logic.

## Conclusion

Causal DAG represents more than a feature enhancement—it's a strategic evolution toward causal thinking in marketing measurement. By recognizing that reality is graphical rather than tabular, and that correlation equals causation plus bias, it enables marketing teams to build measurement systems grounded in true causal understanding rather than statistical correlation.

The transition from pure data-driven analysis to causal thinking empowers decision makers to take control of their assumptions, avoid statistical paradoxes, and build models that remain valid under intervention scenarios. The two-tier architecture ensures that business logic remains consistent while allowing for model-specific flexibility, creating a foundation for reliable measurement across diverse marketing contexts.

As marketing continues to evolve in complexity, the organizations that invest in causal thinking and structured relationship management will be best positioned to extract meaningful insights, optimize performance, and drive sustainable growth. Causal DAG provides the foundation for this competitive advantage, transforming relationship management from a necessary complexity into a strategic asset that delivers genuine causal insights.

***