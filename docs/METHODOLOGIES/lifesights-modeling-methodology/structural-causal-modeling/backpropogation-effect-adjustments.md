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
<br />

Before we start the back-propogation process, we have already successfully completed these two :

1. FCI based Causal Discovery based on the Causal Graph
2. Ridge Regression based Direct & Nested Direct effect estimation (A detailed view of this approach can be seen <Anchor label="here" target="_blank" href="https://docs.lifesight.io/update/docs/machine-learning-based-inference#/">here</Anchor> )

***

### Effect Adjustments - Getting to Indirect & Total Effects from Direct Effects

**To explain how the adjustment of contributions happens, let us take a simple example and go through the various stages**

**Stage 1 - We start with a DAG, backed by domain knowledge. Let us assume that the DAG looks like this :**

<Image align="center" border={false} src="https://files.readme.io/1d3538b3042854b70790afa437411c1918fbc997040f515c1f89c542134751f1-b.jpg" />

<br />

**Stage 2 - Apply Causal Discovery on this and we get to know the strength of these relationships**

[Refer this page to know about the <Anchor label="algorithm" target="_blank" href="https://docs.lifesight.io/update/docs/causal-discovery-estimation#/">algorithm</Anchor> ]

<Image align="center" border={false} src="https://files.readme.io/efa635ac780384cd72a5658ec228abe4b917ad64f27c75151d65fcd903bbff1f-c.jpg" />

<br />

**Step 3 - Get the direct effect and contribution from the ML based process based on ridge regression**

<Image align="center" border={false} src="https://files.readme.io/07eb051cede1f739c98a3a7dfdcd3b70fe4dda42af9385578fd38f853c57daae-d.jpg" />

**Step 4 - Run separate ridge regression approaches to explain the change in mediator variables as a function of its drivers**

This gives us the nested direct contribution of "Drivers" to "Mediators"

<Image align="center" border={false} src="https://files.readme.io/62f1b17fdf9ddcb88070f89821ddf62458cb8ffce8de270de8b185d88a2daccd-x.jpg" />

***

### The True Contribution with Back-propagation

True contribution is the sum of Direct & Indirect Contributions, also know as the **Total Effect**.

* For Drivers, Total Effect = Direct Effect + Indirect Effects
* For Mediator variables, Total Effect = Direct Effect - (Sum of Indirect Effects through them)

_This way we penalise the mediator and distribute the Effect (which is the incremental contribution) to the true causal drivers_

<Image align="center" border={false} src="https://files.readme.io/447c321faca3e1acaddc6dec0454fdd7af1dc5ddb6897e7893ed69b0afb05e67-z.jpg" />

<br />

**Example **

| Variable                       | Direct Effect on Sales | Indirect Effect (from DAG) | **Total Effect** |
| ------------------------------ | ---------------------- | -------------------------- | ---------------- |
| **TV**                         | 5%                     | **5.75%**                  | **10.75%**       |
| **Brand Equity**               | 20%                    | 1.5% - (4%)                | **17.5%**        |
| **Branded Search**             | 5%                     | -(1.5%+.25%)               | **3.25%**        |
| **Organic Search Impressions** | 5%                     | -.25%                      | **4.75%**        |
| **Retargeting**                | 10%                    | 4%                         | **6%**           |
| **Meta Prospecting**           | 15%                    | 4%                         | **19%**          |

<br />

Next let us understand the core ML algorithm that powers this inference. It is detailed [here](https://docs.lifesight.io/update/docs/machine-learning-based-inference#/)
