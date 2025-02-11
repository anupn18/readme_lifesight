---
title: How to optimize budget using constraints
excerpt: >-
  How to set optimal budget constraints for media channels to maximize
  incremental revenue.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Problem Statement:

How can you set the right budget constraints to maximize the effectiveness of your marketing spend? In marketing mix modelling, constraints dictate how much you can adjust spending on each media channel. If your constraints are too narrow, you risk limiting potential gains by sticking to conservative adjustments, which may prevent you from achieving the best possible returns. On the other hand, wider constraints offer flexibility, allowing you to explore more optimal allocations and improve overall performance. The challenge is finding the right balance to ensure your marketing budget is working as efficiently as possible to drive incremental revenue.

Note : constraints are also a way to inform the model of the practical real world limitations that needs to be considered before moving the budget.

***

### 1. How Budget Optimizer Works

Budget optimiser allocates the given budget across media variables based on their marginal returns. Variables with the highest marginal returns get highest allocation and so on. To direct the model to give reasonable and practical recommendations, lifesight lets marketer set the right constraints for every variable.

Once the optimiser exhaust the marginal return based budget allocation, given there is any residual budget to allocate, model will then look for two variable synergy (positive interaction effect) to divide the budget among media variables that shows positive interaction. This process then repeats for 3 variable interactions, 4 variable interactions and so on.

<br />

### 2. Narrow vs. Wide Budget Constraints:

When budget constraints are **narrow**, they tightly limit how much the spend on a media channel can be adjusted. For example, if the allowed spending range for a channel is very close to its current spend, the allocator has limited flexibility. As a result, the optimization may be more conservative, potentially missing opportunities to improve overall performance.

#### Example: This is a sample example of one of the marketing channels for our customer :

- **Narrow Bound (0.7–1.5x of current spend):** The allocator suggests a budget decrease from 5% to 3.5%. This conservative adjustment is due to the tight constraint, which restricts the ability to explore higher or lower spending levels that might yield better returns.
- **Wide Bound (0.1–2.5x of current spend):** When the constraint is loosened, the allocator can explore a broader range of spending options. In this case, it finds that increasing the spending to 12.4% would be more optimal. The wider bound allows the allocator to move along the saturation curve and find a point where the mROAS is higher, leading to a more effective allocation.

<br />

### 3. Saturation Curves and Optimization Potential

Saturation curves illustrate how the effectiveness of additional spending decreases as more budget is allocated to a channel. When a budget constraint is narrow, the allocator might be forced to stay within a part of the curve where the returns are linear. This means that the allocator is operating in a range where each additional dollar brings a `predictable`, but not necessarily `optimal`, return.

However, when the constraint is widened, the allocator can explore other parts of the curve, potentially moving into a range where the return per additional dollar starts to decrease more slowly or rapidly. This exploration can lead to a more efficient allocation, as the allocator might discover that reallocating budget from one channel with diminishing returns to another with higher potential can maximize overall performance.

<br />

### 4. The Risk of Being Too Conservative

If the constraints are too conservative (narrow), there is a risk that the allocator will not optimize the budget effectively. In the example of above we have shown how we are not getting the optimal return because our constraints are narrower.

**Key Takeaway:** While narrow constraints can keep spending within safe limits, they may also prevent the allocator from finding the most efficient distribution of the budget. Wider constraints, or at least understanding the potential impact of wider constraints, can lead to better optimization and higher overall returns.