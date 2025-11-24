---
title: Backpropogation & Effect Adjustments
excerpt: >-
  How effects are back-propogated to get the indirect effect and the true total
  effects
deprecated: false
hidden: false
metadata:
  robots: index
---
Before we start this step, we have already successfully completed these two :

1. FCI based Causal Discovery based on the Causal Graph
2. Ridge Regression based Direct & Indirect effect estimation (A detailed view of this approach can be seen <Anchor label="here" target="_blank" href="https://docs.lifesight.io/update/docs/machine-learning-based-inference#/">here</Anchor> )

***

### Effect Adjustments - Getting to Indirect & Total Effects from Direct Effects

**To explain how the adjustment of contributions happens, let us take a simple example and go through the various stages**

**Step 1 - Let us assume we started with a DAG , that looks like this :**

<Image align="center" border={false} src="https://files.readme.io/1d3538b3042854b70790afa437411c1918fbc997040f515c1f89c542134751f1-b.jpg" />

<br />

**Step 2 - Apply Causal Discovery on this and we get to know the strength of these relationships**

<Image align="center" border={false} src="https://files.readme.io/efa635ac780384cd72a5658ec228abe4b917ad64f27c75151d65fcd903bbff1f-c.jpg" />

<br />

**Step 3 - Get the direct effect and contribution from the ML based process**

<Image align="center" border={false} src="https://files.readme.io/07eb051cede1f739c98a3a7dfdcd3b70fe4dda42af9385578fd38f853c57daae-d.jpg" />

**Step 4 - Run separate ridge regression approaches to explain the change in mediator variables as a function of its drivers**

This helps us break down Contribution the Direct effect to its indirect contributions

<Image align="center" border={true} src="https://files.readme.io/3073977cb96716eefb1ddd6afd3c2717bf2d5d33c099876c03f72550009a451e-e.jpg" className="border" />

***

### The True Contribution

True contribution is the sum of Direct & Indirect Contributions. For Mediator variables, their Indirect effect is negative as they have incoming arrows that's supporting their values

<br />

| Variable                       | Direct Effect on Sales | Indirect Effect (via mediators)                                                       | Total Effect |
| ------------------------------ | ---------------------- | ------------------------------------------------------------------------------------- | ------------ |
| **TV**                         | 5%                     | 20% (via Brand Equity) + 30% (via Branded Search) + 5% (via Organic Search) = **55%** | **60%**      |
| **Meta Prospecting**           | 15%                    | 40% (via Retargeting)                                                                 | **55%**      |
| **Brand Equity**               | 20%                    | 30% (via Branded Search)                                                              | **50%**      |
| **Branded Search**             | 5%                     | —                                                                                     | **5%**       |
| **Organic Search Impressions** | 5%                     | —                                                                                     | **5%**       |
| **Retargeting**                | 10%                    | —                                                                                     | **10%**      |

<br />
